---
title: Planification DNS avancée du serveur Edge pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Résumé : Examinez les scénarios relatifs aux options de déploiement de Skype entreprise Server. Si vous voulez utiliser un serveur unique ou si vous préférez un pool de serveurs avec DNS ou HLB, cette rubrique devrait vous aider.'
ms.openlocfilehash: 098d25a23745c035813cfc5c0ea6d291999c3704
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803384"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Planification DNS avancée du serveur Edge pour Skype entreprise Server
 
**Résumé :** Passez en revue les scénarios relatifs aux options de déploiement de Skype entreprise Server. Si vous voulez utiliser un serveur unique ou si vous préférez un pool de serveurs avec DNS ou HLB, cette rubrique devrait vous aider.
  
Dans le cadre de la planification de votre système de nom de domaine (DNS) pour Skype entreprise Server, il existe de nombreux facteurs qui peuvent être à votre décision. Si la structure de domaines de votre organisation est déjà en place, la question est peut-être de réviser la façon dont vous allez procéder. Commençons par les rubriques situées ci-dessous :
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Les clients Skype entreprise sont similaires aux versions précédentes de clients Lync dans le cas où ils trouvent et accèdent aux services dans Skype entreprise Server. Cette section aborde en détail le processus d’emplacement du serveur.
  
1. lyncdiscoverinternal. \<Domain (domaine)\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le service de découverte automatique sur les services web internes.* 
    
2. lyncdiscover. \<Domain (domaine)\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le service de découverte automatique sur les services web internes.* 
    
3. _sipinternaltls. _tcp. \<Domain (domaine)\>
    
     *Il s’agit d’un enregistrement SRV pour les connexions TLS internes.* 
    
4. _sip. _tls. \<Domain (domaine)\>
    
     *Il s’agit d’un enregistrement SRV pour les connexions TLS externes.* 
    
5. sipinternal. \<Domain (domaine)\>
    
     *Il s’agit d’un enregistrement hôte du pool frontal ou du réalisateur qui peut être résolu uniquement sur le réseau interne.* 
    
6. SIP. \<Domain (domaine)\>
    
     *Il s’agit d’un enregistrement hôte du pool frontal ou du réalisateur qui peut être résolu uniquement sur le réseau interne.* 
    
7. sipexternal. \<Domain (domaine)\>
    
     *Il s’agit d’un enregistrement hôte du service Edge d’accès, lorsque le client est externe.* 
    
Le service de découverte automatique est toujours privilégié, car il s’agit de la méthode préférée pour l’emplacement du service, et les autres sont des méthodes de secours.
  
> [!NOTE]
> Lorsque vous créez des enregistrements SRV, il est important de ne pas oublier qu’ils doivent pointer vers un DNS A (et AAAA si vous utilisez l’adressage IPv6) dans le même domaine que celui sur lequel l’enregistrement DNS SRV est créé. Par exemple, si l’enregistrement SRV se trouve dans contoso.com, l’enregistrement A (et AAAA) vers lequel il pointe ne peut pas se trouver dans fabrikam.com. 
  
Si vous avez vraiment envie d’y parvenir, vous pouvez configurer votre appareil mobile à la découverte manuelle des services. Si c’est ce que vous cherchez à faire, chaque utilisateur doit configurer ses paramètres de l’appareil mobile avec les URI complètes interne et externe du service de découverte automatique, dont le protocole et le chemin d’accès, comme suit :
  
- Pour l’accès externe :\<https://\>ExtPoolFQDN/Autodiscover/autodiscoverservice.svc/root
    
- Pour l’accès interne :\<https://\>IntPoolFQDN/autodiscover/autodiscover.svc/root
    
Nous vous recommandons l’utilisation de la découverte automatique par opposition à la découverte manuelle. Mais si vous faites de la résolution de problèmes ou des tests, les paramètres manuels peuvent être très utiles.
  
## <a name="split-brain-dns"></a>DNS split-brain
<a name="SplitBrainDNS"> </a>

Il s’agit d’une configuration DNS où vous avez deux zones DNS avec le même espace de noms. La première zone DNS traite les demandes internes, tandis que la deuxième zone DNS traite les requêtes.
  
Pourquoi une société fait-elle ceci ? Peut-être à cause d’une obligation d’utiliser le même espace de noms en interne et en externe, mais, bien sûr, vous aboutissez ainsi à de nombreux enregistrements DNS SRV et A qui sont uniques pour une zone ou une autre et, là où il y a duplication, les adresses IP associées à ces enregistrements sont uniques.
  
Cela présente certains défis. Le plus important est que le DNS partagé par le cerveau n’est **pas pris en charge** pour la mobilité. Ceci est dû aux enregistrements DNS LyncDiscover et LyncDiscoverInternal (LyncDiscover doit être défini sur votre serveur DNS externe, tandis que LyncDiscoverInternal doit être défini sur votre serveur DNS interne).
  
Nous allons répertorier les enregistrements DNS pour les zones internes et externes ici, mais vous trouverez des exemples détaillés dans la section Configuration requise pour l’environnement du serveur Edge.
  
### <a name="internal-dns"></a>DNS interne

- Contient une zone DNS appelée (par exemple) contoso.com, pour laquelle il fait autorité.
    
- Ce contoso.com interne contient :
    
  - Les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour votre liste frontale, votre pool de directeurs ou le nom du pool de réalisateurs, ainsi que tous les serveurs internes exécutant Skype entreprise Server sur le réseau de votre organisation.
    
  - Les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour votre interface interne latérale pour chaque serveur Edge Skype entreprise Server dans votre réseau de périmètre.
    
  - Les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne de chaque serveur proxy inverse dans votre réseau de périmètre (qui est **facultatif** pour la gestion d’un proxy inverse).
    
  - DNS A et AAAA (si vous utilisez l’adressage IPv6) et enregistrements SRV pour la configuration automatique du client Skype entreprise Server interne ( **facultatif** ).
    
  - Les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) ou les enregistrements CNAMe pour la découverte automatique des services Web Skype entreprise Server ( **facultatif** ).
    
- Toutes les interfaces Edge internes de Skype entreprise Server dans votre réseau de périmètre utilisent cette zone DNS interne pour la résolution des requêtes vers contoso.com.
    
- Tous les serveurs exécutant Skype entreprise Server et clients exécutant Skype entreprise Server sur le réseau d’entreprise, pointez sur les serveurs DNS internes pour la résolution des requêtes vers contoso.com, ou utilisez le fichier hôte sur chaque serveur Edge et la liste A et le AAAA (si vous utilisez Adressage IPv6) pour le serveur du tronçon suivant (spécialement pour le directeur ou le VIP du pool de réalisateurs, le protocole VIP du pool frontal ou le serveur Standard Edition Server).
    
### <a name="external-dns"></a>DNS externe

- Contient une zone DNS appelée (par exemple) contoso.com, pour laquelle il fait autorité.
    
- Ce contoso.com externe contient :
    
  - Les DNS A et AAAA (si vous utilisez l’adressage IPv6), ou les enregistrements CNAMe pour la découverte automatique des services Web de Skype entreprise Server. Ils s’utilisent avec la mobilité.
    
  - Les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6), ainsi que les enregistrements SRV pour l’interface externe Edge de chaque adresse VIP du serveur Edge Skype entreprise Server ou de l’équilibrage de charge matérielle (HLB) dans le réseau de périmètre.
    
  - Les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et les enregistrements SRV pour l’interface externe du serveur proxy inverse ou (VIP pour un pool de serveurs proxy inverse), dans le réseau de périmètre.
    
  - DNS A et AAAA (si vous utilisez l’adressage IPv6) et enregistrements SRV pour la configuration automatique du client Skype entreprise Server ( **facultatif** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuration automatique sans DNS Split-Brain
<a name="NoSplitBrainDNS"> </a>

Si vous n’utilisez pas le DNS fractionné-Brain, la configuration automatique de clients exécutant Skype entreprise ne fonctionne pas, sauf si vous utilisez l’une des solutions de contournement dont nous disposons. Pourquoi ? Dans la mesure où Skype entreprise Server nécessite que l’URI SIP de l’utilisateur corresponde au domaine du pool frontal désigné pour la configuration automatique. Ce n’est pas le cas pour les versions antérieures de Lync Server.
  
Par conséquent, si vous avez deux domaines SIP (Session Initiation Protocol) utilisés, vous avez besoin de ces enregistrements SRV DNS :
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Si un utilisateur se connecte en tant que bob@contoso.com, cet enregistrement fonctionnera pour la configuration automatique, car le domaine SIP de l’utilisateur correspond au domaine du pool frontal (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Si un utilisateur se connecte en tant que alice@fabrikam.com, cet enregistrement fonctionnerait pour la configuration automatique du deuxième domaine, de nouveau, car le domaine SIP correspond au pool frontal pour ce domaine.* 
    
Pour développer l’exemple, cela ne fonctionne pas :
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un utilisateur se connectant en tant que tim@litwareinc.com ne fonctionnera pas pour la configuration automatique, car son domaine SIP (Session Initiation Protocol) (litwareinc.com) ne correspond pas au domaine dans le pool (fabrikam.com).* 
    
À présent que nous savons que c’est le cas, si vous avez besoin d’une configuration automatique pour vos clients Skype entreprise sans DNS split-brain, vous disposez des options suivantes :
  
- **Objets de stratégie de groupe**
    
    Vous pouvez utiliser des objets de stratégie de groupe (GPO) pour remplir le serveur avec les valeurs correctes.
    
    > [!NOTE]
    > Cette option ne permet pas d’autoriser la configuration automatique, mais elle automatise la configuration manuelle. Si cette approche est utilisée, les enregistrements SRV associés à la configuration automatique ne sont pas obligatoires. 
  
- **Zone interne correspondante**
    
    Vous devez créer une zone dans votre DNS interne qui correspond à votre zone DNS externe (par exemple, contoso.com), puis créer des enregistrements DNS A (et AAAA si vous utilisez l’adressage IPv6) qui correspondent au pool de serveurs Skype entreprise utilisé pour le regroupement automatique. configurations.
    
    Par exemple, si vous avez un utilisateur hébergé sur pool01.contoso.net, mais que vous vous connectez à Skype entreprise en tant que bob@contoso.com, créez une zone DNS interne appelée contoso.com, et à l’intérieur de celle-ci, vous devez créer un enregistrement DNS A (et le protocole AAAA si l’adressage IPv6 est utilisé) pour pool01.contoso.com.
    
- **Repérage de la zone interne**
    
    Si la création d’une zone complète dans votre DNS interne n’est pas envisageable pour vous, vous pouvez créer des zones repère (dédiées) qui correspondent aux enregistrements SRV requis pour la configuration automatique, et renseigner ces zones à l’aide de dnscmd.exe. Dnscmd.exe est obligatoire car l’interface utilisateur DNS ne prendra pas en charge la création de zones repère.
    
    Par exemple, si votre domaine SIP est contoso.com et que vous avez un pool frontal appelé pool01 qui contient deux serveurs frontaux, vous aurez besoin des zones de points de repère et des enregistrements A suivants dans votre DNS interne :
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Vous avez peut-être un second domaine SIP (Session Initiation Protocol) dans votre environnement. Dans ce cas, vous avez besoin des zones repère et des enregistrements A suivants dans votre DNS interne :
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Le nom de domaine complet (FQDN) du pool frontal apparaît deux fois, mais avec deux adresses IP différentes. C’est parce que l’équilibrage de charge DNS est utilisé. Si HLB est utilisé, il n’y a qu’une entrée de pool frontal unique. 
  
> [!NOTE]
> Par ailleurs, les valeurs de nom de domaine complet du pool frontal changent entre les exemples contoso.com et fabrikam.com, mais les adresses IP restent identiques. En effet, les utilisateurs qui se connectent à partir d’un domaine SIP utiliseront le même pool frontal pour la configuration automatique. 
  
## <a name="dns-disaster-recovery"></a>DNS disaster recovery
<a name="DNSDR"> </a>

Pour configurer le DNS afin de rediriger le trafic Web de Skype entreprise Server vers votre système de reprise après sinistre et vos sites de basculement, vous devez utiliser un fournisseur DNS qui prend en charge GeoDNS. Vous pouvez configurer vos enregistrements DNS pour qu’ils prennent en charge la récupération après sinistre, de sorte que les fonctionnalités qui utilisent des services Web continuent de fonctionner, même si un pool frontal complet est disponible. Cette fonctionnalité DR prend en charge les URL simples de découverte automatique, de réunion et de rendez-vous.
  
Vous définissez et configurez des enregistrements d’hôte DNS A (AAAA en cas d’utilisation d’IPv6) supplémentaires pour la résolution interne et externe des services web au niveau de votre fournisseur GeoDNS. Les détails suivants supposent l’existence de pools associés et géographiquement dispersés, et le fait que GeoDNS est pris en charge par votre fournisseur **avec**DNS round-robin **ou** qu’il est configuré de façon à utiliser Pool1 comme pool principal et à basculer vers Pool2 en cas de perte de communication ou de défaillance matérielle.
  
Tous les enregistrements DNS dans ce tableau sont des exemples.
  
|**Enregistrement GeoDNS**|**Enregistrements de pool**|**Enregistrements CNAME**|**Paramètres DNS (sélectionnez une option)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com vers Meet-int.geolb.contoso.com  <br/>   <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisez le principal, se connecter au secondaire en cas de défaillance  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com vers Meet-ext.geolb.contoso.com  <br/>   <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com vers Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com vers Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com vers Meet-int.geolb.contoso.com   <br/>   <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com vers Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com vers Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com vers Meet-ext.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
   
## <a name="dns-load-balancing"></a>Équilibrage de charge DNS
<a name="DNSLB"> </a>

L’équilibrage de charge DNS est généralement mis en œuvre au niveau de l’application. L’application (par exemple, un client exécutant Skype entreprise) essaie de se connecter à un serveur dans un pool en vous connectant à l’une des adresses IP renvoyées à partir de l’adresse DNS A et du nom de domaine complet du pool.
  
Par exemple, s’il existe trois serveurs front end dans un pool intitulé pool01.contoso.com, les éléments suivants se produisent :
  
- Clients exécutant la requête DNS de Skype entreprise pour pool01.contoso.com. La requête renvoie trois adresses IP et les met dans le cache comme suit (pas nécessairement dans cet ordre) :
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Le client essaie d’établir une connexion TCP à l’une des adresses IP. En cas d’échec, il essayera l’adresse IP suivante qu’il a mise en cache de cette liste.
    
- Si la connexion TCP aboutit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool1.contoso.com.
    
- Si le client tente d’accéder à toutes les entrées du cache sans connexion réussie, l’utilisateur reçoit une notification indiquant qu’aucun serveur exécutant Skype entreprise Server n’est disponible pour le moment.
    
> [!NOTE]
> L’équilibrage de charge DNS est différent du tourniquet (round robin) DNS (DNS RR), qui fait généralement référence à l’équilibrage de charge en s’appuyant sur DNS pour donner un ordre d’adresses IP différent pour les serveurs dans votre pool. En règle générale, DNS RR active la distribution de la charge, mais il ne vous permettra pas d’activer le basculement. Par exemple, si la connexion à l’adresse IP renvoyée par votre requête DNS (ou AAAA dans un scénario IPv6) échoue, cette connexion échouera. Cela rend DNS RR moins fiable que l’équilibrage de charge DNS. Vous pouvez toujours utiliser DNS RR conjointement avec l’équilibrage de charge DNS si vous avez besoin de procéder ainsi. 
  
Vous utilisez l’équilibrage de charge DNS pour :
  
- Équilibrage de charge : SIP de serveur à serveur sur les serveurs de périphérie.
    
- équilibrer la charge des applications des services d’applications de communications unifiées (UCAS) telles que le Standard automatique de conférence, Response Group et le parcage d’appel ;
    
- empêcher les nouvelles connexions aux applications UCAS (également appelé « drainage ») ;
    
- Equilibrez le trafic client à serveur entre les clients et les serveurs de périphérie.
    
Vous ne pouvez pas utiliser l’équilibrage de charge DNS pour :
  
- Trafic Web de client à serveur vers votre serveur frontal ou un directeur.
    
Pour plus d’informations sur la façon dont un enregistrement SRV DNS est sélectionné lorsque des enregistrements DNS mutiple sont renvoyés par une requête, le service Edge d’accès sélectionne toujours l’enregistrement avec la priorité numérique la plus basse et, si un débordement est nécessaire, le poids numérique le plus élevé. Cette fonction est cohérente avec [la documentation sur Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Ainsi, par exemple, si votre premier enregistrement DNS SRV a un poids de 20 et une priorité de 40, et votre deuxième enregistrement SRV DNS a une valeur de 10 et une priorité de 50, le premier enregistrement va être choisi car il a la priorité basse de 40. La priorité vient toujours d’abord, et c’est l’hôte qu’un client va cibler le premier. Que se passe-t-il s’il existe deux cibles ayant la même priorité ? 
  
Dans ce cas, le poids vient en considération. Les poids les plus élevés doivent recevoir une forte probabilité d’être sélectionnés dans ces conditions. Les administrateurs DNS doivent utiliser un poids égal à 0 quand il n’y a aucune sélection de serveur à effectuer. En présence d’enregistrements contenant des poids supérieurs à 0, les enregistrements de poids nul ont une chance très faible d’être sélectionnés.
  
Alors, que se passe-t-il si plusieurs SRV DNS de même priorité et de même poids s’enregistrent comme renvoyés ? Dans ce cas, le service Edge d’accès choisit l’enregistrement SRV qu’il a obtenu du serveur DNS d’abord.
  

