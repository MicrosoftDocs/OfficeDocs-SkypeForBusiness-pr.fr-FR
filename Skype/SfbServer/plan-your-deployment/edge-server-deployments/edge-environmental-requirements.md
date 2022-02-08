---
title: Exigences environnementales du serveur Edge dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Résumé : Découvrez les exigences en matière d’environnement pour le serveur Edge dans Skype Entreprise Server.'
ms.openlocfilehash: d6594b76a66aab6354db516f1223059fe09caf82
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387972"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Exigences environnementales du serveur Edge dans Skype Entreprise Server
 
**Résumé :** Découvrez les exigences en matière d’environnement pour le serveur Edge dans Skype Entreprise Server.
  
Une grande partie de la planification et de la préparation doit avoir lieu en dehors de l Skype Entreprise Server de serveur Edge lui-même. Dans cet article, nous examinerons les préparations qui doivent être réalisées dans l’environnement organisationnel, comme dans notre liste ci-dessous :
  
- [Planification de la topologie](edge-environmental-requirements.md#TopoPlan)
    
- [Planification DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Planification des certificats](edge-environmental-requirements.md#CertPlan)
    
- [Planification des ports et des pare-feu](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planification de la topologie
<a name="TopoPlan"> </a>

Skype Entreprise Server les topologies de serveur Edge peuvent utiliser :
  
- Adresses IP publiques routables.
    
- Adresses IP privées non routables, si **la traduction d’adresses** réseau symétrique (NAT) est utilisée.
    
> [!TIP]
> Votre serveur Edge peut être configuré pour utiliser une adresse IP unique avec des ports distincts pour chaque service, ou il peut utiliser des adresses IP distinctes pour chaque service, mais utiliser le même port par défaut (qui, par défaut, sera TCP 443). Pour plus d’informations, voir la section Sur les exigences en matière d’adresses IP ci-dessous. 
  
Si vous choisissez des adresses IP privées non routables avec NAT, n’oubliez pas les points ci-après :
  
- Vous devez utiliser des adresses IP privées routables sur **les trois** interfaces externes.
    
- Vous devez configurer la nat **symétrique** pour le trafic entrant et sortant. La nat symétrique est la seule nat prise en charge que vous pouvez utiliser Skype Entreprise Server serveur Edge.
    
- Configurez votre nat pour ne pas modifier les adresses sources entrantes. Le service Edge A/V doit être en mesure de recevoir l’adresse source entrante pour trouver le chemin d’accès multimédia optimal.
    
- Vos serveurs Edge doivent pouvoir communiquer entre eux à partir de leurs adresses IP Edge A/V publiques. Votre pare-feu doit autoriser ce trafic.
    
- Nat ne **peut être** utilisé que pour les serveurs Edge consolidés à l’échelle si vous utilisez l’équilibrage de charge DNS. Si vous utilisez l’équilibrage de la charge matérielle, vous devez utiliser des adresses IP publiquement routables **sans** NAT.
    
Vos interfaces Edge Access, webconférence et A/V n’auront aucun problème derrière un routeur ou un pare-feu qui exécutent une nat symétrique pour les topologies de serveur Edge consolidées unique et mise à l’échelle (tant que vous n’utilisez pas l’équilibrage de la charge matérielle).
  
### <a name="summary-of-edge-server-topology-options"></a>Résumé des options de topologie de serveur Edge

Plusieurs options de topologie sont disponibles pour les déploiements Skype Entreprise Server Edge Server :
  
- Edge consolidé unique avec adresses IP privées et NAT
    
- Edge consolidé unique avec adresses IP publiques
    
- Edge consolidé à l’échelle avec adresses IP privées et NAT
    
- Edge consolidé à l’échelle avec adresses IP publiques
    
- Edge consolidé à l’échelle avec des équilibreurs de charge matérielle
    
Pour vous aider à en choisir une, nous avons le tableau suivant qui récapitule les options disponibles pour chaque topologie :
  
|**Topologie**|**Disponibilité élevée**|**Enregistrements DNS supplémentaires requis pour le serveur Edge externe dans le pool edge ?**|**Le failover Edge pour les sessions Skype Entreprise Server sessions**|**Le failover Edge pour Skype Entreprise Server sessions de fédération**|
|:-----|:-----|:-----|:-----|:-----|
|Edge consolidé unique avec adresses IP privées et NAT  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Edge consolidé unique avec adresses IP publiques  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Edge consolidé à l’échelle avec adresses IP privées et NAT (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui&sup1;  <br/> |
|Edge consolidé à l’échelle avec adresses IP publiques (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui&sup1;  <br/> |
|Edge consolidé à l’échelle avec des équilibreurs de charge matérielle  <br/> |Oui  <br/> |Non (un enregistrement DNS A par VIP)  <br/> |Oui  <br/> |Oui  <br/> |
   
&sup1; Exchange de messagerie unifiée à distance à l’aide de l’équilibrage de charge DNS nécessite Exchange 2013 ou une nouvelle génération.
  
### <a name="ip-address-requirements"></a>Exigences relatives aux adresses IP

À un niveau fondamental, trois services ont besoin d’adresses IP ; Service Edge d’accès, service Edge de conférence web et service Edge A/V. Vous avez la possibilité d’utiliser trois adresses IP, une pour chacun des services, ou vous pouvez en utiliser une et choisir de placer chaque service sur un port différent (vous pouvez consulter [la section Planification](edge-environmental-requirements.md#PortFirewallPlan) du port et du pare-feu pour plus d’informations sur certains de ces services). Pour un environnement Edge consolidé unique, c’est à peu près tout.
  
> [!NOTE]
> Comme indiqué ci-dessus, vous pouvez choisir d’avoir une adresse IP pour les trois services et de les exécuter sur différents ports. Mais, pour être clair, nous ne recommandons pas cela. Si vos clients ne peuvent pas accéder aux autres ports que vous utiliseriez dans ce scénario, ils ne peuvent pas non plus accéder aux fonctionnalités complètes de votre environnement Edge. 
  
Cela peut être un peu plus compliqué avec des topologies consolidées à l’échelle. Examinons donc certains tableaux qui détaillent les exigences en matière d’adresses IP, en gardant à l’esprit que les principaux points de décision pour la sélection de topologie sont la haute disponibilité et l’équilibrage de charge. Les besoins de haute disponibilité peuvent influencer votre choix d’équilibrage de charge (nous en parlerons davantage après les tableaux).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Exigences en matière d’adresses IP pour le edge consolidé à l’échelle (adresse IP par rôle)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses IP requises pour l’équilibrage de charge DNS**|**Nombre d’adresses IP requises pour l’équilibrage de la charge matérielle**|
|:-----|:-----|:-----|
|2  <br/> |6   <br/> |3 (1 par adresse IP virtuelle) + 6  <br/> |
|3  <br/> |9   <br/> |3 (1 par adresse IP virtuelle) + 9  <br/> |
|4  <br/> |12   <br/> |3 (1 par adresse IP virtuelle) + 12  <br/> |
|5  <br/> |15   <br/> |3 (1 par vip) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Exigences en matière d’adresses IP pour le edge consolidé à l’échelle (adresse IP unique pour tous les rôles)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses IP requises pour l’équilibrage de charge DNS**|**Nombre d’adresses IP requises pour l’équilibrage de la charge matérielle**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 par adresse IP virtuelle) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 par adresse IP virtuelle) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 par adresse IP virtuelle) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 par adresse IP virtuelle) + 5  <br/> |
   
Examinons quelques éléments supplémentaires à prendre en compte lors de la planification.
  
- **Haute disponibilité** : si vous avez besoin d’une haute disponibilité dans votre déploiement, vous devez déployer au moins deux serveurs Edge dans un pool. Il est intéressant de noter qu’un seul pool edge prendra en charge jusqu’à 12 serveurs Edge (bien que le Générateur de topologie vous permet d’ajouter jusqu’à 20 serveurs, ce qui n’est pas testé ou pris en charge, nous vous conseillons de ne pas le faire). Si vous avez besoin de plus de 12 serveurs Edge, vous devez créer des pools de serveurs Edge supplémentaires pour eux.
    
- **Équilibrage de la charge matérielle** : nous recommandons l’équilibrage de charge DNS pour la plupart des scénarios. L’équilibrage de la charge matérielle est également pris en charge, bien entendu, mais il est notamment nécessaire pour un scénario unique sur l’équilibrage de charge DNS :
    
  - Accès externe à Exchange 2007 ou Exchange 2010 (sans SP) messagerie unifiée (UM).
    
- Équilibrage de charge **DNS** : pour la Exchange 2010 SP1 et les plus nouvelles sont en mesure d’être pris en charge par l’équilibrage de charge DNS. Notez que si vous devez passer à l’équilibrage de charge DNS pour une version antérieure de Exchange, cela fonctionne, mais tout le trafic pour cela sera vers le premier serveur du pool, et s’il n’est pas disponible, ce trafic échouera par la suite.
    
    L’équilibrage de charge DNS est également recommandé si vous vous fédéré avec des sociétés utilisant :
- Skype Entreprise Server 2015 :
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 ou Office 365
- Skype Entreprise Server 2019 :
    - Lync Server 2013
    - Skype Entreprise Server 2015
    - Microsoft 365 ou Office 365
    
## <a name="dns-planning"></a>Planification DNS
<a name="DNSPlan"> </a>

En ce qui concerne Skype Entreprise Server déploiement de serveur Edge, il est essentiel de préparer correctement le DNS. Une fois les enregistrements en place, le déploiement sera beaucoup plus simple. Nous espérons que vous avez choisi une topologie dans la section ci-dessus, car nous allons faire une vue d’ensemble, puis ré lister quelques tableaux décrivant les enregistrements DNS pour ces scénarios. Nous allons également avoir une planification [DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) de serveur Edge avancé pour Skype Entreprise Server pour une lecture plus approfondie, si nécessaire.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Enregistrements DNS pour les scénarios de serveur Edge consolidé unique

Il s’agit des enregistrements DNS dont vous aurez besoin pour un serveur Edge en utilisant des IP publiques ou privées avec nat. Étant donné qu’il s’agit d’exemples de données, nous allons donner des exemples d’entrées d’entrée pour vous aider à trouver vos propres entrées :
  
- Carte réseau interne : 172.25.33.10 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et tous les réseaux qui contiennent des serveurs exécutant des clients Skype Entreprise Server ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Les IP publiques :
    
  - Edge d’accès : 131.107.155.10 (il s’agit de la passerelle principale, avec la passerelle par défaut définie sur votre routeur public, par exemple : 131.107.155.1)
    
  - Serveur Edge de conférence web : 131.107.155.20 (secondaire)
    
  - Edge A/V : 131.107.155.30 (secondaire)
    
  Les adresses IP publiques edge A/V et de conférence web sont des adresses IP supplémentaires (secondaires) dans la section Avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion de zone locale dans Windows Server.
    
  - IPs privés :
    
  - Edge d’accès : 10.45.16.10 (il s’agit de la passerelle principale, avec la passerelle par défaut définie sur votre routeur, par exemple : 10.45.16.1)
    
  - Serveur Edge de conférence web : 10.45.16.20 (secondaire)
    
  - Edge A/V : 10.45.16.30 (secondaire)
    
Les adresses IP publiques edge A/V et de conférence web sont des adresses IP supplémentaires (secondaires) dans la section Avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion de zone locale dans Windows Server.
  
> [!TIP]
>Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Cela n’est pas recommandé, car vous devrez faire la distinction entre les différents services à l’aide de différents ports (ce que vous pouvez faire dans Skype Entreprise Server), mais certains pare-feu peuvent bloquer les autres ports. Pour plus [d’informations à](edge-environmental-requirements.md#PortFirewallPlan) ce sujet, consultez la section Sur la planification des ports et des pare-feu.
    
- Vous pouvez avoir trois cartes réseau externes au lieu d’une seule et affecter l’une des IP de service à chacune d’elles. Pourquoi faire cela ? Cela séparerait les services et en cas de problème, cela faciliterait la résolution des problèmes et laisserait éventuellement vos autres services continuer à fonctionner pendant que vous résolvez un problème.
    
|**Location**|**Type**|**Port**|**Enregistrement DNS ou FQDN**|**Adresse IP ou FQDN**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Un enregistrement  <br/> |N/A  <br/> |sip.contoso.com  <br/> |**public :** 131.107.155.10 <br/> **private:** 10.45.16.10 <br/> |Une interface externe pour votre service Edge d’accès. Vous en aurez besoin pour chaque domaine SIP avec Skype Entreprise utilisateurs.  <br/> |
|DNS externe  <br/> |Un enregistrement  <br/> |N/A  <br/> |webcon.contoso.com  <br/> |**public :** 131.107.155.20 <br/> **private:** 10.45.16.20 <br/> |Une interface externe pour votre service Edge de conférence web.  <br/> |
|DNS externe  <br/> |Un enregistrement  <br/> |N/A  <br/> |av.contoso.com  <br/> |**public :** 131.107.155.30 <br/> **private:** 10.45.16.30 <br/> |Une interface externe pour votre service Edge A/V.  <br/> |
|DNS externe  <br/> |enregistrement SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour que Skype Entreprise Server clients Lync Server 2013 et Lync Server 2010 fonctionnent en externe. Vous en aurez besoin pour chaque domaine avec Skype Entreprise utilisateurs.  <br/> |
|DNS externe  <br/> |enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour la découverte DNS automatique des partenaires fédérés appelés domaines SIP autorisés. Vous en aurez besoin pour chaque domaine avec Skype Entreprise utilisateurs.  <br/> |
|DNS interne  <br/> |Un enregistrement  <br/> |N/A  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Interface interne pour votre edge consolidé.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Enregistrements DNS pour les scénarios DNS avec mise à l’échelle et serveur Edge matériel

Il s’agit des enregistrements DNS dont vous aurez besoin pour un serveur Edge en utilisant des IP publiques ou privées avec nat. Étant donné qu’il s’agit d’exemples de données, nous allons donner des exemples d’entrées d’entrée pour vous aider à trouver vos propres entrées :
  
- Carte réseau interne :
    
  - Nœud 1 : 172.25.33.10 (aucune passerelle par défaut affectée)
    
  - Nœud 2 : 172.25.33.11 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et tous les réseaux qui contiennent des serveurs exécutant des clients Skype Entreprise Server ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Nœud 1
    
     - Les IP publiques :
    
        - Edge d’accès : 131.107.155.10 (il s’agit de la passerelle principale, avec la passerelle par défaut définie sur votre routeur public, par exemple : 131.107.155.1)
    
        - Serveur Edge de conférence web : 131.107.155.20 (secondaire)
    
        - Edge A/V : 131.107.155.30 (secondaire)
    
          Les adresses IP publiques edge A/V et de conférence web sont des adresses IP supplémentaires (secondaires) dans la section Avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion de zone locale dans Windows Server.
    
    - IPs privés :
    
         - Edge d’accès : 10.45.16.10 (il s’agit de la passerelle principale, avec la passerelle par défaut définie sur votre routeur, par exemple : 10.45.16.1)
    
         - Serveur Edge de conférence web : 10.45.16.20 (secondaire)
    
         - Edge A/V : 10.45.16.30 (secondaire)
    
      Les adresses IP publiques edge A/V et de conférence web sont des adresses IP supplémentaires (secondaires) dans la section Avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion de zone locale dans Windows Server.
    
  - Nœud 2
    
    - Les IP publiques :
    
      - Edge d’accès : 131.107.155.11 (il s’agit de la passerelle principale, avec la passerelle par défaut définie sur votre routeur public, par exemple : 131.107.155.1)
    
      - Serveur Edge de conférence web : 131.107.155.21 (secondaire)
    
      - Edge A/V : 131.107.155.31 (secondaire)
    
      Les adresses IP publiques edge A/V et de conférence web sont des adresses IP supplémentaires (secondaires) dans la section Avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion de zone locale dans Windows Server.
    
  - IPs privés :
    
    - Edge d’accès : 10.45.16.11 (il s’agit de la passerelle principale, avec la passerelle par défaut définie sur votre routeur, par exemple : 10.45.16.1)
    
    - Serveur Edge de conférence web : 10.45.16.21 (secondaire)
    
    - Edge A/V : 10.45.16.31 (secondaire)
    
      Les adresses IP publiques edge A/V et de conférence web sont des adresses IP supplémentaires (secondaires) dans la section Avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion de zone locale dans Windows Server.
    
Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Cela n’est pas recommandé, car vous devrez faire la distinction entre les différents services à l’aide de différents ports (ce que vous pouvez faire dans Skype Entreprise Server), mais certains pare-feu peuvent bloquer les autres ports. Pour plus [d’informations à](edge-environmental-requirements.md#PortFirewallPlan) ce sujet, consultez la section Sur la planification des ports et des pare-feu.
    
- Vous pouvez avoir trois cartes réseau externes au lieu d’une seule et affecter l’une des IP de service à chacune d’elles. Pourquoi faire cela ? Cela séparerait les services et en cas de problème, cela faciliterait la résolution des problèmes et laisserait éventuellement vos autres services continuer à fonctionner pendant que vous résolvez un problème.
    
|**Location**|**Type**|**Port**|**Enregistrement DNS ou FQDN**|**Adresse IP ou FQDN**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Un enregistrement  <br/> |N/A  <br/> |sip.contoso.com  <br/> |**public :** 131.107.155.10 et 131.107.155.11 <br/> **private:** 10.45.16.10 et 10.45.16.11 <br/> |Une interface externe pour votre service Edge d’accès. Vous en aurez besoin pour chaque domaine SIP avec Skype Entreprise utilisateurs.  <br/> |
|DNS externe  <br/> |Un enregistrement  <br/> |N/A  <br/> |webcon.contoso.com  <br/> |**public :** 131.107.155.20 et 131.107.155.21 <br/> **private:** 10.45.16.20 et 10.45.16.21 <br/> |Une interface externe pour votre service Edge de conférence web.  <br/> |
|DNS externe  <br/> |Un enregistrement  <br/> |N/A  <br/> |av.contoso.com  <br/> |**public :** 131.107.155.30 et 131.107.155.31 <br/> **private:** 10.45.16.30 et 10.45.16.31 <br/> |Une interface externe pour votre service Edge A/V.  <br/> |
|DNS externe  <br/> |enregistrement SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour que Skype Entreprise Server clients Lync Server 2013 et Lync Server 2010 fonctionnent en externe. Vous en aurez besoin pour chaque domaine avec Skype Entreprise.  <br/> |
|DNS externe  <br/> |enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour la découverte DNS automatique des partenaires fédérés appelés domaines SIP autorisés. Vous en aurez besoin pour chaque domaine avec Skype Entreprise.  <br/> |
|DNS interne  <br/> |Un enregistrement  <br/> |N/A  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 et 172.25.33.11  <br/> |Interface interne pour votre edge consolidé.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Enregistrement DNS pour la fédération (tous les scénarios)

|**Location**|**Type**|**Port**|**FQDN**|**Enregistrement d’hôte FQDN**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Interface externe du edge d’accès SIP requise pour la découverte DNS automatique. Utilisé par vos autres partenaires de fédération potentiels. Il est également appelé « Autoriser les domaines SIP ». Vous en aurez besoin pour chaque domaine SIP avec Skype Entreprise utilisateurs.  <br/><br/> **Remarque :** Vous aurez besoin de cet enregistrement SRV pour la mobilité et le centre d’échange de notifications Push. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Enregistrements DNS pour le protocole de messagerie et de présence extensible

|**Location**|**Type**|**Port**|**FQDN**|**Adresse IP ou enregistrement d’hôte FQDN**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |Interface proxy XMPP sur votre service Edge d’accès ou pool edge. Vous devez répéter cette procédure si nécessaire pour tous les domaines SIP internes avec des utilisateurs Skype Entreprise Server activés, où le contact avec des contacts XMPP est autorisé via :  <br/> • une stratégie globale  <br/> • une stratégie de site dans laquelle l’utilisateur est activé  <br/> • une stratégie utilisateur appliquée à l’Skype Entreprise Server utilisateur activé  <br/> Une stratégie XMPP autorisée doit également être configurée dans la stratégie utilisateurs fédérés XMPP.  <br/> |
|DNS externe  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Adresse IP du service Edge d’accès sur le serveur Edge ou le pool edge hébergeant votre service proxy XMPP  <br/> |Cela pointe vers le service Edge d’accès sur le serveur Edge ou le pool edge qui héberge le service proxy XMPP. En règle générale, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).  <br/> |
   
> [!NOTE]
> Les passerelles et les proxies XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. Pour [plus d’informations, voir](../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.

## <a name="certificate-planning"></a>Planification de certificat
<a name="CertPlan"> </a>

Skype Entreprise Server utilise des certificats pour sécuriser et chiffrer les communications entre les serveurs et de serveur à client. Comme vous vous y attendiez, vos certificats doivent avoir des enregistrements DNS pour vos serveurs qui correspondent à n’importe quel nom de sujet (SN) et autre nom du sujet (SAN) sur vos certificats. Cela prendra du travail maintenant, à l’étape de planification, pour vous assurer que vous avez les FQDN enregistrés dans DNS pour les entrées SN et SAN pour vos certificats.
  
Nous aborderons séparément les besoins des certificats externes et internes, puis examinerons un tableau fournissant les conditions requises pour les deux.
  
### <a name="external-certificates"></a>Certificats externes

Au minimum, le certificat affecté à vos interfaces de serveur Edge externes doit être fourni par une autorité de certification publique. Nous ne pouvons pas vous recommander une ca spécifique, mais nous avons une liste de ca, partenaires de certificats [de communications](../../../SfbPartnerCertification/certification/services-ssl.md) unifiées, que vous pouvez consulter pour voir si votre ca préférée est répertoriée.
  
Quand devez-vous envoyer une demande à une ca pour ce certificat public et comment le faire ? Il existe deux façons d’effectuer cette tâche :
  
- Vous pouvez passer par l’installation de Skype Entreprise Server, puis le déploiement du serveur Edge. L Skype Entreprise Server de déploiement d’entreprise aura une étape pour générer une demande de certificat, que vous pouvez ensuite envoyer à votre cae choisie.
    
- Vous pouvez également utiliser Windows PowerShell pour générer cette demande, si celle-ci est plus en ligne avec les besoins de votre entreprise ou votre stratégie de déploiement.
    
- Enfin, votre ca peut avoir son propre processus d’envoi, qui peut également impliquer Windows PowerShell ou une autre méthode. Dans ce cas, vous devez vous appuyer sur leur documentation, en plus des informations fournies ici pour votre référence.
    
Une fois que vous avez obtenu le certificat, vous devez continuer et l’affecter à ces services dans Skype Entreprise Server :
  
- Interface de service Edge d’accès
    
- Interface de service Edge de conférence web
    
- Service d’authentification audio/vidéo (ne le confondez pas avec le service Edge A/V, car il n’utilise pas de certificat pour chiffrer les flux audio et vidéo)
    
> [!IMPORTANT]
> Tous les serveurs Edge (s’ils appartiennent au même pool de serveurs Edge) doivent avoir le même certificat avec la même clé privée pour le service d’authentification du relais multimédia. 
  
### <a name="internal-certificates"></a>Certificats internes

Pour l’interface interne du serveur Edge, vous pouvez utiliser un certificat public d’une ca publique ou un certificat émis par l’ac de votre organisation. N’oubliez pas que le certificat interne utilise une entrée SN et aucune entrée SAN. Vous n’avez donc pas à vous soucier du san du tout sur le certificat interne.
  
### <a name="required-certificates-table"></a>Table Certificats requis

Nous avons un tableau ici pour vous aider à répondre à vos demandes. Les entrées de nom de domaine domaine (FQDN) sont ici uniquement pour les exemples de domaines. Vous devrez effectuer des demandes en fonction de vos propres domaines privés et publics, mais voici un guide de ce que nous avons utilisé :
  
- contoso.com<span></span> : FQDN public
    
- fabrikam.com<span></span> : deuxième nom de domaine général (ajouté en tant que démonstration des demandes si vous avez plusieurs domaines SIP)
    
- Contoso.net<span></span> : domaine interne
    
#### <a name="edge-certificate-table"></a>Table Certificat Edge

Quel que soit le serveur Edge ou le pool de serveurs Edge que vous faites, voici ce dont vous aurez besoin pour votre certificat :
  
|**Composant**|**Nom du sujet (SN)**|**Autres noms du sujet (SAN)/ordre**|**Notes**|
|:-----|:-----|:-----|:-----|
|Edge externe  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Il s’agit du certificat que vous devez demander à une ca publique. Il doit être affecté aux interfaces Edge externes pour les opérations suivantes :  <br/> • Edge d’accès  <br/> • Serveur Edge de conférence web  <br/> • Authentification audio/vidéo  <br/> <br/>La bonne nouvelle est que les réseaux sans sont automatiquement ajoutés à votre demande de certificat, et par conséquent à votre certificat après l’envoi de la demande, en fonction de ce que vous avez défini pour ce déploiement dans le Générateur de topologies. Vous devez uniquement ajouter des entrées SAN pour les domaines SIP supplémentaires ou d’autres entrées que vous devez prendre en charge. Pourquoi les sip.contoso.com sont-ils répliqués dans cette instance ? Cela se produit également automatiquement et est nécessaire pour que les choses fonctionnent correctement.  <br/><br/> **Remarque :** Ce certificat peut également être utilisé pour la connectivité de messagerie instantanée publique. Vous n’avez pas besoin d’en faire autrement, mais dans les versions précédentes de cette documentation, elle était répertoriée en tant que tableau distinct, ce qui n’est plus le cas maintenant. <br/> |
|Edge interne  <br/> |sfbedge.contoso.com  <br/> |N/A  <br/> |Vous pouvez obtenir ce certificat auprès d’une ca publique ou interne. Il doit contenir la référence EKU du serveur (utilisation améliorée des clés) et vous l’affecterez à l’interface Edge interne.  <br/> |
   
Si vous avez besoin d’un certificat pour le protocole XMPP (Extensible Messaging and Presence Protocol), il sera identique aux entrées de la table Edge externe ci-dessus, mais aura les deux entrées SAN supplémentaires suivantes :
  
- xmpp.<span></span> contoso.com<span></span>
    
- \*.contoso.com<span></span>
    
N’oubliez pas que XMPP est actuellement pris en charge uniquement dans Skype Entreprise Server pour Google Talk. Si vous souhaitez ou avez besoin de l’utiliser pour autre chose, vous devez confirmer cette fonctionnalité auprès du fournisseur tiers impliqué.
  
## <a name="port-and-firewall-planning"></a>Planification des ports et des pare-feu
<a name="PortFirewallPlan"> </a>

La bonne planification des ports et des pare-feu pour Skype Entreprise Server déploiements de serveurs Edge peut vous éviter des jours ou des semaines de dépannage et de contrainte. Par conséquent, nous allons ré lister quelques tableaux qui indiqueront l’utilisation de notre protocole et les ports que vous devez avoir ouverts, entrants et sortants, à la fois pour les scénarios NAT et IP publics. Nous allons également avoir des tableaux distincts pour les scénarios d’équilibrage de la charge matérielle (HLB) et des instructions supplémentaires à ce niveau. Pour en savoir plus à partir de là, nous avons également des [scénarios](scenarios.md) de serveur Edge dans Skype Entreprise Server vous pouvez vérifier si vous avez des problèmes de déploiement particuliers.
  
### <a name="general-protocol-usage"></a>Utilisation générale du protocole

Avant d’examiner les tableaux récapitulatifs des pare-feu internes et externes, examinons également le tableau suivant :
  
|**Transport audio/vidéo**|**Utilisation**|
|:-----|:-----|
|UDP  <br/> |Protocole de couche de transport préféré pour l’audio et la vidéo.  <br/> |
|TCP  <br/> |Protocole de couche de transport de fallback pour l’audio et la vidéo.  <br/> Protocole de couche transport requis pour le partage d’application Skype Entreprise Server, Lync Server 2013 et Lync Server 2010.  <br/> Protocole de couche transport requis pour le transfert de fichiers vers Skype Entreprise Server, Lync Server 2013 et Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tableau récapitulatif du pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiennent des informations pour les utilisateurs qui utilisent des adresses IP privées avec nat, ainsi que les personnes utilisant des adresses IP publiques. Cela couvrira toutes les permutations dans nos [scénarios](scenarios.md) de serveur Edge dans Skype Entreprise Server section.
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non pris en charge Skype Entreprise Server 2019 |TCP  <br/> |5269  <br/> |N’importe lequel  <br/> |Service proxy XMPP (partage une adresse IP avec le service Edge d’accès  <br/> |Le service proxy XMPP accepte le trafic provenant de contacts XMPP dans les fédérations XMPP définies.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N’importe lequel  <br/> |Révocation de certificats, vérification et récupération de la CRL.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N’importe lequel  <br/> |Requête DNS sur TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N’importe lequel  <br/> |Requête DNS sur UDP.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |Trafic SIP client à serveur pour l’accès des utilisateurs externes.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |Pour la connectivité de messagerie instantanée publique et fédérée à l’aide de SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N’importe lequel  <br/> |Pour la connectivité de messagerie instantanée publique et fédérée à l’aide de SIP.  <br/> |
|Conférence web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge de conférence web de serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge de conférence web du serveur Edge <br/> |Média de conférence web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge A/V du serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |N’importe lequel  <br/> |Il est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge A/V du serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |N’importe lequel  <br/> |Il est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge A/V du serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |N’importe lequel  <br/> |3478 sortant est :  <br/> • Utilisé par Skype Entreprise Server pour déterminer la version du serveur Edge avec qui il communique.  <br/> • Utilisé pour le trafic multimédia entre les serveurs Edge.  <br/> • Requis pour la fédération avec Lync Server 2010.  <br/> • Nécessaire si plusieurs pools Edge sont déployés au sein de votre organisation.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge A/V du serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge A/V du serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge A/V du serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |N’importe lequel  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tableau récapitulatif du pare-feu de port interne

|**Protocol (Protocole)**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des façons suivantes d’exécution du service de passerelle XMPP :  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic XMPP sortant à partir de votre service de passerelle XMPP en cours d’exécution sur votre serveur frontal ou pool frontal.  <br/> **Remarque :** Les passerelles et les proxies XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. Pour [plus d’informations, voir](../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Tout :  <br/> • Directeur  <br/> • Pool directeur  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic SIP sortant de votre directeur, pool directeur, serveur frontal ou pool frontal vers votre interface interne de serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interne du serveur Edge  <br/> |Tout :  <br/> • Directeur  <br/> • Pool directeur  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Trafic SIP entrant vers votre directeur, pool directeur, serveur frontal ou pool frontal à partir de votre interface interne de serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Tout :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal  <br/>  dans votre pool frontal <br/> |Interface interne du serveur Edge  <br/> |Trafic de conférence web à partir de votre serveur frontal ou de chaque serveur frontal (si vous avez un pool frontal) vers votre interface interne de serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Tout :  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> • Tout Survivable Branch Appliance utilisant ce serveur Edge  <br/> • Tout serveur Survivable Branch Server utilisant ce serveur Edge  <br/> |Interface interne du serveur Edge  <br/> |Authentification des utilisateurs A/V à partir de votre serveur frontal ou pool frontal, ou de votre Survivable Branch Appliance ou survivable Branch Server, à l’aide de votre serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès de retour pour le transfert multimédia A/V entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou survivable Branch Server, si la communication UDP ne fonctionne pas. TCP est ensuite utilisé pour les transferts de fichiers et le partage de bureau.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Tout :  <br/> • Serveur frontal qui contient le magasin central de gestion  <br/> • Pool frontal qui contient le magasin central de gestion  <br/> |Interface interne du serveur Edge  <br/> |Réplication des modifications de votre magasin central de gestion vers votre serveur Edge.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur du service de journalisation centralisée à l’aide des cmdlets Skype Entreprise Server Management Shell et du service de journalisation centralisée, des commandes de ligne de commande ClsController (ClsController.exe) ou agent (ClsAgent.exe) et de la collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur du service de journalisation centralisée à l’aide des cmdlets Skype Entreprise Server Management Shell et du service de journalisation centralisée, des commandes de ligne de commande ClsController (ClsController.exe) ou agent (ClsAgent.exe) et de la collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur du service de journalisation centralisée à l’aide des cmdlets Skype Entreprise Server Management Shell et du service de journalisation centralisée, des commandes de ligne de commande ClsController (ClsController.exe) ou agent (ClsAgent.exe) et de la collection de journaux.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Équilibreurs de charge matérielle pour les tables de ports Edge

Nous accordons aux équilibreurs de charge matérielle (HLB) et aux ports Edge leur propre section, car les choses sont un peu plus complexes avec le matériel supplémentaire. Reportez-vous aux tableaux ci-dessous pour obtenir des conseils pour ce scénario particulier :
  
#### <a name="external-port-firewall-summary-table"></a>Tableau récapitulatif du pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiennent des informations pour les utilisateurs qui utilisent des adresses IP privées avec nat, ainsi que les personnes utilisant des adresses IP publiques. Cela couvrira toutes les permutations dans nos [scénarios](scenarios.md) de serveur Edge dans Skype Entreprise Server section.
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Adresse IP publique du service Edge d’accès au serveur Edge  <br/> |N’importe lequel  <br/> |Révocation de certificats, vérification et récupération de la CRL.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |Adresse IP publique du service Edge d’accès au serveur Edge  <br/> |N’importe lequel  <br/> |Requête DNS sur TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Adresse IP publique du service Edge d’accès au serveur Edge  <br/> |N’importe lequel  <br/> |Requête DNS sur UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Adresse IP du service Edge A/V du serveur Edge  <br/> |N’importe lequel  <br/> |Il est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |N’importe lequel  <br/> |Il est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |N’importe lequel  <br/> |3478 sortant est :  <br/> • Utilisé par Skype Entreprise Server pour déterminer la version du serveur Edge avec qui il communique.  <br/> • Utilisé pour le trafic multimédia entre les serveurs Edge.  <br/> • Obligatoire pour la fédération.  <br/> • Nécessaire si plusieurs pools Edge sont déployés au sein de votre organisation.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |N’importe lequel  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |N’importe lequel  <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tableau récapitulatif du pare-feu de port interne

|**Protocol (Protocole)**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des façons suivantes d’exécution du service de passerelle XMPP :  <br/> • Serveur frontal  <br/> • Adresse IP ip du pool frontal exécutant le service de passerelle XMPP  <br/> |Interface interne du serveur Edge  <br/> |Trafic XMPP sortant à partir de votre service de passerelle XMPP en cours d’exécution sur votre serveur frontal ou pool frontal.  <br/><br/> **Remarque :** Les passerelles et les proxies XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. Pour [plus d’informations, voir](../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP. |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Tout :  <br/> • Serveur frontal qui contient le magasin central de gestion  <br/> • Pool frontal qui contient le magasin central de gestion  <br/> |Interface interne du serveur Edge  <br/> |Réplication des modifications de votre magasin central de gestion vers votre serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Tout :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal de votre pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic de conférence web à partir de votre serveur frontal ou de chaque serveur frontal (si vous avez un pool frontal) vers votre interface interne de serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Tout :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal de votre pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Tout :  <br/> • Serveur frontal  <br/> • Chaque serveur frontal de votre pool  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès de retour pour le transfert multimédia A/V entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou survivable Branch Server, si la communication UDP ne fonctionne pas. TCP est ensuite utilisé pour les transferts de fichiers et le partage de bureau.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur du service de journalisation centralisée à l’aide des cmdlets Skype Entreprise Server Management Shell et du service de journalisation centralisée, des commandes de ligne de commande ClsController (ClsController.exe) ou agent (ClsAgent.exe) et de la collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur du service de journalisation centralisée à l’aide des cmdlets Skype Entreprise Server Management Shell et du service de journalisation centralisée, des commandes de ligne de commande ClsController (ClsController.exe) ou agent (ClsAgent.exe) et de la collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur du service de journalisation centralisée à l’aide des cmdlets Skype Entreprise Server Management Shell et du service de journalisation centralisée, des commandes de ligne de commande ClsController (ClsController.exe) ou agent (ClsAgent.exe) et de la collection de journaux.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IPS virtuels d’interface externe

|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non pris en charge dans Skype pour Businesss Server 2019 |TCP  <br/> |5269  <br/> |N’importe lequel  <br/> |Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)  <br/> |Le service proxy XMPP accepte le trafic provenant de contacts XMPP dans les fédérations XMPP définies.  <br/> |
|XMPP  <br/>Non pris en charge dans Skype pour Businesss Server 2019 |TCP  <br/> |5269  <br/> |Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)  <br/> |N’importe lequel  <br/> |Le service proxy XMPP envoie le trafic des contacts XMPP dans les fédérations XMPP définies.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |Trafic SIP client à serveur pour l’accès des utilisateurs externes.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |Pour la connectivité de messagerie instantanée publique et fédérée à l’aide de SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge d’accès au serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N’importe lequel  <br/> |Pour la connectivité de messagerie instantanée publique et fédérée à l’aide de SIP.  <br/> |
|Conférence web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge de conférence web de serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge de conférence web du serveur Edge <br/> |Média de conférence web.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge A/V du serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |Négociation STUN/TURN des candidats sur UDP sur le port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |**Adresse IP privée à l’aide de NAT :** Service Edge A/V du serveur Edge <br/> **ADRESSE IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |Négociation STUN/TURN des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IPS virtuels de l’interface interne

Nos recommandations ici vont être légèrement différentes. En réalité, dans une situation d’programme d’acheminement de l’programme d’acheminement, nous vous recommandons uniquement d’avoir un routage via une vip interne dans les circonstances suivantes :
  
- Si vous utilisez la messagerie Exchange 2007 ou Exchange 2010.
    
- Si vous avez des clients hérités à l’aide du edge.
    
Le tableau suivant donne des conseils pour ces scénarios, mais dans le cas contraire, vous devriez être en mesure de dépendre du magasin central de gestion (CMS) pour router le trafic vers le serveur Edge qu’il connaît (cela nécessite bien entendu que cms soit tenu à jour sur les informations du serveur Edge).
  
|**Protocol (Protocole)**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Tout :  <br/> • Directeur  <br/> • Adresse IP ip du pool directeur  <br/> • Serveur frontal  <br/> • Adresse IP ip du pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic SIP sortant à partir de votre adresse IP ip du directeur, du pool directeur, du serveur frontal ou de l’adresse IP ip du pool frontal vers votre interface interne du serveur Edge.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface VIP interne du serveur Edge  <br/> |Tout :  <br/> • Directeur  <br/> • Adresse IP ip du pool directeur  <br/> • Serveur frontal  <br/> • Adresse IP ip du pool frontal  <br/> |Trafic SIP entrant vers votre adresse IP ip du directeur, du pool directeur, du serveur frontal ou du pool frontal à partir de votre interface interne du serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Tout :  <br/> • Adresse IP du serveur frontal  <br/> • Adresse IP du pool frontal  <br/> • Tout Survivable Branch Appliance utilisant ce serveur Edge  <br/> • Tout serveur Survivable Branch Server utilisant ce serveur Edge  <br/> |Interface interne du serveur Edge  <br/> |Authentification des utilisateurs A/V à partir de votre serveur frontal ou pool frontal, ou de votre Survivable Branch Appliance ou survivable Branch Server, à l’aide de votre serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |N’importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Chemin d’accès préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |N’importe lequel  <br/> |Interface VIP interne du serveur Edge  <br/> |Chemin d’accès de retour pour le transfert multimédia A/V entre vos utilisateurs internes et externes si la communication UDP ne fonctionne pas. TCP est ensuite utilisé pour les transferts de fichiers et le partage de bureau.  <br/> |