---
title: DNS du serveur Edge une planification avancée pour Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Résumé : Examen de scénarios pour Skype pour les options de déploiement de serveur d’entreprise. Si vous souhaitez qu’un seul serveur ou que vous préférez un pool de serveurs DNS ou matérielle, cette rubrique doit contribuer à.'
ms.openlocfilehash: e6619056d7c8a69f63fa22007a7702b41480719f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207180"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>DNS du serveur Edge une planification avancée pour Skype pour Business Server
 
**Résumé :** Examen de scénarios pour Skype pour les options de déploiement de serveur d’entreprise. Si vous souhaitez qu’un seul serveur ou que vous préférez un pool de serveurs DNS ou matérielle, cette rubrique doit contribuer à.
  
Lorsqu’il s’agit de planification de nom de domaine DNS (Domain Name System) pour Skype pour Business Server, il existe un grand nombre de facteurs qui peuvent être lus dans votre décision. Si la structure de domaines de votre organisation est déjà en place, la question est peut-être de réviser la façon dont vous allez procéder. Commençons par les rubriques situées ci-dessous :
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype pour les clients d’entreprise sont similaires aux versions antérieures de clients Lync dans leur trouvent et accéder aux services dans Skype pour Business Server. Cette section aborde en détail le processus d’emplacement du serveur.
  
1. lyncdiscoverinternal. \<domaine\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le service de découverte automatique sur les services web internes.* 
    
2. lyncdiscover. \<domaine\>
    
     *Il s’agit d’un enregistrement d’hôte A pour le service de découverte automatique sur les services web internes.* 
    
3. _sipinternaltls._tcp. \<domaine\>
    
     *Il s’agit d’un enregistrement SRV pour les connexions TLS internes.* 
    
4. _sip._tls. \<domaine\>
    
     *Il s’agit d’un enregistrement SRV pour les connexions TLS externes.* 
    
5. sipinternal. \<domaine\>
    
     *Il s’agit d’un enregistrement A d’hôte pour le pool frontal ou directeur, être résolu uniquement sur le réseau interne.* 
    
6. SIP. \<domaine\>
    
     *Il s’agit d’un enregistrement A d’hôte pour le pool frontal ou directeur, être résolu uniquement sur le réseau interne.* 
    
7. sipexternal. \<domaine\>
    
     *Il s’agit d’un enregistrement A d’hôte pour le service Edge d’accès, lorsque le client est externe.* 
    
Le service de découverte automatique est toujours privilégié, car il s’agit de la méthode préférée pour l’emplacement du service, et les autres sont des méthodes de secours.
  
> [!NOTE]
> Lorsque vous créez des enregistrements SRV, il est important de ne pas oublier qu’ils doivent pointer vers un DNS A (et AAAA si vous utilisez l’adressage IPv6) dans le même domaine que celui sur lequel l’enregistrement DNS SRV est créé. Par exemple, si l’enregistrement SRV se trouve dans contoso.com, l’enregistrement A (et AAAA) vers lequel il pointe ne peut pas se trouver dans fabrikam.com. 
  
Si vous avez vraiment envie d’y parvenir, vous pouvez configurer votre appareil mobile à la découverte manuelle des services. Si c’est ce que vous cherchez à faire, chaque utilisateur doit configurer ses paramètres de l’appareil mobile avec les URI complètes interne et externe du service de découverte automatique, dont le protocole et le chemin d’accès, comme suit :
  
- Pour l’accès externe : https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- Pour l’accès interne : https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
Nous vous recommandons l’utilisation de la découverte automatique par opposition à la découverte manuelle. Mais si vous faites de la résolution de problèmes ou des tests, les paramètres manuels peuvent être très utiles.
  
## <a name="split-brain-dns"></a>DNS split-brain
<a name="SplitBrainDNS"> </a>

Il s’agit d’une configuration DNS où vous avez deux zones DNS avec le même espace de noms. La première zone DNS traite les demandes internes, tandis que la deuxième zone DNS traite les requêtes.
  
Pourquoi une société fait-elle ceci ? Peut-être à cause d’une obligation d’utiliser le même espace de noms en interne et en externe, mais, bien sûr, vous aboutissez ainsi à de nombreux enregistrements DNS SRV et A qui sont uniques pour une zone ou une autre et, là où il y a duplication, les adresses IP associées à ces enregistrements sont uniques.
  
Cela présente certains défis. Le plus important est que DNS Split-Brain est le **pas pris en charge** pour la mobilité. Ceci est dû aux enregistrements DNS LyncDiscover et LyncDiscoverInternal (LyncDiscover doit être défini sur votre serveur DNS externe, tandis que LyncDiscoverInternal doit être défini sur votre serveur DNS interne).
  
Nous allons répertorient les enregistrements DNS pour les zones internes et externes ici, mais vous pouvez trouver des exemples détaillés dans la section exigences de serveur de transport Edge.
  
### <a name="internal-dns"></a>DNS interne

- Contient une zone DNS appelée (par exemple) contoso.com, pour laquelle il fait autorité.
    
- Ce contoso.com interne contient :
    
  - Des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour votre pool frontal, le pool directeur ou nom de pool directeur et tous les serveurs internes exécutant Skype pour Business Server dans le réseau de votre organisation.
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne du serveur Edge pour chaque Skype pour Business serveur Edge dans votre réseau de périmètre.
    
  - Des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne de chaque serveur proxy inverse dans votre réseau de périmètre (qui est **facultatif** pour la gestion d’un proxy inverse).
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour Skype interne pour la configuration automatique du client Business Server (qui est **facultative** ).
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) ou CNAME pour la découverte automatique de Skype pour Business Server Web Services (qui est **facultative** ).
    
- Tous vos Skype pour les interfaces Edge internes Business Server dans votre réseau de périmètre utiliser cette zone DNS interne pour résoudre les requêtes vers contoso.com.
    
- Pointez sur tous les serveurs exécutant Skype pour Business Server et les clients exécutant Skype pour Business Server dans le réseau d’entreprise, les serveurs DNS internes pour résoudre les requêtes vers contoso.com, ou ils utilisent le fichier hôte sur chaque serveur Edge, liste A et AAAA (si vous utilisez Adressage IPv6) des enregistrements pour le serveur du tronçon suivant (en particulier pour le directeur ou adresse IP virtuelle du pool directeur, Front End pool VIP ou serveur Standard Edition server).
    
### <a name="external-dns"></a>DNS externe

- Contient une zone DNS appelée (par exemple) contoso.com, pour laquelle il fait autorité.
    
- Ce contoso.com externe contient :
    
  - DNS A et AAAA (si vous utilisez l’adressage IPv6) ou CNAME enregistre pour la découverte automatique de Skype pour les services web Business Server. Ils s’utilisent avec la mobilité.
    
  - DNS A et AAAA (si vous utilisez l’adressage IPv6) et les enregistrements SRV pour l’interface externe Edge de chaque Skype pour Business Server Edge Server ou de la charge matérielle équitablement adresse IP virtuelle (du) dans le réseau de périmètre.
    
  - Des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour l’interface externe du serveur proxy inverse ou (adresse IP virtuelle pour un pool de serveurs proxy inverses), dans le réseau de périmètre.
    
  - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour Skype pour la configuration automatique des clients Business Server ( **facultatif** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuration automatique sans DNS Split-Brain
<a name="NoSplitBrainDNS"> </a>

Si vous n’utilisez pas DNS split-brain, interne configuration automatique des clients exécutant Skype pour les entreprises ne fonctionne pas, sauf si vous utilisez une des solutions que nous avons ici. Pourquoi ? Étant donné que Skype pour Business Server nécessite l’URI SIP de l’utilisateur correspondre au domaine du pool frontal désigné pour la configuration automatique. Cela n’a pas changé par rapport aux versions antérieures de Lync Server.
  
Par conséquent, si vous avez deux domaines SIP (Session Initiation Protocol) utilisés, vous avez besoin de ces enregistrements SRV DNS :
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Si un utilisateur se connecte en tant que bob@contoso.com, cet enregistrement fonctionnerait pour la configuration automatique, comme domaine SIP de l’utilisateur correspond au domaine du pool frontal (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Si un utilisateur se connecte en tant que alice@fabrikam.com, cet enregistrement fonctionnerait pour la configuration automatique du deuxième domaine, nouveau, car le domaine SIP établit une correspondance avec le pool frontal pour ce domaine.* 
    
Pour développer l’exemple, cela ne fonctionne pas :
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un utilisateur se connectant en tant que tim@litwareinc.com ne fonctionnera pas pour la configuration automatique, car son domaine SIP (Session Initiation Protocol) (litwareinc.com) ne correspond pas au domaine dans le pool (fabrikam.com).* 
    
Maintenant que nous savons que tout, si vous devez exigence automatique pour votre Skype pour les clients d’entreprise sans DNS split-brain, vous donc ces options :
  
- **Objets de stratégie de groupe**
    
    Vous pouvez utiliser des objets de stratégie de groupe (GPO) pour remplir le serveur avec les valeurs correctes.
    
    > [!NOTE]
    > Cette option ne permet pas d’autoriser la configuration automatique, mais elle automatise la configuration manuelle. Si cette approche est utilisée, les enregistrements SRV associés à la configuration automatique ne sont pas obligatoires. 
  
- **Zone interne correspondante**
    
    Vous devrez créer une zone dans votre DNS interne qui correspond à la zone DNS externe (par exemple, contoso.com), puis créez DNS A (et AAAA si vous utilisez l’adressage IPv6) les enregistrements qui correspondent à la Skype pour le pool Business Server utilisé pour automatique configuration.
    
    Par exemple, si vous disposez d’un utilisateur hébergé sur pool01.contoso.net, mais que les signes dans Skype pour l’entreprise en tant que bob@contoso.com, créer une zone DNS interne nommée contoso.com et qu’il vous devez créer un DNS A (et AAAA si IPv6 adressage utilisé) enregistrement pool01.contoso.com.
    
- **Repérage de la zone interne**
    
    Si la création d’une zone complète dans votre DNS interne n’est pas envisageable pour vous, vous pouvez créer des zones repère (dédiées) qui correspondent aux enregistrements SRV requis pour la configuration automatique, et renseigner ces zones à l’aide de dnscmd.exe. Dnscmd.exe est obligatoire car l’interface utilisateur DNS ne prendra pas en charge la création de zones repère.
    
    Par exemple, si votre domaine SIP est contoso.com et que vous disposez d’un pool frontal appelé pool01 qui contient deux serveurs frontaux, vous devez les zones suivantes de repère et des enregistrements A dans votre DNS interne :
    
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
> Vous verrez le pool frontal que nom de domaine complet s’affiche à deux reprises, mais avec deux adresses IP. C’est parce que l’équilibrage de charge DNS est utilisé. Si matérielle est utilisé, il ne serait une entrée de pool frontal unique. 
  
> [!NOTE]
> En outre, les valeurs de nom de domaine complet du pool frontal modifier entre les exemples de contoso.com et fabrikam.com, mais les adresses IP restent les mêmes. C’est parce que les utilisateurs qui vous connectez depuis un domaine SIP utiliseront le même pool frontal pour la configuration automatique. 
  
## <a name="dns-disaster-recovery"></a>DNS disaster recovery
<a name="DNSDR"> </a>

Pour configurer DNS pour rediriger Skype pour le trafic web Business Server à vos sites de basculement et de récupération d’urgence (DR), vous devez utiliser un fournisseur de DNS qui prend en charge GeoDNS. Vous pouvez configurer vos enregistrements DNS pour prendre en charge de la récupération d’urgence, afin que les fonctionnalités qui utilisent les services web continuent même si un pool frontal entier tombe en panne. Cette fonctionnalité DR prend en charge les URL simples de découverte automatique, de réunion et de rendez-vous.
  
Vous définissez et configurez des enregistrements d’hôte DNS A (AAAA en cas d’utilisation d’IPv6) supplémentaires pour la résolution interne et externe des services web au niveau de votre fournisseur GeoDNS. Les détails suivants supposent l’existence de pools associés et géographiquement dispersés, et le fait que GeoDNS est pris en charge par votre fournisseur **avec**DNS round-robin **ou** qu’il est configuré de façon à utiliser Pool1 comme pool principal et à basculer vers Pool2 en cas de perte de communication ou de défaillance matérielle.
  
Tous les enregistrements DNS dans ce tableau sont des exemples.
  
|**Enregistrement GeoDNS**|**Enregistrements de pool**|**Enregistrements CNAME**|**Paramètres DNS (sélectionnez une option)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à int.geolb.contoso.com à la conférence  <br/>   <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisez le principal, se connecter au secondaire en cas de défaillance  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à ext.geolb.contoso.com à la conférence  <br/>   <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à int.geolb.contoso.com à la conférence   <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à ext.geolb.contoso.com à la conférence  <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à int.geolb.contoso.com à la conférence   <br/>   <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à ext.geolb.contoso.com à la conférence  <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à int.geolb.contoso.com à la conférence   <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com à ext.geolb.contoso.com à la conférence   <br/>  <br/> |Round Robin entre pools  <br/> **SOIT** <br/> Utilisation du principal, connexion au secondaire en cas de défaillance  <br/> |
   
## <a name="dns-load-balancing"></a>Équilibrage de charge DNS
<a name="DNSLB"> </a>

L’équilibrage de charge DNS est généralement mis en œuvre au niveau de l’application. L’application (par exemple, un client exécutant Skype pour les entreprises), essaie de se connecter à un serveur dans un pool en se connectant à une des adresses IP retournées par le DNS A et AAAA (si l’adressage IPv6 est utilisé) enregistrent la requête pour le nom de domaine complet du pool.
  
Par exemple, s’il existe trois serveurs frontaux dans un pool appelé pool01.contoso.com, suivantes qui se passerait :
  
- Les clients Skype pour les entreprises en cours d’exécution de requête DNS pour pool01.contoso.com. La requête renvoie trois adresses IP et les met dans le cache comme suit (pas nécessairement dans cet ordre) :
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Le client essaie d’établir une connexion TCP à l’une des adresses IP. En cas d’échec, il essayera l’adresse IP suivante qu’il a mise en cache de cette liste.
    
- Si la connexion TCP aboutit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool1.contoso.com.
    
- Si le client essaie toutes les mises en cache des entrées sans connexion réussie, l’utilisateur reçoit une notification qu’aucun serveur exécutant Skype pour Business Server n’est disponibles pour le moment.
    
> [!NOTE]
> L’équilibrage de charge DNS est différent du tourniquet (round robin) DNS (DNS RR), qui fait généralement référence à l’équilibrage de charge en s’appuyant sur DNS pour donner un ordre d’adresses IP différent pour les serveurs dans votre pool. En règle générale, DNS RR active la distribution de la charge, mais il ne vous permettra pas d’activer le basculement. Par exemple, si la connexion à l’adresse IP renvoyée par votre requête DNS (ou AAAA dans un scénario IPv6) échoue, cette connexion échouera. Cela rend DNS RR moins fiable que l’équilibrage de charge DNS. Vous pouvez toujours utiliser DNS RR conjointement avec l’équilibrage de charge DNS si vous avez besoin de procéder ainsi. 
  
Vous utilisez l’équilibrage de charge DNS pour :
  
- Équilibrez la charge serveur à serveur SIP pour les serveurs de périphérie.
    
- équilibrer la charge des applications des services d’applications de communications unifiées (UCAS) telles que le Standard automatique de conférence, Response Group et le parcage d’appel ;
    
- empêcher les nouvelles connexions aux applications UCAS (également appelé « drainage ») ;
    
- Équilibrez la charge tout le trafic de client à serveur entre les clients et serveurs de périphérie.
    
Vous ne pouvez pas utiliser l’équilibrage de charge DNS pour :
  
- Trafic web client à serveur pour vos serveurs frontaux ou un directeur.
    
Pour accéder à un peu plus détaillées sur le mode de sélection d’un enregistrement DNS SRV lorsque plusieurs enregistrements DNS sont retournés par une requête, le service Edge d’accès toujours sélectionne l’enregistrement par ordre de priorité numérique et, si un séparateur de jonction n’est nécessaire, le poids numérique le plus élevé. Cela est cohérent avec la [documentation de Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Ainsi, par exemple, si votre premier enregistrement DNS SRV a un poids de 20 et une priorité de 40, et votre deuxième enregistrement SRV DNS a une valeur de 10 et une priorité de 50, le premier enregistrement va être choisi car il a la priorité basse de 40. La priorité vient toujours d’abord, et c’est l’hôte qu’un client va cibler le premier. Que se passe-t-il s’il existe deux cibles ayant la même priorité ? 
  
Dans ce cas, le poids vient en considération. Les poids les plus élevés doivent recevoir une forte probabilité d’être sélectionnés dans ces conditions. Les administrateurs DNS doivent utiliser un poids égal à 0 quand il n’y a aucune sélection de serveur à effectuer. En présence d’enregistrements contenant des poids supérieurs à 0, les enregistrements de poids nul ont une chance très faible d’être sélectionnés.
  
Alors, que se passe-t-il si plusieurs SRV DNS de même priorité et de même poids s’enregistrent comme renvoyés ? Dans ce cas, le serveur Edge d’accès service choisira l’enregistrement SRV obtenu à partir du serveur DNS premier.
  

