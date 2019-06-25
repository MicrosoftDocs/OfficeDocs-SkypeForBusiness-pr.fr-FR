---
title: Configuration requise pour l’environnement du serveur Edge dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Résumé: en savoir plus sur la configuration environnementale requise pour le serveur Edge dans Skype entreprise Server.'
ms.openlocfilehash: c6127f862bcc21d113404eb7bf1868757a83cf32
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35203955"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Configuration requise pour l’environnement du serveur Edge dans Skype entreprise Server
 
**Résumé:** En savoir plus sur la configuration environnementale requise pour le serveur Edge dans Skype entreprise Server.
  
Un grand nombre de planification et de préparation doivent avoir lieu à l’extérieur de l’environnement de serveur Edge de Skype entreprise Server. Dans cet article, nous allons examiner les préparations à effectuer dans l’environnement organisationnel, selon la liste ci-dessous :
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planification de la topologie
<a name="TopoPlan"> </a>

Les topologies de serveur Edge de Skype entreprise Server peuvent utiliser les éléments suivants:
  
- des adresses IP publiques routables ;
    
- des adresses IP privées non routables si la conversion d’adresses réseau (NAT) **symétrique** est utilisée.
    
> [!TIP]
> Votre serveur Edge peut être configuré pour utiliser une seule adresse IP avec des ports distincts pour chaque service, ou bien il peut utiliser des adresses IP distinctes pour chaque service, mais utiliser le même port par défaut (qui, par défaut, est TCP 443). Vous trouverez plus d’informations dans la section consacrée aux exigences liées aux adresses IP, ci-dessous. 
  
Si vous sélectionnez des adresses IP privées non routables avec conversion d’adresses réseau, n’oubliez pas les points suivants :
  
- Vous devez utiliser des adresses IP privées routables sur les **trois** interfaces externes.
    
- Vous devez configurer la fonction de conversion d’adresses réseau (NAT) **symétrique** pour le trafic entrant et sortant. Le NAT symétrique est le seul protocole NAT pris en charge que vous pouvez utiliser avec Skype entreprise Server Edge Server.
    
- Configurez la fonction de conversion d’adresses réseau (NAT) de manière à ne pas modifier les adresses source entrantes. Le service Edge A/V doit être en mesure de recevoir l’adresse source entrante pour trouver le chemin multimédia optimal.
    
- Votre serveur Edge doit être en mesure de communiquer entre eux à partir de leur adresse IP publique A/V. Votre pare-feu doit autoriser ce trafic.
    
- TAR ne peut être utilisée **que** pour les serveurs Edge consolidés mis à l’échelle si vous utilisez l’équilibrage de charge DNS. Si vous utilisez l’équilibrage de charge matérielle, vous devez utiliser des adresses IP publiquement routables **sans** la fonction de conversion d’adresses réseau.
    
Vous n’avez aucun problème avec vos interfaces d’accès, de conférence Web et de périphérie A/V derrière un routeur ou un pare-feu qui effectue NAT symétrique pour les topologies de serveur de périphérie unique et à l’échelle (à condition que vous n’utilisiez pas l’équilibrage de charge matérielle).
  
### <a name="summary-of-edge-server-topology-options"></a>Résumé des options de topologie du serveur Edge

Plusieurs options de topologie sont disponibles pour les déploiements de serveur Edge de Skype entreprise Server:
  
- Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau
    
- Serveur Edge consolidé unique avec des adresses IP publiques
    
- Serveur Edge consolidé ajusté avec des adresses IP privées et la conversion d’adresses réseau
    
- Serveur Edge consolidé ajusté avec des adresses IP publiques
    
- Topologie Edge consolidée ajustée avec des équilibreurs de charge matérielle
    
Pour vous aider à choisir, le tableau ci-dessous contient un résumé des options à votre disposition pour chaque topologie :
  
|**Topologie**|**Haute disponibilité**|**Enregistrements DNS supplémentaires requis pour le serveur de périphérie externe dans le pool Edge?**|**Reprise latérale pour les sessions Skype entreprise Server**|**Reprise latérale pour les sessions de Fédération Skype entreprise Server**|
|:-----|:-----|:-----|:-----|:-----|
|Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Serveur Edge consolidé unique avec des adresses IP publiques  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Serveur Edge consolidé ajusté avec des adresses IP privées et de conversion d’adresses réseau (NAT) (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui&sup1;  <br/> |
|Serveur Edge consolidé ajusté avec des adresses IP publiques (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui&sup1;  <br/> |
|Topologie Edge consolidée ajustée avec des équilibreurs de charge matérielle  <br/> |Oui  <br/> |Non (un enregistrement DNS A par VIP)  <br/> |Oui  <br/> |Oui  <br/> |
   
&sup1; Le basculement d’utilisateur distant de la messagerie unifiée (MU) à l’aide de l’équilibrage de charge DNS nécessite Exchange 2013 ou une version ultérieure.
  
### <a name="ip-address-requirements"></a>Exigences d’adresse IP

D’un niveau fondamental, trois services nécessitent une adresse IP. Service Edge d’accès, service Edge de conférence Web et service Edge A/V. Vous avez la possibilité d’utiliser trois adresses IP, à savoir une pour chacun des services, ou d’en utiliser une seule et de placer chaque service sur un port différent (pour plus d’informations sur cette procédure, reportez à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)). Pour un environnement de serveur Edge consolidé unique, c’est à peu près tout ce qu’il y a à faire.
  
> [!NOTE]
> Comme indiqué ci-dessus, vous pouvez choisir d’avoir une adresse IP pour les trois services et de les exécuter sur différents ports, mais nous ne vous recommandons pas cette solution. Si vos clients ne peuvent pas accéder aux ports de remplacement que vous utiliseriez dans ce scénario, ils ne peuvent pas non plus accéder aux fonctionnalités complètes de votre environnement Edge. 
  
Les choses pouvant être un peu plus complexes avec topologies consolidées ajustées, examinons quelques tableaux reprenant les exigences d’adresses IP, en gardant à l’esprit que les principaux points devant orienter la sélection de la topologie sont la haute disponibilité et l’équilibrage de la charge. Des besoins de haute disponibilité peuvent influencer votre choix d’équilibrage de charge (nous approfondirons ce point après les tableaux).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Exigences d’adresses IP pour la topologie Edge consolidée ajustée (adresse IP par rôle)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses IP requises pour l’équilibrage de charge DNS**|**Nombre d’adresses IP requises pour l’équilibrage de charge matérielle**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 par adresse IP virtuelle) + 6  <br/> |
|3  <br/> |09  <br/> |3 (1 par adresse IP virtuelle) + 9  <br/> |
|4  <br/> |midi  <br/> |3 (1 par adresse IP virtuelle) + 12  <br/> |
|5  <br/> |0,15  <br/> |3 (1 par adresse IP virtuelle) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Exigences d’adresses IP pour la topologie Edge consolidée ajustée (adresse IP unique pour tous les rôles)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses IP requises pour l’équilibrage de charge DNS**|**Nombre d’adresses IP requises pour l’équilibrage de charge matérielle**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 par adresse IP virtuelle) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 par adresse IP virtuelle) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 par adresse IP virtuelle) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 par adresse IP virtuelle) + 5  <br/> |
   
Examinons d’autres aspects à prendre en compte lors de la planification.
  
- **Haute disponibilité**: Si vous avez besoin d’une haute disponibilité dans votre déploiement, vous devez déployer au moins deux serveurs Edge dans un pool. Il est intéressant de noter qu’un seul pool de bords peut prendre en charge jusqu’à 12 serveurs de bord (si le générateur de topologie vous permet d’ajouter jusqu’à 20, ce n’est pas testé ou pris en charge, nous vous conseillons de ne pas le faire). Si vous avez besoin de plus de 12 serveurs Edge, vous devez créer des pools d’arête supplémentaires.
    
- **Équilibrage de charge matérielle**: nous vous recommandons d’utiliser l’équilibrage de charge DNS pour la plupart des scénarios. Le service d’équilibrage de la charge matérielle est également pris en charge, bien évidemment, s’il est requis pour un scénario unique sur l’équilibrage de charge DNS:
    
  - Accès externe à Exchange 2007 ou Exchange 2010 (sans processeur de messagerie unifiée).
    
- L' **équilibrage de charge DNS**: pour la messagerie unifiée, Exchange 2010 SP1 et les versions ultérieures peuvent être pris en charge par l’équilibrage de charge DNS. Notez que si vous avez besoin d’utiliser l’équilibrage de charge DNS pour une version antérieure d’Exchange, le trafic sera ainsi transféré vers le premier serveur du pool et, s’il ne l’est pas, le trafic échouera par la suite.
    
    Il est également recommandé d’utiliser le service d’équilibrage de charge DNS si vous vous utilisez:
- Skype entreprise Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office 365
- Skype entreprise Server 2019:
    - Lync Server 2013
    - Skype Entreprise Server 2015
    - Microsoft Office 365.
    
## <a name="dns-planning"></a>Planification DNS
<a name="DNSPlan"> </a>

Lorsqu’il s’agit du déploiement de serveur Edge de Skype entreprise Server, il est essentiel de préparer correctement le DNS. Si les enregistrements corrects sont en place, le déploiement est beaucoup plus simple. Nous espérons que vous avez sélectionné une topologie dans la section ci-dessus, car nous allons présenter, puis répertorier plusieurs tableaux qui décrivent les enregistrements DNS pour les scénarios illustrés. Pour plus de détails, si vous en avez besoin, nous avons également besoin d’une [planification de DNS de serveur Edge avancée pour Skype entreprise Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) .
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Enregistrements DNS pour les scénarios de serveur Edge consolidés unique

Il s’agira des enregistrements DNS que vous allez avoir besoin pour un serveur de périphérie unique utilisant une IPS privée ou une IPs privée avec NAT. Comme il s’agit d’exemples de données, nous allons vous donner des exemples d’adresses IP pour que vous puissiez élaborer plus facilement vos propres entrées :
  
- Carte réseau interne: 172.25.33.10 (aucune passerelle par défaut attribuée)
    
    > [!NOTE]
    > Assurez-vous qu’il existe un itinéraire du réseau contenant l’interface interne latérale vers des réseaux contenant des serveurs exécutant Skype entreprise Server ou des clients Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Adresses IP publiques :
    
  - Access Edge: 131.107.155.10 (il s’agit du principal, avec passerelle par défaut définie pour votre routeur public, par exemple: 131.107.155.1)
    
  - Edge de conférence Web: 131.107.155.20 (secondaire)
    
  - Bordure A/V: 131.107.155.30 (secondaire)
    
  Les adresses IP publiques d’audioconférence et de conférence Web sont des adresses IP supplémentaires (secondaires) figurant dans la section avancé des propriétés de protocole Internet version 4 (TCP/IPv4) et protocole Internet (TCP/IPv6) des propriétés de connexion de la zone locale dans Windows Server.
    
  - Adresses IP privées :
    
  - Access Edge: 10.45.16.10 (il s’agit du principal, avec passerelle par défaut définie sur votre routeur, par exemple: 10.45.16.1)
    
  - Edge de conférence Web: 10.45.16.20 (secondaire)
    
  - Bordure A/V: 10.45.16.30 (secondaire)
    
Les adresses IP publiques d’audioconférence et de conférence Web sont des adresses IP supplémentaires (secondaires) figurant dans la section avancé des propriétés de protocole Internet version 4 (TCP/IPv4) et protocole Internet (TCP/IPv6) des propriétés de connexion de la zone locale dans Windows Server.
  
> [!TIP]
>Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Nous vous déconseillons de le faire, car vous devrez alors faire la distinction entre les services de la société qui utilise différents ports (ce que vous pouvez faire dans Skype entreprise Server), mais certains pare-feu peuvent bloquer les autres ports. Pour plus d’informations à ce sujet, reportez-vous à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan).
    
- Vous pouvez avoir trois cartes réseau externe au lieu d’une, et affecter un des services d’adresses IP à chacune d’elles. Pourquoi ? Vous séparez ainsi les services. Par conséquent, si un problème survient, il sera plus facile à résoudre et cela permettra éventuellement aux autres services de continuer à fonctionner pendant que cherchez une solution.
    
|**Emplacement**|**Type**|**Port**|**Enregistrement FQDN ou DNS**|**Adresse IP ou FQDN**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 <br/> **privé:** 10.45.16.10 <br/> |Interface externe pour votre service Edge d’accès. Vous en aurez besoin pour chaque domaine SIP avec des utilisateurs Skype entreprise.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 <br/> **privé:** 10.45.16.20 <br/> |Une interface externe pour le service Edge de conférence Web.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 <br/> **privé:** 10.45.16.30 <br/> |Une interface externe pour votre service Edge A/V.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour les clients Skype entreprise Server, Lync Server 2013 et Lync Server 2010 pour fonctionner en externe. Vous en aurez besoin pour chaque domaine avec des utilisateurs Skype entreprise.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour permettre la découverte DNS automatique de partenaires fédérés appelés domaines SIP (Session Initiation Protocol) autorisés. Vous en aurez besoin pour chaque domaine avec des utilisateurs Skype entreprise.  <br/> |
|DNS interne  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |L’interface interne de votre serveur Edge consolidé.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Enregistrements DNS pour les scénarios DNS et de serveur Edge à l’échelle

Il s’agira des enregistrements DNS que vous allez avoir besoin pour un serveur de périphérie unique utilisant une IPS privée ou une IPs privée avec NAT. Comme il s’agit d’exemples de données, nous allons vous donner des exemples d’adresses IP pour que vous puissiez élaborer plus facilement vos propres entrées :
  
- Carte réseau interne :
    
  - Nœud 1 : 172.25.33.10 (aucune passerelle par défaut affectée)
    
  - Nœud 2 : 172.25.33.11 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Assurez-vous qu’il existe un itinéraire du réseau contenant l’interface interne latérale vers des réseaux contenant des serveurs exécutant Skype entreprise Server ou des clients Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Nœud 1
    
     - Adresses IP publiques :
    
        - Access Edge: 131.107.155.10 (il s’agit du principal, avec passerelle par défaut définie pour votre routeur public, par exemple: 131.107.155.1)
    
        - Edge de conférence Web: 131.107.155.20 (secondaire)
    
        - Bordure A/V: 131.107.155.30 (secondaire)
    
          Les adresses IP publiques d’audioconférence et de conférence Web sont des adresses IP supplémentaires (secondaires) figurant dans la section avancé des propriétés de protocole Internet version 4 (TCP/IPv4) et protocole Internet (TCP/IPv6) des propriétés de connexion de la zone locale dans Windows Server.
    
    - Adresses IP privées :
    
         - Access Edge: 10.45.16.10 (il s’agit du principal, avec passerelle par défaut définie sur votre routeur, par exemple: 10.45.16.1)
    
         - Edge de conférence Web: 10.45.16.20 (secondaire)
    
         - Bordure A/V: 10.45.16.30 (secondaire)
    
      Les adresses IP publiques d’audioconférence et de conférence Web sont des adresses IP supplémentaires (secondaires) figurant dans la section avancé des propriétés de protocole Internet version 4 (TCP/IPv4) et protocole Internet (TCP/IPv6) des propriétés de connexion de la zone locale dans Windows Server.
    
  - Nœud 2
    
    - Adresses IP publiques :
    
      - Access Edge: 131.107.155.11 (il s’agit du principal, avec passerelle par défaut définie pour votre routeur public, par exemple: 131.107.155.1)
    
      - Edge de conférence Web: 131.107.155.21 (secondaire)
    
      - Bordure A/V: 131.107.155.31 (secondaire)
    
      Les adresses IP publiques d’audioconférence et de conférence Web sont des adresses IP supplémentaires (secondaires) figurant dans la section avancé des propriétés de protocole Internet version 4 (TCP/IPv4) et protocole Internet (TCP/IPv6) des propriétés de connexion de la zone locale dans Windows Server.
    
  - Adresses IP privées :
    
    - Access Edge: 10.45.16.11 (il s’agit du principal, avec passerelle par défaut définie sur votre routeur, par exemple: 10.45.16.1)
    
    - Edge de conférence Web: 10.45.16.21 (secondaire)
    
    - Bordure A/V: 10.45.16.31 (secondaire)
    
      Les adresses IP publiques d’audioconférence et de conférence Web sont des adresses IP supplémentaires (secondaires) figurant dans la section avancé des propriétés de protocole Internet version 4 (TCP/IPv4) et protocole Internet (TCP/IPv6) des propriétés de connexion de la zone locale dans Windows Server.
    
Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Nous vous déconseillons de le faire, car vous devrez alors faire la distinction entre les services de la société qui utilise différents ports (ce que vous pouvez faire dans Skype entreprise Server), mais certains pare-feu peuvent bloquer les autres ports. Pour plus d’informations à ce sujet, reportez-vous à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan).
    
- Vous pouvez avoir trois cartes réseau externe au lieu d’une, et affecter un des services d’adresses IP à chacune d’elles. Pourquoi ? Vous séparez ainsi les services. Par conséquent, si un problème survient, il sera plus facile à résoudre et cela permettra éventuellement aux autres services de continuer à fonctionner pendant que cherchez une solution.
    
|**Emplacement**|**Type**|**Port**|**Enregistrement FQDN ou DNS**|**Adresse IP ou FQDN**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 et 131.107.155.11 <br/> **privé:** 10.45.16.10 et 10.45.16.11 <br/> |Interface externe pour votre service Edge d’accès. Vous en aurez besoin pour chaque domaine SIP avec des utilisateurs Skype entreprise.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 et 131.107.155.21 <br/> **privé:** 10.45.16.20 et 10.45.16.21 <br/> |Une interface externe pour le service Edge de conférence Web.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 et 131.107.155.31 <br/> **privé:** 10.45.16.30 et 10.45.16.31 <br/> |Une interface externe pour votre service Edge A/V.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour les clients Skype entreprise Server, Lync Server 2013 et Lync Server 2010 pour fonctionner en externe. Vous en aurez besoin pour chaque domaine avec Skype entreprise.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour permettre la découverte DNS automatique de partenaires fédérés appelés domaines SIP (Session Initiation Protocol) autorisés. Vous en aurez besoin pour chaque domaine avec Skype entreprise.  <br/> |
|DNS interne  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 et 172.25.33.11  <br/> |L’interface interne de votre serveur Edge consolidé.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Enregistrement DNS pour la fédération (tous les scénarios)

|**Emplacement**|**Type**|**Port**|**FQDN**|**Enregistrement d’hôte FQDN**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |L’interface externe d’accès SIP SIP requise pour la découverte automatique du DNS. Utilisée par vos autres partenaires de fédération potentiels. Elle est également connue sous le nom de « domaines SIP autorisés ». Vous aurez besoin de l’un de ces éléments pour chaque domaine SIP avec des utilisateurs de Skype entreprise.  <br/><br/> **Remarque:** Vous aurez besoin de cet enregistrement SRV pour la mobilité et de l’hébergement d’échanges de notifications de transmission. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Enregistrements DNS pour le protocole XMPP (Extensible Messaging et Presence Protocol)

|**Emplacement**|**Type**|**Port**|**FQDN**|**Adresse IP ou enregistrement d’hôte FQDN**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |Interface de proxy XMPP sur votre service Edge d’accès ou votre pool d’arêtes. Vous devez effectuer cette opération si nécessaire pour tous les domaines SIP internes dotés de Skype entreprise Server, où le contact avec les contacts XMPP est autorisé via:  <br/> • politique globale  <br/> • stratégie de site sur laquelle l’utilisateur a activé  <br/> • une stratégie utilisateur appliquée à l’utilisateur de Skype entreprise Server.  <br/> une stratégie XMPP autorisée doit également être configurée dans la stratégie des utilisateurs fédérés XMPP.  <br/> |
|DNS externe  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Adresse IP du service Edge d’accès du serveur de périphérie ou du pool de périphérie qui héberge votre service proxy XMPP  <br/> |Ce point pointe vers le service Edge d’accès sur le serveur Edge ou le pool Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).  <br/> |
   
> [!NOTE]
> Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

## <a name="certificate-planning"></a>Planification de certificat
<a name="CertPlan"> </a>

Skype entreprise Server utilise des certificats pour des communications sécurisées et chiffrées entre les serveurs et du serveur vers le client. Comme vous devez vous y attendre, les enregistrements DNS de vos certificats doivent correspondre au nom de sujet (SN) et à l’autre nom de sujet (SAN) de vos certificats. Vous accéderez maintenant fonctionner, à l’issue de la phase de planification, afin de vous assurer que vous avez le droit domaine complets enregistré dans DNS pour le nom de sujet et entrées d’autres noms de sujet de vos certificats.
  
Nous aborderons séparément les besoins de certificats internes et externes, puis examinerons un tableau qui présente la configuration requise pour les deux.
  
### <a name="external-certificates"></a>Certificats externes

Au minimum, le certificat attribué à vos interfaces de serveur Edge externe doit être fourni par une autorité de certification (CA) publique. Nous ne sommes pas en mesure de vous recommander une autorité de certification spécifique, mais nous disposons d’une liste de [partenaires de certification de communications unifiées](https://support.microsoft.com/en-us/kb/929395) qui vous permettent de vérifier si votre autorité de certification préférée figure dans la liste.
  
Quand aurez-vous besoin d’envoyer une demande à une autorité de certification pour ce certificat public et comment procéder ? Il existe différentes façons de faire :
  
- Vous pouvez suivre l’installation de Skype entreprise Server, puis le déploiement de serveur Edge. L’Assistant Déploiement de Skype entreprise Server dispose d’une étape pour générer une demande de certificat, que vous pouvez ensuite envoyer à l’aide de votre choix.
    
- Vous pouvez également utiliser les commandes Windows PowerShell pour générer cette demande, si ce n’est pas le cas pour les besoins de votre entreprise ou de votre stratégie de déploiement.
    
- Enfin, votre autorité de certification dispose de son propre processus de soumission, qui peuvent également impliquer Windows PowerShell ou une autre méthode. Dans ce cas, vous devrez, outre les informations figurant dans le présent document, à sa documentation.
    
Une fois le certificat reçu, vous devez commencer et l’attribuer à ces services dans Skype entreprise Server:
  
- Interface du service Edge d’accès
    
- Interface du service Edge de conférence Web
    
- Service d’authentification audio/vidéo (ne pas confondre avec le service Edge A/V, car il n’utilise pas de certificat pour chiffrer les flux audio et vidéo)
    
> [!IMPORTANT]
> Tous les serveurs Edge (s’ils appartiennent à la même liste de serveurs Edge) doivent avoir exactement le même certificat avec la même clé privée pour le service d’authentification par relais de média. 
  
### <a name="internal-certificates"></a>Certificats internes

Pour l’interface du serveur Edge interne, vous pouvez utiliser un certificat public d’une autorité de certification publique ou un certificat émis à partir de l’autorité de certification interne de votre organisation. Il n’est pas nécessaire de penser que le certificat interne utilise une entrée SN et qu’il n’y a aucune entrée SAN, de sorte que vous n’avez pas à vous soucier du réseau SAN du tout.
  
### <a name="required-certificates-table"></a>Tableau des certificats requis

Vous trouverez ici un tableau pour vous aider avec vos demandes. Les entrées FQDN indiquées ici sont fournies uniquement à titre d’exemples de domaines. Vous devrez introduire des demandes en fonction de vos propres domaines privés et publics. Voici un guide expliquant ce que nous avons utilisé :
  
- Contoso<span></span>. com: FQDN public
    
- Fabrikam<span></span>. com: deuxième nom de domaine complet public (ajouté comme une démonstration de ce que vous devez demander si vous avez plusieurs domaines SIP)
    
- Contoso<span></span>.net: domaine interne
    
#### <a name="edge-certificate-table"></a>Tableau des certificats de serveur Edge

Que vous utilisiez un serveur Edge ou un pool Edge, vous avez besoin de ce qui suit pour votre certificat:
  
|**Composant**|**Nom du sujet (SN)**|**Autres noms de sujets (SAN)/ordre**|**Remarques**|
|:-----|:-----|:-----|:-----|
|Serveur Edge externe  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Il s’agit du certificat que vous devez demander à une autorité de certification publique. Il devra être affecté aux interfaces Edge externes pour les éléments suivants :<br/> • Accès Edge  <br/> • Bordure de conférences Web  <br/> • Authentification audio/vidéo  <br/> <br/>La bonne nouvelle, c’est que les San sont ajoutés automatiquement à votre demande de certificat, et par conséquent, votre certificat une fois que vous avez envoyé la demande, en fonction de ce que vous avez défini pour ce déploiement dans le générateur de topologie. Vous devrez uniquement ajouter des entrées SAN pour les autres domaines SIP (Session Initiation Protocol) ou les autres entrées à prendre en charge. Pourquoi sip.contoso.com est-il répliqué dans cette instance ? Cela se produit aussi automatiquement et c’est nécessaire pour que tout fonctionne correctement.  <br/><br/> **Remarque:** Ce certificat peut également être utilisé pour la connectivité de messagerie instantanée publique. Vous n’avez pas besoin de faire quoi que ce soit différemment à son sujet, mais dans les versions précédentes de cette documentation, il était répertorié en tant que tableau distinct, ce qui n’est plus le cas maintenant. <br/> |
|Interface interne du serveur Edge  <br/> |sfbedge.contoso.com  <br/> |S.O.  <br/> |Vous pouvez obtenir ce certificat auprès d’une autorité de certification publique ou d’une autorité de certification interne. Il devra contenir l’utilisation améliorée de la clé du serveur, et vous devez l’affecter à l’interface Edge interne.  <br/> |
   
Si vous avez besoin d’un certificat pour le protocole XMPP (Extensible Messaging and Presence Protocol), ce dernier est identique aux entrées du tableau du serveur Edge externe ci-dessus, mais comporte les deux nouvelles entrées SAN suivantes :
  
- XMPP. <span> </span>Contoso<span></span>. com
    
- \*. contoso<span></span>. com
    
N’oubliez pas que la fonction XMPP est uniquement prise en charge dans Skype entreprise Server pour Google Talk, si vous le souhaitez ou si vous avez besoin de l’utiliser pour toute autre information, vous devez confirmer que le fournisseur tiers impliqué est disponible.
  
## <a name="port-and-firewall-planning"></a>Planification des ports et des pare-feu
<a name="PortFirewallPlan"> </a>

Le bon fonctionnement de votre planification sur les ports et les pare-feu pour les déploiements de serveur Edge Skype entreprise Server peut vous permettre de gagner du temps et de faire des économies. Par conséquent, nous allons répertorier des tableaux indiquant notre utilisation des protocoles et les ports, entrants ou sortants, à ouvrir, pour des scénarios de conversion d’adresses réseau (NAT) et des adresses IP publiques. Nous aurons également des tableaux distincts pour les scénarios d’équilibrage de charge matérielle et de plus amples conseils à ce sujet. Pour plus d’informations à ce sujet, nous avons également quelques [scénarios de serveur Edge dans Skype entreprise Server](scenarios.md) que vous pouvez consulter en fonction de vos problèmes de déploiement spécifiques.
  
### <a name="general-protocol-usage"></a>Utilisation générale des protocoles

Avant de consulter les tableaux récapitulatifs pour les pare-feu internes et externes, consultons également le tableau suivant :
  
|**Transport audio/vidéo**|**Utilisation**|
|:-----|:-----|
|UDP  <br/> |Protocole de couche transport par défaut pour les données audio et vidéo.  <br/> |
|TCP  <br/> |Protocole de couche transport de secours pour les données audio et vidéo.  <br/> Protocole requis pour le partage d’application sur Skype entreprise Server, Lync Server 2013 et Lync Server 2010.  <br/> Protocole de couche de transport requis pour le transfert de fichiers vers Skype entreprise Server, Lync Server 2013 et Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiendront des informations pour les utilisateurs utilisant des adresses IP privées avec conversion d’adresses réseau, ainsi que pour les personnes utilisant des adresses IP publiques. Vous trouverez ainsi toutes les permutations dans les [scénarios de votre serveur Edge dans la section Skype entreprise Server](scenarios.md) .
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non pris en charge dans Skype entreprise Server 2019 |TCP  <br/> |5269  <br/> |Indifférente  <br/> |Service proxy XMPP (partage d’une adresse IP avec le service Edge d’accès  <br/> |Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations de XMPP définies.  <br/> |
|Accès/HTTP  <br/> |TCP  <br/> |80  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Indifférente  <br/> |Vérification et extraction de la liste de révocation de certificats.  <br/> |
|Accès/DNS  <br/> |TCP  <br/> |53  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Indifférente  <br/> |Requête DNS sur TCP.  <br/> |
|Accès/DNS  <br/> |UDP  <br/> |53  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Indifférente  <br/> |Requête DNS sur UDP  <br/> |
|Accès/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Trafic SIP client vers serveur pour l’accès des utilisateurs externes.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifférente  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Indifférente  <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Conférence web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge de conférence Web Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge Conferencing Server Web <br/> |Support de conférence Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge serveur Edge A/V <br/> **Adresse IP publique:** Adresse IP publique du service Edge Server A/V <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge serveur Edge A/V <br/> **Adresse IP publique:** Adresse IP publique du service Edge Server A/V <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge serveur Edge A/V <br/> **Adresse IP publique:** Adresse IP publique du service Edge Server A/V <br/> |Indifférente  <br/> |Le port sortant 3478 est :  <br/> • Utilisé par Skype entreprise Server pour déterminer la version du serveur Edge avec laquelle il communique.  <br/> • Utilisé pour le trafic multimédia entre les serveurs Edge.  <br/> • Requis pour la Fédération avec Lync Server 2010.  <br/> • Indispensable si plusieurs pools Edge sont déployés au sein de votre organisation.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge serveur Edge A/V <br/> **Adresse IP publique:** Adresse IP publique du service Edge Server A/V <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge serveur Edge A/V <br/> **Adresse IP publique:** Adresse IP publique du service Edge Server A/V <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge serveur Edge A/V <br/> **Adresse IP publique:** Adresse IP publique du service Edge Server A/V <br/> |Indifférente  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port interne

|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des opérations ci-dessous exécutant le service de passerelle XMPP :  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic XMPP sortant de votre service de passerelle XMPP exécuté sur votre serveur frontal ou pool frontal.  <br/> **Remarque:** Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Pool de Directors  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Le trafic SIP sortant de votre directeur, de votre pool de directeurs, de votre serveur frontal ou de votre pool frontal vers votre interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interne du serveur Edge  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Pool de Directors  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Trafic SIP entrant vers votre directeur, pool de directeurs, serveur frontal ou pool frontal à partir de l’interface interne de votre serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal  <br/>  dans votre liste frontale <br/> |Interface interne du serveur Edge  <br/> |Trafic de conférences Web à partir de votre serveur frontal ou de chaque serveur frontal (si vous disposez d’un pool frontal) vers votre interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> • Toute unité de branchement Survivable utilisant ce serveur Edge  <br/> • Tout serveur de succursales survivant utilisant ce serveur Edge  <br/> |Interface interne du serveur Edge  <br/> |L’authentification des utilisateurs A/V à partir de votre serveur frontal ou de votre liste frontale ou de votre application de succursales ou de votre serveur de succursales survivant sur votre serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour le transfert de média A/V entre vos utilisateurs internes et externes et votre appareil de branche Survivable ou votre serveur de succursales survivant.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |Interface interne du serveur Edge  <br/> |Chemin de secours pour le transfert de média A/V entre vos utilisateurs internes et externes et votre appareil de succursales ou votre serveur de succursales survivables, si la communication UDP ne fonctionne pas. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Indifféremment :  <br/> • Serveur frontal sur lequel est stockée la Banque centrale de gestion  <br/> • Pool frontal qui contient le centre de gestion central  <br/> |Interface interne du serveur Edge  <br/> |La réplication des modifications de votre magasin d’administration centrale vers votre serveur Edge.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisé utilisant Skype entreprise Server Management Shell et les applets de commande de service de journalisation centralisée, de ClsController de ligne de commande (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisé utilisant Skype entreprise Server Management Shell et les applets de commande de service de journalisation centralisée, de ClsController de ligne de commande (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisé utilisant Skype entreprise Server Management Shell et les applets de commande de service de journalisation centralisée, de ClsController de ligne de commande (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Programmes d’équilibrage de charge matérielle pour les tableaux des ports Edge

Nous consacrons une section propre aux équilibreurs de charge matérielle et aux ports Edge, car les choses sont un peu plus complexes avec le matériel supplémentaire. Reportez-vous aux tableaux ci-dessous pour obtenir des conseils pour ce scénario particulier :
  
#### <a name="external-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiendront des informations pour les utilisateurs utilisant des adresses IP privées avec conversion d’adresses réseau, ainsi que pour les personnes utilisant des adresses IP publiques. Vous trouverez ainsi toutes les permutations dans les [scénarios de votre serveur Edge dans la section Skype entreprise Server](scenarios.md) .
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accès/HTTP  <br/> |TCP  <br/> |80  <br/> |Adresse IP publique du service Edge d’accès Edge Server  <br/> |Indifférente  <br/> |Vérification et extraction de la liste de révocation de certificats.  <br/> |
|Accès/DNS  <br/> |TCP  <br/> |53  <br/> |Adresse IP publique du service Edge d’accès Edge Server  <br/> |Indifférente  <br/> |Requête DNS sur TCP.  <br/> |
|Accès/DNS  <br/> |UDP  <br/> |53  <br/> |Adresse IP publique du service Edge d’accès Edge Server  <br/> |Indifférente  <br/> |Requête DNS sur UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Adresse IP du service Edge serveur Edge A/V  <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Adresse IP publique du service Edge Server A/V  <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Adresse IP publique du service Edge Server A/V  <br/> |Indifférente  <br/> |Le port sortant 3478 est :  <br/> • Utilisé par Skype entreprise Server pour déterminer la version du serveur Edge avec laquelle il communique.  <br/> • Utilisé pour le trafic multimédia entre les serveurs Edge.  <br/> • Requis pour la Fédération.  <br/> • Indispensable si plusieurs pools Edge sont déployés au sein de votre organisation.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Adresse IP publique du service Edge Server A/V  <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |Adresse IP publique du service Edge Server A/V  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Adresse IP publique du service Edge Server A/V  <br/> |Indifférente  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port interne

|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des opérations ci-dessous exécutant le service de passerelle XMPP :  <br/> • Serveur frontal  <br/> • Adresse VIP du pool frontal exécutant le service de passerelle XMPP  <br/> |Interface interne du serveur Edge  <br/> |Trafic XMPP sortant de votre service de passerelle XMPP exécuté sur votre serveur frontal ou pool frontal.  <br/><br/> **Remarque:** Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Indifféremment :  <br/> • Serveur frontal sur lequel est stockée la Banque centrale de gestion  <br/> • Pool frontal qui contient le centre de gestion central  <br/> |Interface interne du serveur Edge  <br/> |La réplication des modifications de votre magasin d’administration centrale vers votre serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal dans votre liste frontale  <br/> |Interface interne du serveur Edge  <br/> |Trafic de conférences Web à partir de votre serveur frontal ou de chaque serveur frontal (si vous disposez d’un pool frontal) vers votre interface interne du serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal dans votre liste frontale  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour le transfert de média A/V entre vos utilisateurs internes et externes et votre appareil de branche Survivable ou votre serveur de succursales survivant.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifféremment :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal de votre liste  <br/> |Interface interne du serveur Edge  <br/> |Chemin de secours pour le transfert de média A/V entre vos utilisateurs internes et externes et votre appareil de succursales ou votre serveur de succursales survivables, si la communication UDP ne fonctionne pas. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisé utilisant Skype entreprise Server Management Shell et les applets de commande de service de journalisation centralisée, de ClsController de ligne de commande (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisé utilisant Skype entreprise Server Management Shell et les applets de commande de service de journalisation centralisée, de ClsController de ligne de commande (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisé utilisant Skype entreprise Server Management Shell et les applets de commande de service de journalisation centralisée, de ClsController de ligne de commande (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Adresses IP virtuelles d’interface externe

|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non pris en charge dans Skype entreprise Server 2019 |TCP  <br/> |5269  <br/> |Indifférente  <br/> |Service proxy XMPP (partage d’une adresse IP avec le service Edge d’accès)  <br/> |Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations de XMPP définies.  <br/> |
|XMPP  <br/>Non pris en charge dans Skype entreprise Server 2019 |TCP  <br/> |5269  <br/> |Service proxy XMPP (partage d’une adresse IP avec le service Edge d’accès)  <br/> |Indifférente  <br/> |Le service proxy XMPP envoie le trafic de contacts XMPP dans les fédérations de XMPP définies.  <br/> |
|Accès/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Trafic SIP client vers serveur pour l’accès des utilisateurs externes.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifférente  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge d’accès Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge d’accès Edge Server <br/> |Indifférente  <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Conférence web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge de conférence Web Edge Server <br/> **Adresse IP publique:** Adresse IP publique du service Edge Conferencing Server Web <br/> |Support de conférence Web.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge serveur Edge A/V <br/> **Adresse IP publique:** Adresse IP publique du service Edge Server A/V <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau:** Service Edge serveur Edge A/V <br/> **Adresse IP publique:** Adresse IP publique du service Edge Server A/V <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Adresses IP virtuelles d’interface interne

Nos conseils ici vont être légèrement différents. En réalité, dans une situation d’équilibrage de charge matérielle, nous vous recommandons de n’avoir qu’un routage via une adresse virtuelle interne dans les circonstances suivantes :
  
- Si vous utilisez Exchange 2007 ou la messagerie unifiée Exchange 2010 (MU).
    
- Si vous avez des clients hérités utilisant le serveur Edge.
    
Le tableau suivant fournit des conseils pour ces scénarios, mais il est possible que vous soyez en mesure de dépendre du magasin de gestion central (CMS) pour acheminer le trafic vers le serveur de périphérie individuel qu’il est tenu de mettre à jour sur le serveur Edge. informations, bien entendu).
  
|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Adresse VIP du pool de réalisateurs  <br/> • Serveur frontal  <br/> • Adresse VIP du pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic SIP sortant de votre directeur, adresse VIP de pool de directeurs, serveur frontal ou adresse VIP de pool frontal vers l’interface interne de votre serveur Edge.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface VIP interne du serveur Edge  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Adresse VIP du pool de réalisateurs  <br/> • Serveur frontal  <br/> • Adresse VIP du pool frontal  <br/> |Trafic SIP entrant vers votre directeur, adresse VIP de pool de directeurs, serveur frontal ou adresse VIP de pool frontal à partir de l’interface interne de votre serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Indifféremment :  <br/> • Adresse IP du serveur frontal  <br/> • Adresse IP du pool frontal  <br/> • Toute unité de branchement Survivable utilisant ce serveur Edge  <br/> • Tout serveur de succursales survivant utilisant ce serveur Edge  <br/> |Interface interne du serveur Edge  <br/> |L’authentification des utilisateurs A/V à partir de votre serveur frontal ou de votre liste frontale ou de votre application de succursales ou de votre serveur de succursales survivant sur votre serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente   <br/> |Interface VIP interne du serveur Edge  <br/> |Chemin d’accès de secours pour le transfert multimédia A/V entre vos utilisateurs internes et externes. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |
