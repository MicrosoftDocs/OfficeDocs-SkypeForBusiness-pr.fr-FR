---
title: Edge exigences Server dans Skype pour Business Server
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
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Résumé : Découvrez les exigences pour les serveurs de périphérie de Skype pour Business Server.'
ms.openlocfilehash: eaa6c1ac5b1d014f6c2bb54a342dabd4c6388c2e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207159"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Edge exigences Server dans Skype pour Business Server
 
**Résumé :** Découvrez les exigences pour les serveurs de périphérie de Skype pour Business Server.
  
Beaucoup de planification et de préparation doit avoir lieu en dehors de la Skype pour environnement Business Server Edge Server lui-même. Dans cet article, nous allons examiner les préparations à effectuer dans l’environnement organisationnel, selon la liste ci-dessous :
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planification de la topologie
<a name="TopoPlan"> </a>

Skype pour les topologies de serveur de périphérie Business Server sont en mesure d’utiliser :
  
- des adresses IP publiques routables ;
    
- des adresses IP privées non routables si la conversion d’adresses réseau (NAT) **symétrique** est utilisée.
    
> [!TIP]
> Votre serveur Edge peut être configuré pour utiliser une adresse IP unique avec des ports distincts pour chaque service, ou il peut utiliser des adresses IP distincts pour chaque service, mais vous pouvez utiliser le même port par défaut (qui, par défaut, TCP 443 sera). Vous trouverez plus d’informations dans la section consacrée aux exigences liées aux adresses IP, ci-dessous. 
  
Si vous sélectionnez des adresses IP privées non routables avec conversion d’adresses réseau, n’oubliez pas les points suivants :
  
- Vous devez utiliser des adresses IP privées routables sur les **trois** interfaces externes.
    
- Vous devez configurer la fonction de conversion d’adresses réseau (NAT) **symétrique** pour le trafic entrant et sortant. NAT symétrique est que le seul pris en charge NAT, vous pouvez utiliser avec Skype pour Business serveur Edge.
    
- Configurez la fonction de conversion d’adresses réseau (NAT) de manière à ne pas modifier les adresses source entrantes. A / V Edge service doit pouvoir recevoir l’adresse source entrante pour rechercher le chemin d’accès multimédia optimale.
    
- Vos serveurs Edge doivent être en mesure de communiquer entre eux à partir de leur public A / V Edge IP addresses. Votre pare-feu doit autoriser ce trafic.
    
- NAT peuvent **uniquement** être utilisés pour les serveurs Edge consolidé mis à l’échelle si vous utilisez l’équilibrage de charge DNS. Si vous utilisez l’équilibrage de charge matérielle, vous devez utiliser des adresses IP publiquement routables **sans** la fonction de conversion d’adresses réseau.
    
Vous n’aurez aucun problème de l’accès, les conférences Web et A / V Edge interfaces derrière un routeur ou un pare-feu d’adresses réseau symétrique pour unique et à l’échelle consolidée topologies de serveur Edge (à condition que vous n’utilisez pas l’équilibrage de charge matérielle).
  
### <a name="summary-of-edge-server-topology-options"></a>Résumé des options de topologie de serveur de transport Edge

Nous avons plusieurs options de topologie disponibles pour Skype pour les déploiements de serveur de périphérie Business Server :
  
- Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau
    
- Serveur Edge consolidé unique avec des adresses IP publiques
    
- Serveur Edge consolidé ajusté avec des adresses IP privées et la conversion d’adresses réseau
    
- Serveur Edge consolidé ajusté avec des adresses IP publiques
    
- Topologie Edge consolidée ajustée avec des équilibreurs de charge matérielle
    
Pour vous aider à choisir, le tableau ci-dessous contient un résumé des options à votre disposition pour chaque topologie :
  
|**Topologie**|**Haute disponibilité**|**Autres enregistrements DNS requis pour un serveur Edge externe dans le pool Edge ?**|**Basculement Edge pour Skype pour les sessions Business Server**|**Basculement Edge pour Skype pour les sessions de fédération Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Serveur Edge consolidé unique avec des adresses IP publiques  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Serveur Edge consolidé ajusté avec des adresses IP privées et de conversion d’adresses réseau (NAT) (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Yes&sup1 ;  <br/> |
|Serveur Edge consolidé ajusté avec des adresses IP publiques (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Yes&sup1 ;  <br/> |
|Topologie Edge consolidée ajustée avec des équilibreurs de charge matérielle  <br/> |Oui  <br/> |Non (un enregistrement DNS A par VIP)  <br/> |Oui  <br/> |Oui  <br/> |
   
&sup1 ; Le basculement des utilisateurs distants de messagerie unifiée Exchange (MU) à l’aide de l’équilibrage de charge DNS requiert Exchange 2013 ou version ultérieure.
  
### <a name="ip-address-requirements"></a>Exigences d’adresse IP

Sur un niveau fondamental, trois services besoin des adresses IP ; Accéder aux services Edge, service Edge de conférence Web et A / V Edge service. Vous avez la possibilité d’utiliser trois adresses IP, à savoir une pour chacun des services, ou d’en utiliser une seule et de placer chaque service sur un port différent (pour plus d’informations sur cette procédure, reportez à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)). Pour un environnement de serveur Edge consolidé unique, c’est à peu près tout ce qu’il y a à faire.
  
> [!NOTE]
> Comme indiqué ci-dessus, vous pouvez choisir d’avoir une adresse IP pour les trois services et de les exécuter sur différents ports, mais nous ne vous recommandons pas cette solution. Si vos clients ne peuvent pas accéder aux ports de remplacement que vous utiliseriez dans ce scénario, ils ne peuvent pas non plus accéder aux fonctionnalités complètes de votre environnement Edge. 
  
Les choses pouvant être un peu plus complexes avec topologies consolidées ajustées, examinons quelques tableaux reprenant les exigences d’adresses IP, en gardant à l’esprit que les principaux points devant orienter la sélection de la topologie sont la haute disponibilité et l’équilibrage de la charge. Des besoins de haute disponibilité peuvent influencer votre choix d’équilibrage de charge (nous approfondirons ce point après les tableaux).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Exigences d’adresses IP pour la topologie Edge consolidée ajustée (adresse IP par rôle)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses IP requises pour l’équilibrage de charge DNS**|**Nombre d’adresses IP requises pour l’équilibrage de charge matérielle**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 par adresse IP virtuelle) + 6  <br/> |
|3  <br/> |9  <br/> |3 (1 par adresse IP virtuelle) + 9  <br/> |
|4  <br/> |12  <br/> |3 (1 par adresse IP virtuelle) + 12  <br/> |
|5  <br/> |15  <br/> |3 (1 par adresse IP virtuelle) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Exigences d’adresses IP pour la topologie Edge consolidée ajustée (adresse IP unique pour tous les rôles)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses IP requises pour l’équilibrage de charge DNS**|**Nombre d’adresses IP requises pour l’équilibrage de charge matérielle**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 par adresse IP virtuelle) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 par adresse IP virtuelle) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 par adresse IP virtuelle) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 par adresse IP virtuelle) + 5  <br/> |
   
Examinons d’autres aspects à prendre en compte lors de la planification.
  
- **Haute disponibilité**: Si vous avez besoin d’une haute disponibilité dans votre déploiement, vous devez déployer au moins deux serveurs de périphérie dans un pool. Il est important de noter qu’un seul pool Edge prendra en charge jusqu'à 12 serveurs de périphérie (même si le Générateur de topologie vous permettra d’ajouter jusqu'à 20, qui n’a pas testé ou pris en charge, nous vous recommandons de que ne pas procéder). Si vous avez besoin de plus de 12 serveurs de périphérie, vous devez créer des pools de serveurs Edge supplémentaires pour les.
    
- **L’équilibrage de charge matérielle**: nous vous recommandons d’équilibrage de la plupart des scénarios de charge DNS. L’équilibrage de charge matérielle est également prise en charge, bien sûr, mais en particulier est nécessaire pour un seul scénario sur l’équilibrage de charge DNS :
    
  - Accès externe à Exchange 2007 ou Exchange 2010 (sans le SP) de messagerie unifiée.
    
- **Équilibrage de charge DNS**: pour la messagerie unifiée Exchange 2010 SP1 et plus récent sont en mesure de prendre en charge par l’équilibrage de charge DNS. Notez que si vous avez besoin accéder avec charge DNS équilibrée pour une version antérieure d’Exchange, elle fonctionne, mais tout le trafic pour ce est dirigés vers le premier serveur du pool, et s’il n’est pas disponible, ce trafic échoue par la suite.
    
    Équilibrage de charge DNS est également recommandé si vous êtes fédération avec des sociétés à l’aide de :
- Skype pour Business Server 2015 :
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office O365
- Skype pour Business Server 2019 :
    - Lync Server 2013
    - Skype Entreprise Server 2015
    - Microsoft Office 365.
    
## <a name="dns-planning"></a>Planification DNS
<a name="DNSPlan"> </a>

Lorsqu’il s’agit Skype pour le déploiement du serveur de périphérie Business Server, il est essentiel pour préparer correctement DNS. Si les enregistrements corrects sont en place, le déploiement est beaucoup plus simple. Nous espérons que vous avez sélectionné une topologie dans la section ci-dessus, car nous allons présenter, puis répertorier plusieurs tableaux qui décrivent les enregistrements DNS pour les scénarios illustrés. Nous également aurez quelques [avancée Edge Server DNS planification de Skype pour Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) pour la lecture plus approfondie, si nécessaire.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Enregistrements DNS pour unique consolidée des scénarios de serveur de transport Edge

Ces paramètres seront les enregistrements DNS que vous aurez besoin pour un serveur Edge à l’aide d’un accès public unique IP ou IP privé avec NAT. Comme il s’agit d’exemples de données, nous allons vous donner des exemples d’adresses IP pour que vous puissiez élaborer plus facilement vos propres entrées :
  
- Carte réseau interne : 172.25.33.10 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant Skype pour les clients Business Server ou Microsoft Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Adresses IP publiques :
    
  - Serveur Edge d’accès : 131.107.155.10 (il s’agit du principal, avec la passerelle par défaut définie sur votre routeur public, ex : 131.107.155.1)
    
  - Serveur Edge de conférence Web : 131.107.155.20 (secondaire)
    
  - A / V Edge : 131.107.155.30 (secondaire)
    
  Conférence Web et A / adresses IP publiques V Edge sont des adresses IP supplémentaires (secondaires) dans la section des propriétés de protocole Internet Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés dans Options avancées Windows Server.
    
  - Adresses IP privées :
    
  - Serveur Edge d’accès : 10.45.16.10 (il s’agit du principal, avec la passerelle par défaut définie sur votre routeur, ex : 10.45.16.1)
    
  - Serveur Edge de conférence Web : 10.45.16.20 (secondaire)
    
  - A / V Edge : et 10.45.16.30 (secondaire)
    
Conférence Web et A / adresses IP publiques V Edge sont des adresses IP supplémentaires (secondaires) dans la section des propriétés de protocole Internet Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés dans Options avancées Windows Server.
  
> [!TIP]
>Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Nous ne recommandons pas cette car puis vous aurez besoin de faire la distinction entre les trois services à l’aide des ports distincts (que vous pouvez faire dans Skype pour Business Server), mais il existe certains pare-feu qui peut-être bloquer les ports de substitution. Pour plus d’informations à ce sujet, reportez-vous à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan).
    
- Vous pouvez avoir trois cartes réseau externe au lieu d’une, et affecter un des services d’adresses IP à chacune d’elles. Pourquoi ? Vous séparez ainsi les services. Par conséquent, si un problème survient, il sera plus facile à résoudre et cela permettra éventuellement aux autres services de continuer à fonctionner pendant que cherchez une solution.
    
|**Emplacement**|**Type**|**Port**|**Enregistrement FQDN ou DNS**|**Adresse IP ou FQDN**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sip.contoso.com  <br/> |**publics :** 131.107.155.10 <br/> **privé :** 10.45.16.10 <br/> |Une interface externe de votre service Edge d’accès. Vous aurez besoin un pour chaque domaine SIP avec Skype pour les utilisateurs professionnels.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |webcon.contoso.com  <br/> |**publics :** 131.107.155.20 <br/> **privé :** 10.45.16.20 <br/> |Une interface externe de votre service Edge de conférence Web.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |av.contoso.com  <br/> |**publics :** 131.107.155.30 <br/> **privé :** et 10.45.16.30 <br/> |Une interface externe pour votre A / V Edge service.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Une interface externe de votre service Edge d’accès. Cet enregistrement SRV est requis pour Skype pour les clients Business Server, Lync Server 2013 et Lync Server 2010 fonctionner en externe. Vous aurez besoin un pour chaque domaine avec Skype pour les utilisateurs professionnels.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Une interface externe de votre service Edge d’accès. Cet enregistrement SRV est requis pour permettre la découverte DNS automatique de partenaires fédérés appelés domaines SIP (Session Initiation Protocol) autorisés. Vous aurez besoin un pour chaque domaine avec Skype pour les utilisateurs professionnels.  <br/> |
|DNS interne  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |L’interface interne de votre serveur Edge consolidé.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Enregistrements DNS pour les scénarios de serveur Edge de matériel et de DNS mis à l’échelle

Ces paramètres seront les enregistrements DNS que vous aurez besoin pour un serveur Edge à l’aide d’un accès public unique IP ou IP privé avec NAT. Comme il s’agit d’exemples de données, nous allons vous donner des exemples d’adresses IP pour que vous puissiez élaborer plus facilement vos propres entrées :
  
- Carte réseau interne :
    
  - Nœud 1 : 172.25.33.10 (aucune passerelle par défaut affectée)
    
  - Nœud 2 : 172.25.33.11 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant Skype pour les clients Business Server ou Microsoft Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Nœud 1
    
     - Adresses IP publiques :
    
        - Serveur Edge d’accès : 131.107.155.10 (il s’agit du principal, avec la passerelle par défaut définie sur votre routeur public, ex : 131.107.155.1)
    
        - Serveur Edge de conférence Web : 131.107.155.20 (secondaire)
    
        - A / V Edge : 131.107.155.30 (secondaire)
    
          Conférence Web et A / adresses IP publiques V Edge sont des adresses IP supplémentaires (secondaires) dans la section des propriétés de protocole Internet Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés dans Options avancées Windows Server.
    
    - Adresses IP privées :
    
         - Serveur Edge d’accès : 10.45.16.10 (il s’agit du principal, avec la passerelle par défaut définie sur votre routeur, ex : 10.45.16.1)
    
         - Serveur Edge de conférence Web : 10.45.16.20 (secondaire)
    
         - A / V Edge : et 10.45.16.30 (secondaire)
    
      Conférence Web et A / adresses IP publiques V Edge sont des adresses IP supplémentaires (secondaires) dans la section des propriétés de protocole Internet Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés dans Options avancées Windows Server.
    
  - Nœud 2
    
    - Adresses IP publiques :
    
      - Serveur Edge d’accès : 131.107.155.11 (il s’agit du principal, avec la passerelle par défaut définie sur votre routeur public, ex : 131.107.155.1)
    
      - Serveur Edge de conférence Web : 131.107.155.21 (secondaire)
    
      - A / V Edge : et 131.107.155.31 (secondaire)
    
      Conférence Web et A / adresses IP publiques V Edge sont des adresses IP supplémentaires (secondaires) dans la section des propriétés de protocole Internet Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés dans Options avancées Windows Server.
    
  - Adresses IP privées :
    
    - Serveur Edge d’accès : 10.45.16.11 (il s’agit du principal, avec la passerelle par défaut définie sur votre routeur, ex : 10.45.16.1)
    
    - Serveur Edge de conférence Web : 10.45.16.21 (secondaire)
    
    - A / V Edge : et 10.45.16.31 (secondaire)
    
      Conférence Web et A / adresses IP publiques V Edge sont des adresses IP supplémentaires (secondaires) dans la section des propriétés de protocole Internet Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés dans Options avancées Windows Server.
    
Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Nous ne recommandons pas cette car puis vous aurez besoin de faire la distinction entre les trois services à l’aide des ports distincts (que vous pouvez faire dans Skype pour Business Server), mais il existe certains pare-feu qui peut-être bloquer les ports de substitution. Pour plus d’informations à ce sujet, reportez-vous à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan).
    
- Vous pouvez avoir trois cartes réseau externe au lieu d’une, et affecter un des services d’adresses IP à chacune d’elles. Pourquoi ? Vous séparez ainsi les services. Par conséquent, si un problème survient, il sera plus facile à résoudre et cela permettra éventuellement aux autres services de continuer à fonctionner pendant que cherchez une solution.
    
|**Emplacement**|**Type**|**Port**|**Enregistrement FQDN ou DNS**|**Adresse IP ou FQDN**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sip.contoso.com  <br/> |**public :** 131.107.155.10 et 131.107.155.11 <br/> **privé :** 10.45.16.10 et 10.45.16.11 <br/> |Une interface externe de votre service Edge d’accès. Vous aurez besoin un pour chaque domaine SIP avec Skype pour les utilisateurs professionnels.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |webcon.contoso.com  <br/> |**public :** 131.107.155.20 et 131.107.155.21 <br/> **privé :** 10.45.16.20 et 10.45.16.21 <br/> |Une interface externe de votre service Edge de conférence Web.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |av.contoso.com  <br/> |**public :** 131.107.155.30 et et 131.107.155.31 <br/> **privé :** et 10.45.16.30 et et 10.45.16.31 <br/> |Une interface externe pour votre A / V Edge service.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Une interface externe de votre service Edge d’accès. Cet enregistrement SRV est requis pour Skype pour les clients Business Server, Lync Server 2013 et Lync Server 2010 fonctionner en externe. Vous aurez besoin un pour chaque domaine avec Skype pour les entreprises.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Une interface externe de votre service Edge d’accès. Cet enregistrement SRV est requis pour permettre la découverte DNS automatique de partenaires fédérés appelés domaines SIP (Session Initiation Protocol) autorisés. Vous aurez besoin un pour chaque domaine avec Skype pour les entreprises.  <br/> |
|DNS interne  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 et 172.25.33.11  <br/> |L’interface interne de votre serveur Edge consolidé.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Enregistrement DNS pour la fédération (tous les scénarios)

|**Emplacement**|**Type**|**Port**|**FQDN**|**Enregistrement d’hôte FQDN**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |L’interface externe Edge d’accès SIP nécessaire pour la découverte automatique DNS. Utilisée par vos autres partenaires de fédération potentiels. Elle est également connue sous le nom de « domaines SIP autorisés ». Vous aurez besoin d’une de ces pour chaque domaine SIP avec Skype pour les utilisateurs professionnels.  <br/><br/> **Remarque :** Vous devez cet enregistrement SRV pour la mobilité et les échanges de notifications push. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Enregistrements DNS pour le protocole XMPP (Extensible Messaging et Presence Protocol)

|**Emplacement**|**Type**|**Port**|**FQDN**|**Adresse IP ou enregistrement d’hôte FQDN**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |L’interface proxy XMPP sur votre service Edge d’accès ou d’un pool de serveurs Edge. Vous devez reprenez cette étape pour tous les domaines SIP internes avec Skype pour les utilisateurs d’entreprise du serveur, où les contacts avec les contacts XMPP est autorisé par le biais de :  <br/> • une stratégie globale  <br/> • une stratégie de site où l’utilisateur de l’extension  <br/> • une stratégie utilisateur de la Skype pour Business Server activé utilisateur  <br/> une stratégie XMPP autorisée doit également être configurée dans la stratégie des utilisateurs fédérés XMPP.  <br/> |
|DNS externe  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Adresse IP du service Edge d’accès sur le serveur Edge ou le pool de serveurs Edge qui héberge votre service Proxy XMPP  <br/> |Il pointe vers le service Edge d’accès sur le serveur Edge ou le pool de serveurs Edge qui héberge le service Proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).  <br/> |
   
> [!NOTE]
> XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Pour plus d’informations, voir [la fédération XMPP de migration](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

## <a name="certificate-planning"></a>Planification de certificat
<a name="CertPlan"> </a>

Skype pour Business Server utilise des certificats pour les communications sécurisées, chiffrées entre les serveurs et du serveur au client. Comme vous devez vous y attendre, les enregistrements DNS de vos certificats doivent correspondre au nom de sujet (SN) et à l’autre nom de sujet (SAN) de vos certificats. Vous accéderez maintenant fonctionner, à l’issue de la phase de planification, afin de vous assurer que vous avez le droit domaine complets enregistré dans DNS pour le nom de sujet et entrées d’autres noms de sujet de vos certificats.
  
Nous aborderons séparément les besoins de certificats internes et externes, puis examinerons un tableau qui présente la configuration requise pour les deux.
  
### <a name="external-certificates"></a>Certificats externes

Au minimum, le certificat assigné à votre serveur de périphérie des interfaces externe vous devrez être fournie par une autorité de certification publique (CA). Nous ne pouvons vous recommandons d’une autorité de certification spécifique pour vous, mais nous disposons d’une liste d’autorités de certification, [partenaires de certificat de Communications unifiées](https://support.microsoft.com/en-us/kb/929395) que vous pouvez effectuer un aperçu pour voir si votre autorité de certification par défaut est répertoriée.
  
Quand aurez-vous besoin d’envoyer une demande à une autorité de certification pour ce certificat public et comment procéder ? Il existe différentes façons de faire :
  
- Vous pouvez accéder par le biais de l’installation de Skype pour Business Server, puis le déploiement du serveur de transport Edge. Le Skype pour l’Assistant de déploiement Business Server aura une étape pour générer une demande de certificat, vous pouvez envoyer à votre autorité de certification sélectionnée.
    
- Vous pouvez également utiliser les commandes Windows PowerShell pour générer cette demande, si ce n’est plus insérée avec vos besoins ou la stratégie de déploiement.
    
- Enfin, votre autorité de certification peut avoir leur propre processus de soumission, qui peut également inclure Windows PowerShell ou une autre méthode. Dans ce cas, vous devrez, outre les informations figurant dans le présent document, à sa documentation.
    
Une fois que vous avez obtenu le certificat, vous devrez continuez et attribuer à ces services dans Skype pour Business Server :
  
- Interface de service Access Edge
    
- Interface de service du serveur Edge de conférence Web
    
- Service d’authentification audio/vidéo (ne pas confondre avec A / V Edge service, que n’utiliser un certificat pour chiffrer les flux audio et vidéo)
    
> [!IMPORTANT]
> Tous les serveurs Edge (s’ils appartiennent au même pool de serveurs de périphérie) doit être le même certificat exact avec la même clé privée pour le service d’authentification du relais multimédia. 
  
### <a name="internal-certificates"></a>Certificats internes

Pour l’interface interne de serveur de transport Edge, vous pouvez utiliser un certificat public à partir d’une autorité de certification publique, ou un certificat émis par une autorité de certification interne de votre organisation. La chose à retenir sur le certificat interne est qu’il utilise une entrée SN et aucune entrée SAN, sans que vous ayez à se soucier SAN sur le certificat interne tout.
  
### <a name="required-certificates-table"></a>Tableau des certificats requis

Vous trouverez ici un tableau pour vous aider avec vos demandes. Les entrées FQDN indiquées ici sont fournies uniquement à titre d’exemples de domaines. Vous devrez introduire des demandes en fonction de vos propres domaines privés et publics. Voici un guide expliquant ce que nous avons utilisé :
  
- Contoso<span></span>.com : nom de domaine complet Public
    
- Fabrikam<span></span>.com : deuxième public nom de domaine complet (ajouté en tant qu’une démonstration de ce que demander si vous disposez de plusieurs domaines SIP)
    
- Contoso<span></span>.net : domaine interne
    
#### <a name="edge-certificate-table"></a>Tableau des certificats de serveur Edge

Quelle que soit la si vous effectuez un serveur Edge unique ou un pool de serveurs Edge, il s’agit de vous aurez besoin pour votre certificat :
  
|**Composant**|**Nom du sujet (SN)**|**Autres noms de sujets (SAN)/ordre**|**Remarques**|
|:-----|:-----|:-----|:-----|
|Serveur Edge externe  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Il s’agit du certificat que vous devez demander à une autorité de certification publique. Il devra être affecté aux interfaces Edge externes pour les éléments suivants :<br/> • Serveur Edge d’accès  <br/> • Edge de conférence web  <br/> • L’authentification audio/vidéo  <br/> <br/>La bonne nouvelle est que SAN sont automatiquement ajoutées à votre demande de certificat, et par conséquent, votre certificat après vous envoyer la demande, selon ce que vous avez définis pour ce déploiement dans le Générateur de topologie. Vous devrez uniquement ajouter des entrées SAN pour les autres domaines SIP (Session Initiation Protocol) ou les autres entrées à prendre en charge. Pourquoi sip.contoso.com est-il répliqué dans cette instance ? Cela se produit aussi automatiquement et c’est nécessaire pour que tout fonctionne correctement.  <br/><br/> **Remarque :** Ce certificat peut également être utilisé pour la connectivité de messagerie instantanée publique. Vous n’avez pas besoin de faire quoi que ce soit différemment à son sujet, mais dans les versions précédentes de cette documentation, il était répertorié en tant que tableau distinct, ce qui n’est plus le cas maintenant. <br/> |
|Interface interne du serveur Edge  <br/> |sfbedge.contoso.com  <br/> |S.O.  <br/> |Vous pouvez obtenir ce certificat auprès d’une autorité de certification publique ou d’une autorité de certification interne. Il devra contenir l’utilisation améliorée de la clé du serveur, et vous devez l’affecter à l’interface Edge interne.  <br/> |
   
Si vous avez besoin d’un certificat pour le protocole XMPP (Extensible Messaging and Presence Protocol), ce dernier est identique aux entrées du tableau du serveur Edge externe ci-dessus, mais comporte les deux nouvelles entrées SAN suivantes :
  
- XMPP. <span> </span>contoso<span></span>.com
    
- \*.Contoso<span></span>.com
    
N’oubliez pas qu’actuellement XMPP est uniquement pris en charge dans Skype pour Business Server Google Talk, si vous souhaitez ou que vous devez l’utiliser pour tout autre élément, vous devez vérifier que fonctionnalités avec le fournisseur tiers impliqué.
  
## <a name="port-and-firewall-planning"></a>Planification des ports et des pare-feu
<a name="PortFirewallPlan"> </a>

Votre planification pour les ports et les pare-feu pour Skype pour Business Server Edge Server déploiements peuvent enregistrer les jours, voire des semaines de dépannage et une contrainte. Par conséquent, nous allons répertorier des tableaux indiquant notre utilisation des protocoles et les ports, entrants ou sortants, à ouvrir, pour des scénarios de conversion d’adresses réseau (NAT) et des adresses IP publiques. Nous aurons également des tableaux distincts pour les scénarios d’équilibrage de charge matérielle et de plus amples conseils à ce sujet. Pour plus d’informations à partir de là, nous avons également quelques [scénarios de serveur de transport Edge dans Skype pour Business Server](scenarios.md) , vous pouvez extraire des problèmes de votre déploiement particulier.
  
### <a name="general-protocol-usage"></a>Utilisation générale des protocoles

Avant de consulter les tableaux récapitulatifs pour les pare-feu internes et externes, consultons également le tableau suivant :
  
|**Transport audio/vidéo**|**Utilisation**|
|:-----|:-----|
|UDP  <br/> |Protocole de couche transport par défaut pour les données audio et vidéo.  <br/> |
|TCP  <br/> |Protocole de couche transport de secours pour les données audio et vidéo.  <br/> Le protocole de couche de transport requis pour le partage d’applications à Skype pour Business Server, Lync Server 2013 et Lync Server 2010.  <br/> Le protocole de couche de transport requis pour le transfert de fichier à Skype pour Business Server, Lync Server 2013 et Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiendront des informations pour les utilisateurs utilisant des adresses IP privées avec conversion d’adresses réseau, ainsi que pour les personnes utilisant des adresses IP publiques. Cela couvrira toutes les permutations dans notre section sur les [scénarios de serveur de transport Edge dans Skype pour Business Server](scenarios.md) .
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non pris en charge dans Skype Business Server 2019 |TCP  <br/> |5269  <br/> |Indifférente  <br/> |Service Proxy XMPP (partage une adresse IP avec le service Edge d’accès  <br/> |Le service Proxy XMPP accepte le trafic provenant des contacts XMPP dans les fédérations XMPP définies.  <br/> |
|Accès/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Indifférente  <br/> |Vérification et extraction de la liste de révocation de certificats.  <br/> |
|Accès/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Indifférente  <br/> |Requête DNS sur TCP.  <br/> |
|Accès/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Indifférente  <br/> |Requête DNS sur UDP  <br/> |
|Accès/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Trafic SIP client vers serveur pour l’accès des utilisateurs externes.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifférente  <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Indifférente  <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Conférence web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**IP privées utilisant NAT :** Service Edge de conférence Web serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du côté serveur Edge de conférence Web service <br/> |Données multimédias de conférence Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privées utilisant NAT :** Edge Server A / V Edge service <br/> **Les adresses IP publiques :** Edge Server A / V Edge adresse IP publique du service <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privées utilisant NAT :** Edge Server A / V Edge service <br/> **Les adresses IP publiques :** Edge Server A / V Edge adresse IP publique du service <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privées utilisant NAT :** Edge Server A / V Edge service <br/> **Les adresses IP publiques :** Edge Server A / V Edge adresse IP publique du service <br/> |Indifférente  <br/> |Le port sortant 3478 est :  <br/> • Permet de déterminer la version du serveur de transport Edge par Skype pour Business Server il communique avec.  <br/> • Utilisé pour le trafic multimédia entre les serveurs de périphérie.  <br/> • Requis pour la fédération avec Lync Server 2010.  <br/> • Nécessaire si plusieurs pools Edge sont déployés dans votre organisation.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |**IP privées utilisant NAT :** Edge Server A / V Edge service <br/> **Les adresses IP publiques :** Edge Server A / V Edge adresse IP publique du service <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**IP privées utilisant NAT :** Edge Server A / V Edge service <br/> **Les adresses IP publiques :** Edge Server A / V Edge adresse IP publique du service <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privées utilisant NAT :** Edge Server A / V Edge service <br/> **Les adresses IP publiques :** Edge Server A / V Edge adresse IP publique du service <br/> |Indifférente  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port interne

|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des opérations ci-dessous exécutant le service de passerelle XMPP :  <br/> • Serveur frontal  <br/> • Le pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic XMPP sortant provenant de votre service de passerelle XMPP en cours d’exécution sur votre pool frontal ou serveur frontal.  <br/> **Remarque :** XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Pour plus d’informations, voir [la fédération XMPP de migration](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Pool directeur  <br/> • Serveur frontal  <br/> • Le pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic SIP sortant de votre directeur, le pool directeur, un pool frontal ou serveur frontal à l’interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interne du serveur Edge  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Pool directeur  <br/> • Serveur frontal  <br/> • Le pool frontal  <br/> |Trafic SIP entrant vers votre pool directeur, directeur, serveur frontal ou Front End pool à partir de l’interface interne du serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal  <br/>  dans votre pool frontal <br/> |Interface interne du serveur Edge  <br/> |Trafic de conférence Web à partir de votre serveur frontal ou chaque serveur frontal (si vous avez un pool frontal) pour l’interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Le pool frontal  <br/> • Les Survivable Branch Appliance à l’aide de ce serveur Edge  <br/> • N’importe quel serveur Survivable Branch Server à l’aide de ce serveur Edge  <br/> |Interface interne du serveur Edge  <br/> |L’authentification a / utilisateurs V à partir de votre pool frontal ou serveur frontal, ou votre Survivable Branch Appliance ou Survivable Branch Server, à l’aide de votre serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour / le transfert multimédia entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou serveur Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès de secours a / le transfert multimédia entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou Survivable Branch Server, si la communication UDP ne fonctionne pas. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Indifféremment :  <br/> • Serveur frontal qui contient le magasin Central de gestion  <br/> • Le pool frontal qui contient le magasin Central de gestion  <br/> |Interface interne du serveur Edge  <br/> |Réplication des modifications depuis le magasin Central de gestion vers votre serveur Edge.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour les applets de commande Business Server Management Shell et le Service de journalisation centralisée, ligne de commande ClsController (ClsController.exe) ou commandes de l’agent (ClsAgent.exe) et collection de journal.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour les applets de commande Business Server Management Shell et le Service de journalisation centralisée, ligne de commande ClsController (ClsController.exe) ou commandes de l’agent (ClsAgent.exe) et collection de journal.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour les applets de commande Business Server Management Shell et le Service de journalisation centralisée, ligne de commande ClsController (ClsController.exe) ou commandes de l’agent (ClsAgent.exe) et collection de journal.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Programmes d’équilibrage de charge matérielle pour les tableaux des ports Edge

Nous consacrons une section propre aux équilibreurs de charge matérielle et aux ports Edge, car les choses sont un peu plus complexes avec le matériel supplémentaire. Reportez-vous aux tableaux ci-dessous pour obtenir des conseils pour ce scénario particulier :
  
#### <a name="external-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiendront des informations pour les utilisateurs utilisant des adresses IP privées avec conversion d’adresses réseau, ainsi que pour les personnes utilisant des adresses IP publiques. Cela couvrira toutes les permutations dans notre section sur les [scénarios de serveur de transport Edge dans Skype pour Business Server](scenarios.md) .
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accès/HTTP  <br/> |TCP  <br/> |80  <br/> |Adresse IP publique du bord serveur Edge d’accès service  <br/> |Indifférente  <br/> |Vérification et extraction de la liste de révocation de certificats.  <br/> |
|Accès/DNS  <br/> |TCP  <br/> |53  <br/> |Adresse IP publique du bord serveur Edge d’accès service  <br/> |Indifférente  <br/> |Requête DNS sur TCP.  <br/> |
|Accès/DNS  <br/> |UDP  <br/> |53  <br/> |Adresse IP publique du bord serveur Edge d’accès service  <br/> |Indifférente  <br/> |Requête DNS sur UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edge Server A / V Edge adresse IP du service  <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edge Server A / V Edge adresse IP publique du service  <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edge Server A / V Edge adresse IP publique du service  <br/> |Indifférente  <br/> |Le port sortant 3478 est :  <br/> • Permet de déterminer la version du serveur de transport Edge par Skype pour Business Server il communique avec.  <br/> • Utilisé pour le trafic multimédia entre les serveurs de périphérie.  <br/> • Requis pour la fédération.  <br/> • Nécessaire si plusieurs pools Edge sont déployés dans votre organisation.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Edge Server A / V Edge adresse IP publique du service  <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |Edge Server A / V Edge adresse IP publique du service  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Edge Server A / V Edge adresse IP publique du service  <br/> |Indifférente  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port interne

|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des opérations ci-dessous exécutant le service de passerelle XMPP :  <br/> • Serveur frontal  <br/> • Le pool frontal adresse IP virtuelle qui exécute le service de passerelle XMPP  <br/> |Interface interne du serveur Edge  <br/> |Trafic XMPP sortant provenant de votre service de passerelle XMPP en cours d’exécution sur votre pool frontal ou serveur frontal.  <br/><br/> **Remarque :** XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Pour plus d’informations, voir [la fédération XMPP de migration](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Indifféremment :  <br/> • Serveur frontal qui contient le magasin Central de gestion  <br/> • Le pool frontal qui contient le magasin Central de gestion  <br/> |Interface interne du serveur Edge  <br/> |Réplication des modifications depuis le magasin Central de gestion vers votre serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal dans votre pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic de conférence Web à partir de votre serveur frontal ou chaque serveur frontal (si vous avez un pool frontal) pour l’interface interne du serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal dans votre pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour / le transfert multimédia entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou serveur Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal dans votre pool  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès de secours a / le transfert multimédia entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou Survivable Branch Server, si la communication UDP ne fonctionne pas. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour les applets de commande Business Server Management Shell et le Service de journalisation centralisée, ligne de commande ClsController (ClsController.exe) ou commandes de l’agent (ClsAgent.exe) et collection de journal.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour les applets de commande Business Server Management Shell et le Service de journalisation centralisée, ligne de commande ClsController (ClsController.exe) ou commandes de l’agent (ClsAgent.exe) et collection de journal.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour les applets de commande Business Server Management Shell et le Service de journalisation centralisée, ligne de commande ClsController (ClsController.exe) ou commandes de l’agent (ClsAgent.exe) et collection de journal.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Adresses IP virtuelles d’interface externe

|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non pris en charge dans Skype pour professionnels Server 2019 |TCP  <br/> |5269  <br/> |Indifférente  <br/> |Service Proxy XMPP (partage une adresse IP avec le service Edge d’accès)  <br/> |Le service Proxy XMPP accepte le trafic provenant des contacts XMPP dans les fédérations XMPP définies.  <br/> |
|XMPP  <br/>Non pris en charge dans Skype pour professionnels Server 2019 |TCP  <br/> |5269  <br/> |Service Proxy XMPP (partage une adresse IP avec le service Edge d’accès)  <br/> |Indifférente  <br/> |Le service Proxy XMPP envoie le trafic provenant des contacts XMPP dans les fédérations XMPP définies.  <br/> |
|Accès/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Trafic SIP client vers serveur pour l’accès des utilisateurs externes.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifférente  <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privées utilisant NAT :** Service Edge d’accès serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du bord serveur Edge d’accès service <br/> |Indifférente  <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Conférence web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**IP privées utilisant NAT :** Service Edge de conférence Web serveur Edge <br/> **Les adresses IP publiques :** Adresse IP publique du côté serveur Edge de conférence Web service <br/> |Données multimédias de conférence Web.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |**IP privées utilisant NAT :** Edge Server A / V Edge service <br/> **Les adresses IP publiques :** Edge Server A / V Edge adresse IP publique du service <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**IP privées utilisant NAT :** Edge Server A / V Edge service <br/> **Les adresses IP publiques :** Edge Server A / V Edge adresse IP publique du service <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Adresses IP virtuelles d’interface interne

Nos conseils ici vont être légèrement différents. En réalité, dans une situation d’équilibrage de charge matérielle, nous vous recommandons de n’avoir qu’un routage via une adresse virtuelle interne dans les circonstances suivantes :
  
- Si vous utilisez Exchange 2007 ou Exchange 2010 messagerie unifiée.
    
- Si vous avez des clients hérités utilisant le serveur Edge.
    
Le tableau suivant donne des conseils pour ces scénarios, mais dans le cas contraire, vous pourrez dépendent du magasin Central de gestion (CMS) pour acheminer le trafic vers le serveur de périphérie qu’il (cela ne nécessite que CMS est mis à jour sur le serveur de transport Edge informations de cours).
  
|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Pool directeur adresse IP virtuelle  <br/> • Serveur frontal  <br/> • Le pool frontal adresse IP virtuelle  <br/> |Interface interne du serveur Edge  <br/> |Le trafic SIP sortant de votre directeur, le pool directeur adresse VIP, le serveur frontal ou adresse IP virtuelle du pool frontal adresse à l’interface interne du serveur Edge.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface de l’adresse IP virtuelle interne des serveurs de périphérie  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Pool directeur adresse IP virtuelle  <br/> • Serveur frontal  <br/> • Le pool frontal adresse IP virtuelle  <br/> |Trafic SIP entrant vers votre directeur, adresse IP virtuelle de pool de directeur, serveur frontal ou adresse d’adresse IP virtuelle de pool frontal à partir de l’interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Indifféremment :  <br/> • Les adresse IP du serveur frontal  <br/> Adresse IP de • front End pool  <br/> • Les Survivable Branch Appliance à l’aide de ce serveur Edge  <br/> • N’importe quel serveur Survivable Branch Server à l’aide de ce serveur Edge  <br/> |Interface interne du serveur Edge  <br/> |L’authentification a / utilisateurs V à partir de votre pool frontal ou serveur frontal, ou votre Survivable Branch Appliance ou Survivable Branch Server, à l’aide de votre serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |Interface de l’adresse IP virtuelle interne des serveurs de périphérie  <br/> |Chemin d’accès de secours pour le transfert multimédia A/V entre vos utilisateurs internes et externes. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |
