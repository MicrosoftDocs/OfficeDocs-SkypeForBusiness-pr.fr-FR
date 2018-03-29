---
title: Conditions préalables d’environnement pour le serveur Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Résumé : En savoir plus sur les exigences de l’environnement de serveur de transport Edge dans Skype de Business Server 2015.'
ms.openlocfilehash: fd3c7d6c5fe138878b0122ea5c1885ad6ef84171
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server-2015"></a>Conditions préalables d’environnement pour le serveur Edge dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur la configuration de l’environnement de serveur de transport Edge dans Skype pour Business Server 2015.
  
Beaucoup de planification et de préparation doit avoir lieu en dehors de la Skype pour un environnement de serveur de transport Edge 2015 Business Server lui-même. Dans cet article, nous allons examiner les préparations à effectuer dans l’environnement organisationnel, selon la liste ci-dessous :
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planification de la topologie
<a name="TopoPlan"> </a>

Skype pour les topologies de serveur de transport Edge Business Server 2015 sont en mesure d’utiliser :
  
- des adresses IP publiques routables ;
    
- des adresses IP privées non routables si la conversion d’adresses réseau (NAT) **symétrique** est utilisée.
    
> [!TIP]
> Votre serveur Edge peut être configuré pour utiliser une adresse IP unique avec ports distincts pour chaque service, ou il peut utiliser des adresses IP distinctes pour chaque service, mais vous pouvez utiliser le même port par défaut (qui, par défaut, sera TCP 443). Vous trouverez plus d’informations dans la section consacrée aux exigences liées aux adresses IP, ci-dessous. 
  
Si vous sélectionnez des adresses IP privées non routables avec conversion d’adresses réseau, n’oubliez pas les points suivants :
  
- Vous devez utiliser des adresses IP privées routables sur les **trois** interfaces externes.
    
- Vous devez configurer la fonction de conversion d’adresses réseau (NAT) **symétrique** pour le trafic entrant et sortant. NAT symétrique est que la seule prise en charge de NAT, vous pouvez utiliser avec Skype pour le serveur Edge de Business Server 2015.
    
- Configurez la fonction de conversion d’adresses réseau (NAT) de manière à ne pas modifier les adresses source entrantes. A / V Edge service doit être en mesure de recevoir l’adresse source entrante pour rechercher le chemin multimédia optimale.
    
- Vos serveurs Edge doivent être en mesure de communiquer avec l’autre à partir de leur public, A / V Edge adressesIP. Votre pare-feu doit autoriser ce trafic.
    
- NAT peut **uniquement** utilisé pour les serveurs Edge consolidée mise à l’échelle si vous utilisez l’équilibrage de la charge DNS. Si vous utilisez l’équilibrage de charge matérielle, vous devez utiliser des adresses IP publiquement routables **sans** la fonction de conversion d’adresses réseau.
    
Vous n’aurez aucun problème votre accès, conférences Web et A / V Edge des interfaces derrière un routeur ou un pare-feu assurant le service NAT symétrique pour à la fois unique et mise à l’échelle consolidée des topologies de serveur de transport Edge (tant que vous n’utilisez pas l’équilibrage de charge matérielle).
  
### <a name="summary-of-edge-server-topology-options"></a>Résumé des options de topologie de serveur de transport Edge

Nous avons plusieurs options de topologie disponibles pour Skype pour les déploiements de serveur de transport Edge 2015 Business Server :
  
- Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau
    
- Serveur Edge consolidé unique avec des adresses IP publiques
    
- Serveur Edge consolidé ajusté avec des adresses IP privées et la conversion d’adresses réseau
    
- Serveur Edge consolidé ajusté avec des adresses IP publiques
    
- Topologie Edge consolidée ajustée avec des équilibreurs de charge matérielle
    
Pour vous aider à choisir, le tableau ci-dessous contient un résumé des options à votre disposition pour chaque topologie :
  
|**Topologie**|**Haute disponibilité**|**Enregistrements DNS supplémentaires requis pour le serveur de transport Edge externe dans le pool de bord ?**|**Basculement de bord pour Skype pour les sessions Business Server**|**Basculement de bord pour Skype pour les sessions de fédération Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Serveur Edge consolidé unique avec des adresses IP publiques  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Serveur Edge consolidé ajusté avec des adresses IP privées et de conversion d’adresses réseau (NAT) (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui & sup1 ;  <br/> |
|Serveur Edge consolidé ajusté avec des adresses IP publiques (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui & sup1 ;  <br/> |
|Topologie Edge consolidée ajustée avec des équilibreurs de charge matérielle  <br/> |Oui  <br/> |Non (un enregistrement DNS A par VIP)  <br/> |Oui  <br/> |Oui  <br/> |
   
& sup1 ; Basculement sur incident de l’utilisateur distant Exchange la messagerie unifiée (MU) à l’aide de l’équilibrage de la charge DNS nécessite Exchange 2013 ou plus récente.
  
### <a name="ip-address-requirements"></a>Exigences d’adresse IP

À un niveau fondamentaux, trois services ont besoin des adresses IP ; Accès côté service, serveur Edge de conférence Web service et A / V Edge service. Vous avez la possibilité d’utiliser trois adresses IP, à savoir une pour chacun des services, ou d’en utiliser une seule et de placer chaque service sur un port différent (pour plus d’informations sur cette procédure, reportez à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)). Pour un environnement de serveur Edge consolidé unique, c’est à peu près tout ce qu’il y a à faire.
  
> [!NOTE]
> Comme indiqué ci-dessus, vous pouvez choisir d’avoir une adresse IP pour les trois services et de les exécuter sur différents ports, mais nous ne vous recommandons pas cette solution. Si vos clients ne peuvent pas accéder aux ports de remplacement que vous utiliseriez dans ce scénario, ils ne peuvent pas non plus accéder aux fonctionnalités complètes de votre environnement Edge. 
  
Les choses pouvant être un peu plus complexes avec topologies consolidées ajustées, examinons quelques tableaux reprenant les exigences d’adresses IP, en gardant à l’esprit que les principaux points devant orienter la sélection de la topologie sont la haute disponibilité et l’équilibrage de la charge. Des besoins de haute disponibilité peuvent influencer votre choix d’équilibrage de charge (nous approfondirons ce point après les tableaux).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Exigences d’adresses IP pour la topologie Edge consolidée ajustée (adresse IP par rôle)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses d’IP nécessaires pour le serveur DNS de l’équilibrage de la charge**|**Nombre d’adresses d’IP nécessaires pour l’équilibrage de charge matérielle**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 par adresse IP virtuelle) + 6  <br/> |
|3  <br/> |9  <br/> |3 (1 par adresse IP virtuelle) + 9  <br/> |
|4  <br/> |12  <br/> |3 (1 par adresse IP virtuelle) + 12  <br/> |
|5  <br/> |15  <br/> |3 (1 par adresse IP virtuelle) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Exigences d’adresses IP pour la topologie Edge consolidée ajustée (adresse IP unique pour tous les rôles)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses d’IP nécessaires pour le serveur DNS de l’équilibrage de la charge**|**Nombre d’adresses d’IP nécessaires pour l’équilibrage de charge matérielle**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 par adresse IP virtuelle) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 par adresse IP virtuelle) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 par adresse IP virtuelle) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 par adresse IP virtuelle) + 5  <br/> |
   
Examinons d’autres aspects à prendre en compte lors de la planification.
  
- **Haute disponibilité**: Si vous avez besoin d’une disponibilité élevée dans votre déploiement, vous devez déployer au moins deux serveurs de périphérie dans un pool. Il est important de noter qu’un seul pool de bord prend en charge jusqu'à 12 serveurs Edge (bien que le Générateur de topologies vous permettra d’ajouter jusqu'à 20, qui n’a pas testé ou pris en charge, nous vous conseillons de que vous ne pas le faire). Si vous avez besoin de plus de 12 serveurs de périphérie, vous devez créer des pools de bord supplémentaires pour eux.
    
- **L’équilibrage de charge matériel**: nous vous recommandons d’équilibrage pour la plupart des scénarios de charge de DNS. L’équilibrage de la charge matérielle est également prise en charge, bien sûr, mais en particulier est nécessaire pour un seul scénario sur l’équilibrage de la charge DNS :
    
  - Accès externe à Exchange 2007 ou Exchange 2010 (avec aucun SP) la messagerie unifiée (MU).
    
- **L’équilibrage de la charge DNS**: pour service de messagerie unifiée Exchange 2010 SP1 et les plus récent sont en mesure d’être pris en charge par l’équilibrage de la charge DNS. Notez que si vous avez besoin pour équilibrage DNS pour une version antérieure d’Exchange, elle fonctionne, mais tout le trafic pour ce passera au premier serveur dans le pool, et s’il n’est pas disponible, le trafic échoue par la suite.
    
    L’équilibrage de la charge DNS est également recommandée si vous êtes se fédérer avec les sociétés à l’aide de Microsoft Office 365, Lync Server 2013 et Lync Server 2010.
    
## <a name="dns-planning"></a>Planification DNS
<a name="DNSPlan"> </a>

Lorsqu’il s’agit de Skype pour le déploiement du serveur de transport Edge Business Server 2015, il est essentiel de préparer correctement pour le serveur DNS. Si les enregistrements corrects sont en place, le déploiement est beaucoup plus simple. Nous espérons que vous avez sélectionné une topologie dans la section ci-dessus, car nous allons présenter, puis répertorier plusieurs tableaux qui décrivent les enregistrements DNS pour les scénarios illustrés. Nous allons également une [planification de DNS du serveur de bord avancé de Skype pour Business Server 2015](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) pour une lecture plus approfondie, si vous avez besoin il.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Enregistrements DNS unique consolidée des scénarios de serveur de transport Edge

Ces paramètres seront les enregistrements DNS que vous aurez besoin pour un unique serveur de transport Edge à l’aide d’un accès public IPs ou IPs privé avec NAT. Comme il s’agit d’exemples de données, nous allons vous donner des exemples d’adresses IP pour que vous puissiez élaborer plus facilement vos propres entrées :
  
- Carte réseau interne : 172.25.33.10 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Vérifiez qu’il existe un itinéraire à partir du réseau contenant l’interface interne de bord à des réseaux qui contiennent des serveurs Skype pour clients Business Server 2015 ou Lync Server 2013 (par exemple, à partir de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Adresses IP publiques :
    
  - Edge d’accès : 131.107.155.10 (c’est le principal, avec une passerelle par défaut définie sur votre routeur public, ex : 131.107.155.1)
    
  - Serveur Edge de conférence Web : 131.107.155.20 (secondaire)
    
  - A / V Edge : 131.107.155.30 (secondaire)
    
  Web conferencing et A / V Edge public IP adresses sont supplémentaire (secondaire) dans la section Avancé des propriétés de Internet Protocol Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés de Serveur de Windows.
    
  - Adresses IP privées :
    
  - Edge d’accès : 10.45.16.10 (il s’agit de la principale, avec une passerelle par défaut définie sur votre routeur, ex : 10.45.16.1)
    
  - Serveur Edge de conférence Web : 10.45.16.20 (secondaire)
    
  - A / V Edge : 10.45.16.30 (secondaire)
    
Web conferencing et A / V Edge public IP adresses sont supplémentaire (secondaire) dans la section Avancé des propriétés de Internet Protocol Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés de Serveur de Windows.
  
> [!TIP]
>Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Nous ne le recommandons parce que puis vous aurez besoin faire la différence entre les trois services à l’aide de différents ports (vous pouvez le faire dans Skype pour Business Server), mais il existe certains pare-feux qui peut bloquer les autres ports. Pour plus d’informations à ce sujet, reportez-vous à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan).
    
- Vous pouvez avoir trois cartes réseau externe au lieu d’une, et affecter un des services d’adresses IP à chacune d’elles. Pourquoi ? Vous séparez ainsi les services. Par conséquent, si un problème survient, il sera plus facile à résoudre et cela permettra éventuellement aux autres services de continuer à fonctionner pendant que cherchez une solution.
    
|**Emplacement**|**Type de**|**Port**|**Enregistrement de nom de domaine complet ou de DNS**|**Adresse IP ou le nom de domaine complet**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |SIP.contoso.com  <br/> |**publics :** 131.107.155.10 <br/> **privé :** 10.45.16.10 <br/> |Une interface externe pour votre service Edge d’accès. Vous aurez besoin pour chaque domaine SIP avec Skype pour les utilisateurs professionnels.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |webcon.contoso.com  <br/> |**publics :** 131.107.155.20 <br/> **privé :** 10.45.16.20 <br/> |Une interface externe pour votre service serveur Edge de conférence Web.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |AV.contoso.com  <br/> |**publics :** 131.107.155.30 <br/> **privé :** 10.45.16.30 <br/> |Une interface externe pour vos A / V Edge service.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |SIP.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est nécessaire pour Skype pour Business Server 2015, Lync Server 2013 et Lync Server 2010 aux clients de travailler en externe. Vous aurez besoin pour chaque domaine avec Skype pour les utilisateurs professionnels.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour permettre la découverte DNS automatique de partenaires fédérés appelés domaines SIP (Session Initiation Protocol) autorisés. Vous aurez besoin pour chaque domaine avec Skype pour les utilisateurs professionnels.  <br/> |
|DNS interne  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sfvedge.contoso.NET  <br/> |172.25.33.10  <br/> |L’interface interne de votre serveur Edge consolidé.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Enregistrements DNS pour les scénarios de serveur de transport Edge de matériel et de DNS de mise à l’échelle

Ces paramètres seront les enregistrements DNS que vous aurez besoin pour un unique serveur de transport Edge à l’aide d’un accès public IPs ou IPs privé avec NAT. Comme il s’agit d’exemples de données, nous allons vous donner des exemples d’adresses IP pour que vous puissiez élaborer plus facilement vos propres entrées :
  
- Carte réseau interne :
    
  - Nœud 1 : 172.25.33.10 (aucune passerelle par défaut affectée)
    
  - Nœud 2 : 172.25.33.11 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Vérifiez qu’il existe un itinéraire à partir du réseau contenant l’interface interne de bord à des réseaux qui contiennent des serveurs Skype pour clients Business Server 2015 ou Lync Server 2013 (par exemple, à partir de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Nœud 1
    
     - Adresses IP publiques :
    
        - Edge d’accès : 131.107.155.10 (c’est le principal, avec une passerelle par défaut définie sur votre routeur public, ex : 131.107.155.1)
    
        - Serveur Edge de conférence Web : 131.107.155.20 (secondaire)
    
        - A / V Edge : 131.107.155.30 (secondaire)
    
          Web conferencing et A / V Edge public IP adresses sont supplémentaire (secondaire) dans la section Avancé des propriétés de Internet Protocol Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés de Serveur de Windows.
    
    - Adresses IP privées :
    
         - Edge d’accès : 10.45.16.10 (il s’agit de la principale, avec une passerelle par défaut définie sur votre routeur, ex : 10.45.16.1)
    
         - Serveur Edge de conférence Web : 10.45.16.20 (secondaire)
    
         - A / V Edge : 10.45.16.30 (secondaire)
    
      Web conferencing et A / V Edge public IP adresses sont supplémentaire (secondaire) dans la section Avancé des propriétés de Internet Protocol Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés de Serveur de Windows.
    
  - Nœud 2
    
     - Adresses IP publiques :
    
       - Edge d’accès : 131.107.155.11 (c’est le principal, avec une passerelle par défaut définie sur votre routeur public, ex : 131.107.155.1)
    
       - Serveur Edge de conférence Web : 131.107.155.21 (secondaire)
    
       - A / V Edge : 131.107.155.31 (secondaire)
    
      Web conferencing et A / V Edge public IP adresses sont supplémentaire (secondaire) dans la section Avancé des propriétés de Internet Protocol Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés de Serveur de Windows.
    
  - Adresses IP privées :
    
      - Edge d’accès : 10.45.16.11 (il s’agit de la principale, avec une passerelle par défaut définie sur votre routeur, ex : 10.45.16.1)
    
      - Serveur Edge de conférence Web : 10.45.16.21 (secondaire)
    
      - A / V Edge : 10.45.16.31 (secondaire)
    
      Web conferencing et A / V Edge public IP adresses sont supplémentaire (secondaire) dans la section Avancé des propriétés de Internet Protocol Version 4 (TCP/IPv4) et Internet Protocol Version 6 (TCP/IPv6) de la feuille de propriétés de Serveur de Windows.
    
Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Nous ne le recommandons parce que puis vous aurez besoin faire la différence entre les trois services à l’aide de différents ports (vous pouvez le faire dans Skype pour Business Server), mais il existe certains pare-feux qui peut bloquer les autres ports. Pour plus d’informations à ce sujet, reportez-vous à la rubrique [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan).
    
- Vous pouvez avoir trois cartes réseau externe au lieu d’une, et affecter un des services d’adresses IP à chacune d’elles. Pourquoi ? Vous séparez ainsi les services. Par conséquent, si un problème survient, il sera plus facile à résoudre et cela permettra éventuellement aux autres services de continuer à fonctionner pendant que cherchez une solution.
    
|**Emplacement**|**Type de**|**Port**|**Enregistrement de nom de domaine complet ou de DNS**|**Adresse IP ou le nom de domaine complet**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |SIP.contoso.com  <br/> |**public :** 131.107.155.10 et 131.107.155.11 <br/> **privé :** 10.45.16.10 et 10.45.16.11 <br/> |Une interface externe pour votre service Edge d’accès. Vous aurez besoin pour chaque domaine SIP avec Skype pour les utilisateurs professionnels.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |webcon.contoso.com  <br/> |**public :** 131.107.155.20 et 131.107.155.21 <br/> **privé :** 10.45.16.20 et 10.45.16.21 <br/> |Une interface externe pour votre service serveur Edge de conférence Web.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |S.O.  <br/> |AV.contoso.com  <br/> |**public :** 131.107.155.30 et 131.107.155.31 <br/> **privé :** 10.45.16.30 et 10.45.16.31 <br/> |Une interface externe pour vos A / V Edge service.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |SIP.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est nécessaire pour Skype pour Business Server 2015, Lync Server 2013 et Lync Server 2010 aux clients de travailler en externe. Vous aurez besoin pour chaque domaine avec Skype pour les entreprises.  <br/> |
|DNS externe  <br/> |Enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour permettre la découverte DNS automatique de partenaires fédérés appelés domaines SIP (Session Initiation Protocol) autorisés. Vous aurez besoin pour chaque domaine avec Skype pour les entreprises.  <br/> |
|DNS interne  <br/> |Enregistrement A  <br/> |S.O.  <br/> |sfvedge.contoso.NET  <br/> |172.25.33.10 et 172.25.33.11  <br/> |L’interface interne de votre serveur Edge consolidé.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Enregistrement DNS pour la fédération (tous les scénarios)

|**Emplacement**|**Type de**|**Port**|**NOM DE DOMAINE COMPLET**|**Enregistrement de nom de domaine complet d’hôte**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |L’interface externe SIP Edge d’accès requis pour la découverte automatique DNS. Utilisée par vos autres partenaires de fédération potentiels. Elle est également connue sous le nom de « domaines SIP autorisés ». Vous aurez besoin de l’une d'entre elles pour chaque domaine SIP avec Skype pour les utilisateurs professionnels.  <br/><br/> **Remarque :** Vous aurez besoin de cet enregistrement SRV de mobilité et de la notification de transmission centre d’échanges. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Enregistrements DNS pour le protocole XMPP (Extensible Messaging et Presence Protocol)

|**Emplacement**|**Type de**|**Port**|**NOM DE DOMAINE COMPLET**|**Adresse IP ou le nom de domaine complet des enregistrement hôte**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |XMPP.contoso.com  <br/> |L’interface de proxy XMPP sur votre service Edge d’accès ou d’un pool de bord. Vous devez reprenez cette étape pour tous les domaines SIP internes avec Skype pour les utilisateurs professionnels activé, où les contacts avec les contacts XMPP est autorisé par le biais de :  <br/> • une stratégie globale  <br/> • une stratégie de site où l’utilisateur l’activé  <br/> • une stratégie utilisateur le Skype pour entreprise activé utilisateur  <br/> une stratégie XMPP autorisée doit également être configurée dans la stratégie des utilisateurs fédérés XMPP.  <br/> |
|DNS externe  <br/> |SRV  <br/> |A  <br/> |XMPP.contoso.com  <br/> |Adresse IP du service Edge d’accès sur le serveur de transport Edge ou le pool de bord qui héberge votre service de serveur de Proxy XMPP  <br/> |Il pointe vers le service Edge d’accès sur le serveur de transport Edge ou le pool de bord qui héberge le service XMPP Proxy. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).  <br/> |
   
## <a name="certificate-planning"></a>Planification de certificat
<a name="CertPlan"> </a>

Skype pour Business Server 2015 utilise des certificats pour communications cryptées sécurisées entre des serveurs et du serveur au client. Comme vous devez vous y attendre, les enregistrements DNS de vos certificats doivent correspondre au nom de sujet (SN) et à l’autre nom de sujet (SAN) de vos certificats. Vous accéderez maintenant fonctionner, à l’issue de la phase de planification, afin de vous assurer que vous avez le droit domaine complets enregistré dans DNS pour le nom de sujet et entrées d’autres noms de sujet de vos certificats.
  
Nous aborderons séparément les besoins de certificats internes et externes, puis examinerons un tableau qui présente la configuration requise pour les deux.
  
### <a name="external-certificates"></a>Certificats externes

Au minimum, le certificat attribué à votre serveur de transport Edge des interfaces externes devez être fournie par une autorité de certification publiques (CA). Nous ne pouvons pas vous recommandons une autorité de certification spécifique pour vous, mais nous avons une liste d’autorités de certification, [partenaires de certificat de Communications unifiées](https://support.microsoft.com/en-us/kb/929395) que vous pouvez effectuer un aperçu pour voir si votre autorité de certification par défaut est répertoriée.
  
Quand aurez-vous besoin d’envoyer une demande à une autorité de certification pour ce certificat public et comment procéder ? Il existe différentes façons de faire :
  
- Vous pouvez accéder par le biais de l’installation de Skype pour Business Server, puis sur le déploiement de serveur de transport Edge. Le Skype pour l’Assistant de déploiement de Business Server aura une étape pour générer une demande de certificat que vous pouvez ensuite envoyer à votre autorité de certification de choisi.
    
- Vous pouvez également utiliser les commandes Windows PowerShell pour générer cette requête, si ce n’est plus insérée avec votre stratégie de déploiement ou de besoins de l’entreprise.
    
- Enfin, votre autorité de certification peut-être disposer de leur propre processus de soumission, qui peut également impliquer de Windows PowerShell ou une autre méthode. Dans ce cas, vous devrez, outre les informations figurant dans le présent document, à sa documentation.
    
Une fois que vous avez obtenu le certificat, vous devrez continuer et l’assigner à ces services dans Skype pour Business Server :
  
- Interface de service Access Edge
    
- Interface de service du serveur Edge de conférence Web
    
- Service d’authentification de données audio/vidéo (ne pas confondre avec l’A / V Edge service, que n’utiliser un certificat pour crypter les flux audio et vidéo)
    
> [!IMPORTANT]
> Tous les serveurs Edge doivent comporter exactement le même certificat avec la même clé privée pour le service d’authentification du serveur relais multimédia. 
  
### <a name="internal-certificates"></a>Certificats internes

Pour l’interface interne de serveur de transport Edge, vous pouvez utiliser un certificat public à partir d’une autorité de certification publique, ou un certificat émis par une autorité de certification interne de votre organisation. La chose à retenir à propos du certificat interne est qu’il utilise une entrée de n° de série et aucune entrée de SAN, sans que vous ayez à vous soucier SAN sur le certificat interne du tout.
  
### <a name="required-certificates-table"></a>Tableau des certificats requis

Vous trouverez ici un tableau pour vous aider avec vos demandes. Les entrées FQDN indiquées ici sont fournies uniquement à titre d’exemples de domaines. Vous devrez introduire des demandes en fonction de vos propres domaines privés et publics. Voici un guide expliquant ce que nous avons utilisé :
  
- contoso.com : FQDN public
    
- fabrikam.com : deuxième FQDN public (ajouté sous la forme d’une démonstration sur ce qu’il convient de demander si vous disposez de plusieurs domaines SIP [Session Initiation Protocol])
    
- Contoso.net : domaine interne
    
#### <a name="edge-certificate-table"></a>Tableau des certificats de serveur Edge

Que si vous effectuez un seul serveur Edge ou un pool d’arête, c’est ce que vous aurez besoin pour votre certificat :
  
|**Composant**|**Nom de l’objet (SN)**|**Autres noms (SAN) de l’objet / ordre**|**Remarques**|
|:-----|:-----|:-----|:-----|
|Serveur Edge externe  <br/> |SIP.contoso.com  <br/> |SIP.contoso.com  <br/> webcon.contoso.com  <br/> SIP.fabrikam.com  <br/> |Il s’agit du certificat que vous devez demander à une autorité de certification publique. Il devra être affecté aux interfaces Edge externes pour les éléments suivants :<br/> • Accès Edge  <br/> • Serveur Edge de conférence web  <br/> • Authentification de audio/vidéo  <br/> <br/>La bonne nouvelle est que les réseaux SAN sont automatiquement ajoutées à votre demande de certificat, et par conséquent votre certificat une fois que vous soumettez la demande, en fonction de ce que vous avez définis pour ce déploiement dans le Générateur de topologie. Vous devrez uniquement ajouter des entrées SAN pour les autres domaines SIP (Session Initiation Protocol) ou les autres entrées à prendre en charge. Pourquoi sip.contoso.com est-il répliqué dans cette instance ? Cela se produit aussi automatiquement et c’est nécessaire pour que tout fonctionne correctement.  <br/><br/> **Remarque :** Ce certificat peut également être utilisé pour la connectivité de messagerie instantanée publique. Vous n’avez pas besoin de faire quoi que ce soit différemment à son sujet, mais dans les versions précédentes de cette documentation, il était répertorié en tant que tableau distinct, ce qui n’est plus le cas maintenant. <br/> |
|Interface interne du serveur Edge  <br/> |sfbedge.contoso.com  <br/> |S.O.  <br/> |Vous pouvez obtenir ce certificat auprès d’une autorité de certification publique ou d’une autorité de certification interne. Il devra contenir l’utilisation améliorée de la clé du serveur, et vous devez l’affecter à l’interface Edge interne.  <br/> |
   
Si vous avez besoin d’un certificat pour le protocole XMPP (Extensible Messaging and Presence Protocol), ce dernier est identique aux entrées du tableau du serveur Edge externe ci-dessus, mais comporte les deux nouvelles entrées SAN suivantes :
  
- XMPP.contoso.com
    
- \*. contoso.com
    
N’oubliez pas que XMPP n’est pris en charge actuellement que pour Google Talk. Si vous voulez ou souhaitez l’utiliser pour autre chose, vous devez confirmer cette fonctionnalité avec le fournisseur tiers impliqué.
  
## <a name="port-and-firewall-planning"></a>Planification des ports et des pare-feu
<a name="PortFirewallPlan"> </a>

Mise en route de votre planification de droite des ports et des pare-feux pour Skype pour le serveur de transport Edge Server Business déploiements peuvent enregistrer de jours ou semaines de dépannage et de contrainte. Par conséquent, nous allons répertorier des tableaux indiquant notre utilisation des protocoles et les ports, entrants ou sortants, à ouvrir, pour des scénarios de conversion d’adresses réseau (NAT) et des adresses IP publiques. Nous aurons également des tableaux distincts pour les scénarios d’équilibrage de charge matérielle et de plus amples conseils à ce sujet. Pour plus d’informations à partir de là, nous disposons également de [diagrammes techniques pour Skype pour Business Server 2015](../../technical-diagrams.md), ainsi que des [scénarios de serveur de transport Edge dans Skype pour Business Server 2015](scenarios.md) vous pouvez extraire de vos problèmes de déploiement particulier.
  
### <a name="general-protocol-usage"></a>Utilisation générale des protocoles

Avant de consulter les tableaux récapitulatifs pour les pare-feu internes et externes, consultons également le tableau suivant :
  
|**Transport de données audio/vidéo**|**Utilisation de**|
|:-----|:-----|
|UDP  <br/> |Protocole de couche transport par défaut pour les données audio et vidéo.  <br/> |
|TCP  <br/> |Protocole de couche transport de secours pour les données audio et vidéo.  <br/> Le protocole de couche transport requis pour le partage d’applications à Skype pour Business Server 2015, Lync Server 2013 et Lync Server 2010.  <br/> Le protocole de couche transport requis pour le transfert de fichier à Skype pour Business Server 2015, Lync Server 2013 et Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiendront des informations pour les utilisateurs utilisant des adresses IP privées avec conversion d’adresses réseau, ainsi que pour les personnes utilisant des adresses IP publiques. Cela couvrira toutes les permutations dans notre section sur les [scénarios de serveur de transport Edge dans Skype pour Business Server 2015](scenarios.md) .
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Indifférente  <br/> |Service Proxy de XMPP (partage une adresse IP avec le service Edge d’accès  <br/> |Le service Proxy de XMPP accepte le trafic à partir des contacts XMPP les fédérations XMPP définies.  <br/> |
|Accès/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privé avec NAT :** Service de serveur Edge d’accès Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Indifférente  <br/> |Vérification et extraction de la liste de révocation de certificats.  <br/> |
|Accès/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privé avec NAT :** Service de serveur Edge d’accès Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Indifférente  <br/> |Requête DNS sur TCP.  <br/> |
|Accès/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privé avec NAT :** Service de serveur Edge d’accès Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Indifférente  <br/> |Requête DNS sur UDP  <br/> |
|Accès/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Service de serveur Edge d’accès Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Trafic SIP client vers serveur pour l’accès des utilisateurs externes.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Service de serveur Edge d’accès Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privé avec NAT :** Service de serveur Edge d’accès Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Indifférente  <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Conférence web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Service serveur Edge de conférence Web serveur Edge <br/> **Adresse IP publique :** Côté serveur Edge de conférence Web service service adresse IP publique <br/> |Média de conférence Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privé avec NAT :** Edge Server A / V Edge service service <br/> **Adresse IP publique :** Edge Server A / V Edge service adresse IP publique <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privé avec NAT :** Edge Server A / V Edge service service <br/> **Adresse IP publique :** Edge Server A / V Edge service adresse IP publique <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privé avec NAT :** Edge Server A / V Edge service <br/> **Adresse IP publique :** Edge Server A / V Edge service adresse IP publique <br/> |Indifférente  <br/> |Le port sortant 3478 est :  <br/> • Permet de déterminer la version de serveur de transport Edge par Skype pour Business Server il communique avec.  <br/> • Utilisé pour le trafic entre les serveurs Edge media.  <br/> • Requis pour la fédération avec Lync Server 2010.  <br/> • Nécessaire si plusieurs pools de bord sont déployés au sein de votre organisation.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Edge Server A / V Edge service <br/> **Adresse IP publique :** Edge Server A / V Edge service adresse IP publique <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Edge Server A / V Edge service <br/> **Adresse IP publique :** Edge Server A / V Edge service adresse IP publique <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privé avec NAT :** Edge Server A / V Edge service <br/> **Adresse IP publique :** Edge Server A / V Edge service adresse IP publique <br/> |Indifférente  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port interne

|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des opérations ci-dessous exécutant le service de passerelle XMPP :  <br/> • Serveur de Front-End  <br/> Pool de Front-End •  <br/> |Interface interne du serveur Edge  <br/> |XMPP le trafic sortant de votre service de passerelle de XMPP en cours d’exécution sur votre serveur frontal ou Front-End le pool.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Pool du directeur  <br/> • Serveur de Front-End  <br/> Pool de Front-End •  <br/> |Interface interne du serveur Edge  <br/> |Trafic SIP sortant de votre directeur, le directeur pool, pool de Front-End ou de serveur frontal pour l’interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interne du serveur Edge  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Pool du directeur  <br/> • Serveur de Front-End  <br/> Pool de Front-End •  <br/> |Trafic SIP entrant vers votre pool pool directeur, directeur, serveur frontal ou Front-End de l’interface interne du serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Indifféremment :  <br/> • Serveur de Front-End  <br/> • Chaque serveur frontal  <br/>  dans le pool de Front-End <br/> |Interface interne du serveur Edge  <br/> |Conférence le trafic Web de votre serveur frontal ou chaque serveur frontal (si vous avez un pool frontal) vers l’interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Indifféremment :  <br/> • Serveur de Front-End  <br/> Pool de Front-End •  <br/> • Tout Survivable Branch Appliance à l’aide de ce serveur de transport Edge  <br/> • Un serveur Survivable Branch Server à l’aide de ce serveur de transport Edge  <br/> |Interface interne du serveur Edge  <br/> |L’authentification a / utilisateurs V à partir de votre pool de serveur frontal ou de Front-End, ainsi que votre Survivable Branch Appliance ou serveur Survivable Branch Server, à l’aide de votre serveur de transport Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès préféré pour un transfert de médias entre les utilisateurs internes et externes et votre Survivable Branch Appliance ou le serveur Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès de secours pour un transfert de médias entre les utilisateurs internes et externes et votre Survivable Branch Appliance ou le serveur Survivable Branch Server, si la communication UDP ne fonctionne pas. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Indifféremment :  <br/> • Serveur frontal qui contient le magasin Central de gestion  <br/> Pool de Front-End • contenant le magasin Central de gestion  <br/> |Interface interne du serveur Edge  <br/> |Réplication des modifications de votre magasin Central de gestion de stockage à votre serveur de transport Edge.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour Business Server Management Shell et le Service d’enregistrement centralisé des applets de commande, ligne de commande de ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et collection du journal.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour Business Server Management Shell et le Service d’enregistrement centralisé des applets de commande, ligne de commande de ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et collection du journal.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour Business Server Management Shell et le Service d’enregistrement centralisé des applets de commande, ligne de commande de ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et collection du journal.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Programmes d’équilibrage de charge matérielle pour les tableaux des ports Edge

Nous consacrons une section propre aux équilibreurs de charge matérielle et aux ports Edge, car les choses sont un peu plus complexes avec le matériel supplémentaire. Reportez-vous aux tableaux ci-dessous pour obtenir des conseils pour ce scénario particulier :
  
#### <a name="external-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiendront des informations pour les utilisateurs utilisant des adresses IP privées avec conversion d’adresses réseau, ainsi que pour les personnes utilisant des adresses IP publiques. Cela couvrira toutes les permutations dans notre section sur les [scénarios de serveur de transport Edge dans Skype pour Business Server 2015](scenarios.md) .
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accès/HTTP  <br/> |TCP  <br/> |80  <br/> |Adresse IP publique de bord Edge d’accès serveur service  <br/> |Indifférente  <br/> |Vérification et extraction de la liste de révocation de certificats.  <br/> |
|Accès/DNS  <br/> |TCP  <br/> |53  <br/> |Adresse IP publique de bord Edge d’accès serveur service  <br/> |Indifférente  <br/> |Requête DNS sur TCP.  <br/> |
|Accès/DNS  <br/> |UDP  <br/> |53  <br/> |Adresse IP publique de bord Edge d’accès serveur service  <br/> |Indifférente  <br/> |Requête DNS sur UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edge Server A / V Edge service d’adresse IP  <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edge Server A / V Edge service adresse IP publique  <br/> |Indifférente  <br/> |Ceci est utilisé pour relayer le trafic multimédia.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edge Server A / V Edge service adresse IP publique  <br/> |Indifférente  <br/> |Le port sortant 3478 est :  <br/> • Permet de déterminer la version de serveur de transport Edge par Skype pour Business Server il communique avec.  <br/> • Utilisé pour le trafic entre les serveurs Edge media.  <br/> • Requis pour la fédération.  <br/> • Nécessaire si plusieurs pools de bord sont déployés au sein de votre organisation.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Edge Server A / V Edge service adresse IP publique  <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |Edge Server A / V Edge service adresse IP publique  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Edge Server A / V Edge service adresse IP publique  <br/> |Indifférente  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tableau récapitulatif des pare-feu de port interne

|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des opérations ci-dessous exécutant le service de passerelle XMPP :  <br/> • Serveur de Front-End  <br/> Pool de Front-End • adresse VIP exécutant le service passerelle de XMPP  <br/> |Interface interne du serveur Edge  <br/> |XMPP le trafic sortant de votre service de passerelle de XMPP en cours d’exécution sur votre serveur frontal ou Front-End le pool.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Indifféremment :  <br/> • Serveur frontal qui contient le magasin Central de gestion  <br/> Pool de Front-End • contenant le magasin Central de gestion  <br/> |Interface interne du serveur Edge  <br/> |Réplication des modifications de votre magasin Central de gestion à votre serveur de transport Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Indifféremment :  <br/> • Serveur de Front-End  <br/> • Chaque serveur frontal dans votre pool de Front-End  <br/> |Interface interne du serveur Edge  <br/> |Conférence le trafic Web de votre serveur frontal ou chaque serveur frontal (si vous avez un pool frontal) vers l’interface interne du serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifféremment :  <br/> • Serveur de Front-End  <br/> • Chaque serveur frontal dans votre pool de Front-End  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès préféré pour un transfert de médias entre les utilisateurs internes et externes et votre Survivable Branch Appliance ou le serveur Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifféremment :  <br/> • Serveur de Front-End  <br/> • Chaque serveur frontal dans votre pool  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès de secours pour un transfert de médias entre les utilisateurs internes et externes et votre Survivable Branch Appliance ou le serveur Survivable Branch Server, si la communication UDP ne fonctionne pas. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour Business Server Management Shell et le Service d’enregistrement centralisé des applets de commande, ligne de commande de ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et collection du journal.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour Business Server Management Shell et le Service d’enregistrement centralisé des applets de commande, ligne de commande de ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et collection du journal.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de Service de journalisation centralisée à l’aide de Skype pour Business Server Management Shell et le Service d’enregistrement centralisé des applets de commande, ligne de commande de ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et collection du journal.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Adresses IP virtuelles d’interface externe

|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Indifférente  <br/> |Service Proxy de XMPP (partage d’une adresse IP avec le service Edge d’accès)  <br/> |Le service Proxy de XMPP accepte le trafic à partir des contacts XMPP les fédérations XMPP définies.  <br/> |
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Service Proxy de XMPP (partage d’une adresse IP avec le service Edge d’accès)  <br/> |Indifférente  <br/> |Le service Proxy de XMPP envoie le trafic à partir des contacts XMPP les fédérations XMPP définies.  <br/> |
|Accès/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Service de serveur Edge d’accès Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Trafic SIP client vers serveur pour l’accès des utilisateurs externes.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Service de serveur Edge d’accès Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privé avec NAT :** Service de service Edge d’accès serveur Edge <br/> **Adresse IP publique :** Adresse IP publique de bord Edge d’accès serveur service <br/> |Indifférente  <br/> |Pour la connectivité fédérée et PIC utilisant le protocole SIP (Session Initiation Protocol).  <br/> |
|Conférence web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Service serveur Edge de conférence Web serveur Edge <br/> **Adresse IP publique :** Adresse IP publique de bord serveur Edge de conférence Web service <br/> |Média de conférence Web.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Edge Server A / V Edge service <br/> **Adresse IP publique :** Edge Server A / V Edge service adresse IP publique <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |**IP privé avec NAT :** Edge Server A / V Edge service <br/> **Adresse IP publique :** Edge Server A / V Edge service adresse IP publique <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Adresses IP virtuelles d’interface interne

Nos conseils ici vont être légèrement différents. En réalité, dans une situation d’équilibrage de charge matérielle, nous vous recommandons de n’avoir qu’un routage via une adresse virtuelle interne dans les circonstances suivantes :
  
- Si vous utilisez Exchange 2007 ou Exchange 2010 Unified Messaging (MU).
    
- Si vous avez des clients hérités utilisant le serveur Edge.
    
La table suivante a pour effet de conseils pour ces scénarios, mais dans le cas contraire, vous devez pouvoir compter sur le magasin Central de gestion (MCG) pour acheminer le trafic vers le serveur Edge individuels, il est conscient des (cela ne nécessite que CMS est mis à jour sur le serveur de transport Edge informations de cours).
  
|**Protocole**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Le pool directeur adresse VIP  <br/> • Serveur de Front-End  <br/> Pool de Front-End • adresse VIP  <br/> |Interface interne du serveur Edge  <br/> |Le trafic SIP sortant de votre directeur, le directeur pool adresse VIP, le serveur frontal ou VIP de pool frontal adresse à votre interface interne du serveur Edge.  <br/> |
|Accès/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface de bord VIP interne du serveur  <br/> |Indifféremment :  <br/> • Directeur  <br/> • Le pool directeur adresse VIP  <br/> • Serveur de Front-End  <br/> Pool de Front-End • adresse VIP  <br/> |Le trafic SIP à votre directeur, entrant adresse de pool VIP de directeur, serveur frontal ou l’adresse de pool VIP Front-End de l’interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Indifféremment :  <br/> • Avant fin adresse IP du serveur  <br/> Adresse IP de • Front-End pool  <br/> • Tout Survivable Branch Appliance à l’aide de ce serveur de transport Edge  <br/> • Un serveur Survivable Branch Server à l’aide de ce serveur de transport Edge  <br/> |Interface interne du serveur Edge  <br/> |L’authentification a / utilisateurs V à partir de votre pool de serveur frontal ou de Front-End, ainsi que votre Survivable Branch Appliance ou serveur Survivable Branch Server, à l’aide de votre serveur de transport Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indifférente  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Indifférente  <br/> |Interface de bord VIP interne du serveur  <br/> |Chemin d’accès de secours pour le transfert multimédia A/V entre vos utilisateurs internes et externes. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau.  <br/> |