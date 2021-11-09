---
title: Planifier le déploiement de serveurs Edge avancés pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: Examinez les scénarios pour Skype Entreprise Server options de déploiement, que vous vouliez un serveur unique ou préférez un pool de serveurs avec DNS ou HLB.
ms.openlocfilehash: 5fa829bf805529792abb408cd6716e2948dd69ef
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842767"
---
# <a name="plan-advanced-edge-server-deployment-for-skype-for-business-server"></a>Planifier le déploiement de serveurs Edge avancés pour Skype Entreprise Server
 
**Résumé :** Examinez les scénarios pour Skype Entreprise Server options de déploiement. Que vous vouliez un serveur unique ou préférez un pool de serveurs avec DNS ou HLB, cette rubrique doit vous aider.
  
En ce qui concerne la planification DNS (Domain Name System) pour Skype Entreprise Server, de nombreux facteurs peuvent prendre en compte votre décision. Si la structure de domaine de votre organisation est déjà en place, il peut s’agir d’un examen de la façon dont vous allez procéder. Nous allons commencer par les rubriques ci-dessous :
  
- [Walkthrough of Skype Entreprise clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Configuration automatique sans DNS split-brain](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Récupération d’urgence DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [équilibrage de charge DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype Entreprise clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype Entreprise clients sont similaires aux versions précédentes des clients Lync dans la façon dont ils trouvent et accèdent aux services Skype Entreprise Server. Cette section détaille le processus d’emplacement du serveur.
  
1. lyncdiscoverinternal.\<domain\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le service de découverte automatique sur les services web internes.* 
    
2. lyncdiscover.\<domain\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le service de découverte automatique sur les services web externes.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *Il s’agit d’un enregistrement SRV pour les connexions TLS internes.* 
    
4. _sip._tls.\<domain\>
    
     *Il s’agit d’un enregistrement SRV pour les connexions TLS externes.* 
    
5. sipinternal.\<domain\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le pool frontal ou le directeur, qui peut être résolu uniquement sur le réseau interne.* 
    
6. sip.\<domain\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le pool frontal ou le directeur, qui peut être résolu uniquement sur le réseau interne.* 
    
7. sipexternal.\<domain\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le service Edge d’accès, lorsque le client est externe.* 
    
Le service de découverte automatique est toujours privilégié, car il s’agit de la méthode préférée pour l’emplacement du service, tandis que les autres sont des méthodes de retour.
  
> [!NOTE]
> Lorsque vous créez des enregistrements SRV, il est important de ne pas oublier qu’ils doivent pointer vers un DNS A (et AAAA si vous utilisez l’adressare IPv6) dans le même domaine dans lequel l’enregistrement DNS SRV est créé. Par exemple, si l’enregistrement SRV est en contoso.com, l’enregistrement A (et AAAA) vers qui il pointe ne peut pas se trouver dans fabrikam.com. 
  
Si vous avez envie de le faire, vous pouvez configurer votre appareil mobile pour la découverte manuelle des services. Si c’est ce que vous cherchez à faire, chaque utilisateur doit configurer ses paramètres d’appareil mobile avec les URL complètes du service de découverte automatique interne et externe, y compris le protocole et le chemin d’accès, comme suit :
  
- Pour l’accès externe : https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- Pour l’accès interne : https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
Nous vous recommandons d’utiliser la découverte automatique par opposition à la découverte manuelle. Toutefois, si vous faites des tests ou des dépannages, les paramètres manuels peuvent s’avérer très utiles.
  
## <a name="split-brain-dns"></a>Split-brain DNS
<a name="SplitBrainDNS"> </a>

Il s’agit d’une configuration DNS dans laquelle vous avez deux zones DNS avec le même espace de noms. La première zone DNS gère les demandes internes, tandis que la seconde zone DNS gère les demandes externes.
  
Pourquoi une entreprise le ferait-elle ? Ils peuvent avoir besoin d’utiliser le même espace de noms en interne et en externe, mais bien entendu, cela conduit à de nombreux enregistrements DNS SRV et A à être uniques à une zone ou une autre, et en cas de duplication, les adresses IP associées à ces enregistrements sont uniques.
  
Cela présente certains défis. Le plus important est que le DNS split-brain **n’est pas pris en charge pour** la mobilité. Cela est dû aux enregistrements DNS LyncDiscover et LyncDiscoverInternal (LyncDiscover doit être défini sur votre serveur DNS externe, tandis que LyncDiscoverInternal doit être défini sur votre serveur DNS interne).
  
Nous allons énumérer les enregistrements DNS pour les zones internes et externes ici, mais vous trouverez des exemples détaillés dans la section sur les exigences environnementales du serveur Edge.
  
### <a name="internal-dns"></a>DNS interne

- Contient une zone DNS appelée (par exemple) contoso.com, pour laquelle elle fait autorité.
    
- Cette contoso.com contient :
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressare IPv6) pour votre pool frontal, pool directeur ou nom de pool directeur, et tous les serveurs internes exécutant Skype Entreprise Server dans le réseau de votre organisation.
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressag IPv6) pour votre interface interne Edge pour chaque serveur Edge Skype Entreprise Server dans votre réseau de périmètre.
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressag IPv6) pour l’interface  interne de chaque serveur proxy inverse de votre réseau de périmètre (facultatif pour la gestion d’un proxy inverse).
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressag IPv6) et SRV pour  la configuration automatique du client Skype Entreprise Server interne (facultatif).
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressamage IPv6) ou CNAME  pour la découverte automatique des services web Skype Entreprise Server (facultatif).
    
- Toutes vos interfaces Edge internes Skype Entreprise Server votre réseau de périmètre utilisent cette zone DNS interne pour résoudre les requêtes en contoso.com.
    
- Tous les serveurs exécutant Skype Entreprise Server et les clients exécutant des Skype Entreprise Server dans le réseau d’entreprise pointent vers des serveurs DNS internes pour résoudre les requêtes en contoso.com, ou ils utilisent le fichier hôte sur chaque serveur Edge et rép. rép. les enregistrements A et AAAA (si vous utilisez l’adressare IPv6) pour le serveur du saut suivant (spécifiquement pour l’adresse IP ip du directeur ou du pool directeur,  VIP du pool frontal ou serveur Édition Standard serveur frontal).
    
### <a name="external-dns"></a>DNS externe

- Contient une zone DNS appelée (par exemple) contoso.com, pour laquelle elle fait autorité.
    
- Cette contoso.com externe contient :
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressamage IPv6) ou CNAME pour la découverte automatique de Skype Entreprise Server services web. Il s’agit d’une utilisation avec la mobilité.
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressag IPv6) et SRV pour l’interface externe Edge de chaque serveur Edge Skype Entreprise Server ou VIP avec équilibrage de la charge matérielle dans le réseau de périmètre.
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressare IPv6) et SRV pour l’interface externe du serveur proxy inverse ou (ADRESSE IP ip pour un pool de serveurs proxy inverses) dans le réseau de périmètre.
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressag IPv6) et SRV  pour la configuration automatique du client Skype Entreprise Server (facultatif).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuration automatique sans DNS split-brain
<a name="NoSplitBrainDNS"> </a>

Si vous n’utilisez pas le DNS split-brain, la configuration automatique interne des clients exécutant Skype Entreprise ne fonctionne pas, sauf si vous utilisez l’une des solutions de contournement que nous avons ici. Pourquoi ? Étant Skype Entreprise Server l’URI SIP de l’utilisateur doit correspondre au domaine du pool frontal désigné pour la configuration automatique. Cela n’a pas changé par rapport aux versions antérieures de Lync Server.
  
Ainsi, si vous avez deux domaines SIP en cours d’utilisation, vous avez besoin des enregistrements DNS SRV suivants :
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Si un utilisateur se bob@contoso.com, cet enregistrement fonctionne pour la configuration automatique, car le domaine SIP de l’utilisateur correspond au domaine du pool frontal (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Si un utilisateur se alice@fabrikam.com, cet enregistrement fonctionne pour la configuration automatique du deuxième domaine, car le domaine SIP correspond au pool frontal pour ce domaine.* 
    
Pour aller plus loin dans l’exemple, cela ne fonctionne pas :
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un utilisateur qui se tim@litwareinc.com ne fonctionne pas pour la configuration automatique, car son domaine SIP (litwareinc.com) ne correspond pas au domaine du pool (fabrikam.com).* 
    
Maintenant que nous savons tout cela, si vous avez besoin d’une exigence automatique pour vos clients Skype Entreprise sans DNS split-brain, vous avez les options ci-après :
  
- **Objets de stratégie de groupe**
    
    Vous pouvez utiliser des objets de stratégie de groupe pour remplir les valeurs de serveur correctes.
    
    > [!NOTE]
    > Cette option n’active pas la configuration automatique, mais elle automatise la configuration manuelle. Si cette approche est utilisée, les enregistrements SRV associés à la configuration automatique ne sont pas requis. 
  
- **Zone interne correspondante**
    
    Vous devez créer une zone dans votre DNS interne qui correspond à votre zone DNS externe (par exemple, contoso.com), puis créer des enregistrements DNS A (et AAAA si vous utilisez l’adressare IPv6) qui correspondent au pool Skype Entreprise Server utilisé pour la configuration automatique.
    
    Par exemple, si vous avez un utilisateur sur pool01.contoso.net Skype Entreprise, mais que vous vous y êtes invité en tant que bob@contoso.com, créez une zone DNS interne appelée contoso.com et, à l’intérieur, vous devez créer un enregistrement DNS A (et AAAA si l’adressace IPv6 est utilisé) pour pool01.contoso.com.
    
- **Repérer la zone interne**
    
    Si la création d’une zone entière dans votre DNS interne n’est pas une option pour vous, vous pouvez créer des zones de point d’épingle (dédiées) qui correspondent aux enregistrements SRV requis pour la configuration automatique et remplir ces zones à l’aide de dnscmd.exe. Dnscmd.exe est nécessaire, car l’interface utilisateur DNS ne permet pas de créer des zones de point d’épingle.
    
    Par exemple, si votre domaine SIP est contoso.com et que vous avez un pool frontal appelé pool01 qui contient deux serveurs frontaux, vous aurez besoin des zones de point d’épingle et des enregistrements A suivants dans votre DNS interne :
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Vous pouvez avoir un second domaine SIP dans votre environnement. Dans ce cas, vous aurez besoin des zones de point d’épingle et des enregistrements A suivants dans votre DNS interne :
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Le FQDN du pool frontal apparaît deux fois, mais avec deux adresses IP différentes. Cela est dû au fait que l’équilibrage de charge DNS est utilisé. Si l’lb de hlb est utilisé, il n’y aurait qu’une seule entrée de pool frontal. 
  
> [!NOTE]
> En outre, les valeurs de nom de pool frontal changent entre les exemples contoso.com et fabrikam.com, mais les adresses IP restent identiques. En effet, les utilisateurs qui se sont signés à partir de l’un ou l’autre domaine SIP utiliseront le même pool frontal pour la configuration automatique. 
  
## <a name="dns-disaster-recovery"></a>Récupération d’urgence DNS
<a name="DNSDR"> </a>

Pour configurer DNS afin de rediriger le trafic web Skype Entreprise Server vers vos sites de récupération d’urgence et de récupération d’urgence, vous devez utiliser un fournisseur DNS qui prend en charge GeoDNS. Vous pouvez configurer vos enregistrements DNS pour prendre en charge la récupération d’urgence, afin que les fonctionnalités qui utilisent les services web continuent même si un pool frontal entier est en panne. Cette fonctionnalité de dr prend en charge les URL simples de découverte automatique, meet et dial-in.
  
Vous définissez et configurez des enregistrements A (AAAA) d’hôte DNS supplémentaires si vous utilisez IPv6 pour la résolution interne et externe des services web au niveau de votre fournisseur GeoDNS. Les détails suivants supposent que les pools couplés, géographiquement dispersés, sont pris en charge par votre fournisseur soit avec le DNS round robin, soit configurés pour utiliser Pool1 comme pool principal et échouent vers Pool2 en cas de perte de communication ou de panne d’alimentation.  
  
Tous les enregistrements DNS de ce tableau sont des exemples.
  
|**Enregistrement GeoDNS**|**Enregistrements de pool**|**Enregistrements CNAME**|**Paramètres DNS (sélectionnez une option)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à Meet-int.geolb.contoso.com  <br/>   <br/> |Round Robin entre pools  <br/> **OR** <br/> Utiliser le principal, se connecter au secondaire en cas d’échec  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à Meet-ext.geolb.contoso.com  <br/>   <br/> |Round Robin entre pools  <br/> **OR** <br/> Utiliser le principal, se connecter au secondaire en cas d’échec  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OR** <br/> Utiliser le principal, se connecter au secondaire en cas d’échec  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin entre pools  <br/> **OR** <br/> Utiliser le principal, se connecter au secondaire en cas d’échec  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à Meet-int.geolb.contoso.com   <br/>   <br/> |Round Robin entre pools  <br/> **OR** <br/> Utiliser le principal, se connecter au secondaire en cas d’échec  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin entre pools  <br/> **OR** <br/> Utiliser le principal, se connecter au secondaire en cas d’échec  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OR** <br/> Utiliser le principal, se connecter au secondaire en cas d’échec  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à Meet-ext.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OR** <br/> Utiliser le principal, se connecter au secondaire en cas d’échec  <br/> |
   
## <a name="dns-load-balancing"></a>équilibrage de charge DNS
<a name="DNSLB"> </a>

L’équilibrage de charge DNS est généralement implémenté au niveau de l’application. L’application (par exemple, un client exécutant Skype Entreprise) tente de se connecter à un serveur d’un pool en se connectant à l’une des adresses IP renvoyées par la requête d’enregistrement DNS A et AAAA (si l’adressace IPv6 est utilisé) pour le nom de groupe de noms de pool.
  
Par exemple, s’il existe trois serveurs frontux dans un pool nommé pool01.contoso.com, les choses suivantes se produisent :
  
- Les clients exécutant Skype Entreprise DNS pour obtenir pool01.contoso.com. La requête renvoie trois adresses IP et les met en cache comme suit (dans un certain ordre) :
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Le client tente d’établir une connexion TCP à l’une des adresses IP. En cas d’échec, il essaiera l’adresse IP suivante qu’il est mis en cache à partir de cette liste.
    
- Si la connexion TCP réussit, le client négocie TLS pour se connecter au bureau d’enregistrement principal sur pool01.contoso.com.
    
- Si le client tente toutes les entrées mises en cache sans connexion réussie, l’utilisateur reçoit une notification vous avertissant qu’aucun serveur Skype Entreprise Server n’est disponible pour le moment.
    
> [!NOTE]
> L’équilibrage de charge DNS est différent de DNS round robin (DNS RR), qui fait généralement référence à l’équilibrage de charge en s’appuyant sur DNS pour donner un ordre différent d’adresses IP pour les serveurs de votre pool. En règle générale, DNS RR active la distribution de la charge, mais ne vous permet pas d’activer le failover. Par exemple, si la connexion à l’adresse IP renvoyée par votre requête DNS A (ou AAAA dans un scénario IPv6) échoue, cette connexion échoue. Cela rend DNS RR moins fiable que l’équilibrage de charge DNS. Vous pouvez toujours utiliser DNS RR conjointement avec l’équilibrage de charge DNS si vous devez le faire. 
  
Vous utilisez l’équilibrage de charge DNS pour :
  
- Équilibrez la charge sip de serveur à serveur sur les serveurs Edge.
    
- Équilibrer la charge des applications UCAS (Unified Communication Application Services), telles que Standard automatique conférence, Response Group et parcage d’appel.
    
- Empêcher les nouvelles connexions aux applications UCAS (également appelées drainage).
    
- Équilibrez la charge de tout le trafic client à serveur entre les clients et les serveurs Edge.
    
Vous ne pouvez pas utiliser l’équilibrage de charge DNS pour :
  
- Trafic web client à serveur vers vos serveurs frontux ou un directeur.
    
Pour approfondir la sélection d’un enregistrement SRV DNS lorsque plusieurs enregistrements DNS sont renvoyés par une requête, le service Edge d’accès sélectionne toujours l’enregistrement ayant la priorité numérique la plus faible et, si un analyseur d’égalité est nécessaire, la pondération numérique la plus élevée. Cela est cohérent avec la [documentation du groupe de travail d’ingénierie Internet.](https://www.ietf.org/rfc/rfc2782.txt)
  
Par exemple, si votre premier enregistrement DNS SRV a une pondération de 20 et une priorité de 40, et que votre deuxième enregistrement DNS SRV a une pondération de 10 et une priorité de 50, le premier enregistrement sera choisi car il a la priorité inférieure de 40. La priorité passe toujours en premier, et c’est l’hôte qu’un client va cibler en premier. Que se passe-t-il si deux cibles ont la même priorité ? 
  
Dans ce cas, l’importance est prise en compte. Les pondérations plus importantes doivent avoir une probabilité élevée, dans ce cas, d’être sélectionnées. Les administrateurs DNS doivent utiliser le poids 0 lorsqu’il n’y a aucune sélection de serveur à faire. En présence d’enregistrements contenant des poids supérieurs à 0, les enregistrements de poids 0 ont peu de chances d’être sélectionnés.
  
Que se passe-t-il donc si plusieurs enregistrements SRV DNS avec une priorité et une pondération égales comme renvoyés ? Dans ce cas, le service Edge d’accès choisit d’abord l’enregistrement SRV qu’il a obtenu du serveur DNS.
  

