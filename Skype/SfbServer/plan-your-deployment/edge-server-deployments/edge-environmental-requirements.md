---
title: Conditions ambiantes de serveur Edge dans Skype entreprise Server
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
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Résumé : Découvrez les exigences environnementales pour le serveur Edge dans Skype entreprise Server.'
ms.openlocfilehash: 8e2ec6d2afc53648fe50af4cd5ab02ad21d11643
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219924"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Conditions ambiantes de serveur Edge dans Skype entreprise Server
 
**Résumé :** En savoir plus sur les exigences environnementales pour le serveur Edge dans Skype entreprise Server.
  
Un grand nombre de planifications et de préparations doivent avoir lieu en dehors de l’environnement de serveur Edge de Skype entreprise Server. Dans cet article, nous allons examiner les préparations qui doivent être effectuées dans l’environnement de l’organisation, conformément à notre liste ci-dessous :
  
- [Planification de la topologie](edge-environmental-requirements.md#TopoPlan)
    
- [Planification DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Planification de certificat](edge-environmental-requirements.md#CertPlan)
    
- [Planification des ports et des pare-feu](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planification de la topologie
<a name="TopoPlan"> </a>

Les topologies de serveur Edge Skype entreprise Server peuvent utiliser les éléments suivants :
  
- Adresses IP publiques routables.
    
- Adresses IP privées non routables, si la traduction d’adresses réseau (NAT) **symétrique** est utilisée.
    
> [!TIP]
> Votre serveur Edge peut être configuré pour utiliser une adresse IP unique avec des ports distincts pour chaque service, ou il peut utiliser des adresses IP distinctes pour chaque service, mais utiliser le même port par défaut (par défaut, le port TCP 443). Vous trouverez plus d’informations dans la section exigences relatives aux adresses IP, ci-dessous. 
  
Si vous choisissez des adresses IP privées non routables avec NAT, rappelez-vous des points suivants :
  
- Vous devez utiliser des adresses IP privées routables sur **les trois** interfaces externes.
    
- Vous devez configurer la traduction d’adresses réseau **symétrique** pour le trafic entrant et sortant. Le protocole NAT symétrique est le seul que vous pouvez utiliser avec le serveur Edge de Skype entreprise Server.
    
- Configurez votre NAT de façon à ne pas modifier les adresses source entrantes. Le service Edge A/V doit pouvoir recevoir l’adresse source entrante pour trouver le chemin multimédia optimal.
    
- Vos serveurs Edge doivent être en mesure de communiquer les uns avec les autres à partir de leurs adresses IP de serveur Edge A/V publiques. Votre pare-feu doit autoriser ce trafic.
    
- La conversion d’adresses réseau ne peut être utilisée **que** pour les serveurs Edge consolidés mis à l’ampleur si vous utilisez l’équilibrage de charge DNS. Si vous utilisez l’équilibrage de la charge matérielle (charge matérielle), vous devez utiliser des adresses IP publiquement routables **sans** NAT.
    
Vous n’avez aucun problème à faire en sorte que votre accès, la conférence Web et les interfaces de serveur Edge A/V derrière un routeur ou un pare-feu effectuant une traduction d’adresses réseau symétrique à la fois pour les topologies de serveurs Edge consolidées uniques et à l’unité (à condition que vous n’utilisiez pas l’équilibrage de la charge matérielle).
  
### <a name="summary-of-edge-server-topology-options"></a>Résumé des options de topologie de serveur Edge

Plusieurs options de topologie sont disponibles pour les déploiements de serveur Edge de Skype entreprise Server :
  
- Serveur Edge consolidé unique avec adresses IP privées et NAT
    
- Serveur Edge consolidé unique avec adresses IP publiques
    
- Serveur Edge consolidé ajusté avec adresses IP privées et NAT
    
- Serveur Edge consolidé ajusté avec des adresses IP publiques
    
- Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle
    
Pour vous aider à choisir un, nous disposons du tableau suivant qui fournit un résumé des options dont vous disposez pour chaque topologie :
  
|**Topologie**|**Disponibilité élevée**|**Enregistrements DNS supplémentaires requis pour le serveur Edge externe dans le pool de serveurs Edge ?**|**Basculement Edge pour les sessions Skype entreprise Server**|**Basculement de serveur Edge pour les sessions de Fédération Skype entreprise Server**|
|:-----|:-----|:-----|:-----|:-----|
|Serveur Edge consolidé unique avec adresses IP privées et NAT  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Serveur Edge consolidé unique avec adresses IP publiques  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Serveur Edge consolidé ajusté avec des adresses IP privées et NAT (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui&sup1 ;  <br/> |
|Serveur Edge consolidé ajusté avec des adresses IP publiques (charge DNS équilibrée)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui&sup1 ;  <br/> |
|Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle  <br/> |Oui  <br/> |Non (un enregistrement DNS A par VIP)  <br/> |Oui  <br/> |Oui  <br/> |
   
&sup1 ; Le basculement de la messagerie unifiée Exchange (MU) à distance à l’aide de l’équilibrage de charge DNS nécessite Exchange 2013 ou une version ultérieure.
  
### <a name="ip-address-requirements"></a>Exigences en matière d’adresse IP

Sur un niveau fondamental, trois services ont besoin d’adresses IP ; Service Edge d’accès, service Edge de conférence Web et service Edge A/V. Vous avez la possibilité d’utiliser trois adresses IP, une pour chacun des services, ou vous pouvez en utiliser une et choisir de placer chaque service sur un autre port (vous pouvez consulter la section relative à la [planification des ports et des pare-feu](edge-environmental-requirements.md#PortFirewallPlan) pour en savoir plus sur une partie de celle-ci). Pour un environnement de serveur Edge consolidé unique, c’est très largement.
  
> [!NOTE]
> Comme indiqué ci-dessus, vous pouvez choisir de disposer d’une adresse IP pour les trois services et de les exécuter sur des ports différents. Mais pour être clair, nous vous déconseillons de le faire. Si vos clients ne peuvent pas accéder aux autres ports que vous utiliserez dans ce scénario, ils ne pourront pas accéder à l’ensemble des fonctionnalités de votre environnement Edge. 
  
Cela peut être un peu plus compliqué avec des topologies consolidées mises à l’échelle, nous allons donc examiner certaines tables qui présentent les exigences en matière d’adresse IP, en gardant à l’esprit que les principaux points de décision pour la sélection de la topologie sont la haute disponibilité et l’équilibrage de la charge. Les besoins en matière de haute disponibilité peuvent influer sur votre choix d’équilibrage de charge (nous en parlerons plus en détail après les tableaux).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Exigences en matière d’adresses IP pour le serveur Edge consolidé ajusté (adresse IP par rôle)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses IP requises pour l’équilibrage de la charge DNS**|**Nombre d’adresses IP requises pour l’équilibrage de la charge matérielle**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (1 par adresse IP virtuelle) + 6  <br/> |
|3   <br/> |9   <br/> |3 (1 par adresse IP virtuelle) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 par adresse IP virtuelle) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 par adresse IP virtuelle) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Configuration requise pour l’adresse IP pour le serveur Edge consolidé de l’envergure (adresse IP unique pour tous les rôles)

|**Nombre de serveurs Edge par pool**|**Nombre d’adresses IP requises pour l’équilibrage de la charge DNS**|**Nombre d’adresses IP requises pour l’équilibrage de la charge matérielle**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (1 par adresse IP virtuelle) + 2  <br/> |
|3   <br/> |3   <br/> |1 (1 par adresse IP virtuelle) + 3  <br/> |
|4   <br/> |4   <br/> |1 (1 par adresse IP virtuelle) + 4  <br/> |
|5   <br/> |disque  <br/> |1 (1 par adresse IP virtuelle) + 5  <br/> |
   
Examinons quelques éléments supplémentaires à prendre en compte lors de la planification.
  
- **Haute disponibilité**: Si vous avez besoin d’une haute disponibilité dans votre déploiement, vous devez déployer au moins deux serveurs Edge dans un pool. Notez qu’un seul pool de serveurs Edge prend en charge jusqu’à 12 serveurs Edge (bien que le générateur de topologie vous autorise à ajouter jusqu’à 20, ce qui n’est pas testé ou pris en charge, nous vous recommandons donc de ne pas le faire). Si vous avez besoin de plus de 12 serveurs Edge, vous devez créer des pools de serveurs Edge supplémentaires pour ceux-ci.
    
- **Équilibrage**de la charge matérielle : nous vous recommandons d’utiliser l’équilibrage de charge DNS pour la plupart des scénarios. L’équilibrage de la charge matérielle est bien évidemment pris en charge, mais en particulier s’il est requis pour un scénario unique sur l’équilibrage de la charge DNS :
    
  - Accès externe à Exchange 2007 ou Exchange 2010 (sans service de messagerie unifiée).
    
- **Équilibrage de la charge DNS**: pour la messagerie unifiée, Exchange 2010 SP1 et les versions ultérieures peuvent être pris en charge par l’équilibrage de charge DNS. Notez que si vous devez utiliser l’équilibrage de charge DNS pour une version antérieure d’Exchange, cela fonctionnera, mais tout le trafic correspondant sera dirigé vers le premier serveur du pool et, s’il n’est pas disponible, le trafic échouera.
    
    L’équilibrage de charge DNS est également recommandé si vous vous fédérer avec des entreprises en utilisant les éléments suivants :
- Skype entreprise Server 2015 :
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 ou Office 365
- Skype entreprise Server 2019 :
    - Lync Server 2013
    - Skype Entreprise Server 2015
    - Microsoft 365 ou Office 365
    
## <a name="dns-planning"></a>Planification DNS
<a name="DNSPlan"> </a>

En ce qui concerne le déploiement de serveur Edge Skype entreprise Server, il est essentiel de préparer correctement le DNS. Les enregistrements corrects étant en place, le déploiement est beaucoup plus simple. Nous espérons que vous avez choisi une topologie dans la section ci-dessus, puisque nous allons procéder à une vue d’ensemble, puis répertorier quelques tableaux détaillant les enregistrements DNS pour ces scénarios. Nous aurons également une [planification de DNS de serveur Edge avancé pour Skype entreprise Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) pour une lecture plus approfondie, si vous en avez besoin.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Enregistrements DNS pour les scénarios de serveur Edge consolidé unique

Il s’agit des enregistrements DNS dont vous aurez besoin pour un serveur Edge unique utilisant des adresses IP publiques ou des adresses IP privées avec NAT. Étant donné qu’il s’agit d’exemples de données, nous allons donner des exemples de IPs afin que vous puissiez utiliser plus facilement vos propres entrées :
  
- Carte réseau interne : 172.25.33.10 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant Skype entreprise Server ou des clients Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Adresses IP publiques :
    
  - Serveur Edge d’accès : 131.107.155.10 (il s’agit de la configuration principale, avec la passerelle par défaut définie sur votre routeur public, par exemple : 131.107.155.1)
    
  - Serveur Edge de conférence Web : 131.107.155.20 (secondaire)
    
  - Serveur Edge A/V : 131.107.155.30 (secondaire)
    
  Les adresses IP publiques de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires (secondaires) dans la section avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion au réseau local dans Windows Server.
    
  - Adresses IP privées :
    
  - Access Edge : 10.45.16.10 (il s’agit de la configuration principale, avec la passerelle par défaut définie sur votre routeur, par exemple : 10.45.16.1)
    
  - Serveur Edge de conférence Web : 10.45.16.20 (secondaire)
    
  - Serveur Edge A/V : et 10.45.16.30 (secondaire)
    
Les adresses IP publiques de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires (secondaires) dans la section avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion au réseau local dans Windows Server.
  
> [!TIP]
>Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Nous vous déconseillons de le faire, car vous devrez faire la différence entre les services les plus utilisés à l’aide de différents ports (ce que vous pouvez faire dans Skype entreprise Server), mais certains pare-feu peuvent bloquer les autres ports. Pour plus d’informations à ce sujet, consultez la section [planification des ports et des pare-feu](edge-environmental-requirements.md#PortFirewallPlan) .
    
- Vous pouvez avoir trois cartes réseau externes au lieu d’une, et affecter l’une des adresses IP de service à chacune d’entre elles. Pourquoi procéder ? Il sépare les services et en cas de problème, cela permet de faciliter la résolution des problèmes et de laisser vos autres services continuer à fonctionner pendant que vous résolvez un problème.
    
|**Emplacement**|**Type**|**Port**|**Nom de domaine complet ou enregistrement DNS**|**Adresse IP ou nom de domaine complet**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Enregistrement A  <br/> |N/A  <br/> |sip.contoso.com  <br/> |**public :** 131.107.155.10 <br/> **privé :** 10.45.16.10 <br/> |Une interface externe pour votre service Edge d’accès. Vous en aurez besoin un pour chaque domaine SIP avec des utilisateurs de Skype entreprise.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |N/A  <br/> |webcon.contoso.com  <br/> |**public :** 131.107.155.20 <br/> **privé :** 10.45.16.20 <br/> |Une interface externe pour votre service Edge de conférence Web.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |N/A  <br/> |av.contoso.com  <br/> |**public :** 131.107.155.30 <br/> **privé :** et 10.45.16.30 <br/> |Une interface externe pour votre service Edge A/V.  <br/> |
|DNS externe  <br/> |enregistrement SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour que les clients Skype entreprise Server, Lync Server 2013 et Lync Server 2010 fonctionnent en externe. Vous en aurez besoin un pour chaque domaine avec des utilisateurs de Skype entreprise.  <br/> |
|DNS externe  <br/> |enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour la découverte DNS automatique des partenaires fédérés appelés domaines SIP autorisés. Vous en aurez besoin un pour chaque domaine avec des utilisateurs de Skype entreprise.  <br/> |
|DNS interne  <br/> |Enregistrement A  <br/> |N/A  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Interface interne de votre serveur Edge consolidé.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Enregistrements DNS pour les scénarios de serveur Edge DNS et matériel à l’adaptation

Il s’agit des enregistrements DNS dont vous aurez besoin pour un serveur Edge unique utilisant des adresses IP publiques ou des adresses IP privées avec NAT. Étant donné qu’il s’agit d’exemples de données, nous allons donner des exemples de IPs afin que vous puissiez utiliser plus facilement vos propres entrées :
  
- Carte réseau interne :
    
  - Nœud 1:172.25.33.10 (aucune passerelle par défaut affectée)
    
  - Nœud 2:172.25.33.11 (aucune passerelle par défaut affectée)
    
    > [!NOTE]
    > Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant Skype entreprise Server ou des clients Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0). 
  
- Carte réseau externe :
    
  - Nœud 1
    
     - Adresses IP publiques :
    
        - Serveur Edge d’accès : 131.107.155.10 (il s’agit de la configuration principale, avec la passerelle par défaut définie sur votre routeur public, par exemple : 131.107.155.1)
    
        - Serveur Edge de conférence Web : 131.107.155.20 (secondaire)
    
        - Serveur Edge A/V : 131.107.155.30 (secondaire)
    
          Les adresses IP publiques de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires (secondaires) dans la section avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion au réseau local dans Windows Server.
    
    - Adresses IP privées :
    
         - Access Edge : 10.45.16.10 (il s’agit de la configuration principale, avec la passerelle par défaut définie sur votre routeur, par exemple : 10.45.16.1)
    
         - Serveur Edge de conférence Web : 10.45.16.20 (secondaire)
    
         - Serveur Edge A/V : et 10.45.16.30 (secondaire)
    
      Les adresses IP publiques de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires (secondaires) dans la section avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion au réseau local dans Windows Server.
    
  - Nœud 2
    
    - Adresses IP publiques :
    
      - Serveur Edge d’accès : 131.107.155.11 (il s’agit de la configuration principale, avec la passerelle par défaut définie sur votre routeur public, par exemple : 131.107.155.1)
    
      - Serveur Edge de conférence Web : 131.107.155.21 (secondaire)
    
      - Serveur Edge A/V : 131.107.155.31 (secondaire)
    
      Les adresses IP publiques de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires (secondaires) dans la section avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion au réseau local dans Windows Server.
    
  - Adresses IP privées :
    
    - Access Edge : 10.45.16.11 (il s’agit de la configuration principale, avec la passerelle par défaut définie sur votre routeur, par exemple : 10.45.16.1)
    
    - Serveur Edge de conférence Web : 10.45.16.21 (secondaire)
    
    - Serveur Edge A/V : 10.45.16.31 (secondaire)
    
      Les adresses IP publiques de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires (secondaires) dans la section avancé des propriétés du protocole Internet version 4 (TCP/IPv4) et du protocole Internet version 6 (TCP/IPv6) des propriétés de connexion au réseau local dans Windows Server.
    
Il existe d’autres configurations possibles ici :
  
- Vous pouvez utiliser une adresse IP sur la carte réseau externe. Nous vous déconseillons de le faire, car vous devrez faire la différence entre les services les plus utilisés à l’aide de différents ports (ce que vous pouvez faire dans Skype entreprise Server), mais certains pare-feu peuvent bloquer les autres ports. Pour plus d’informations à ce sujet, consultez la section [planification des ports et des pare-feu](edge-environmental-requirements.md#PortFirewallPlan) .
    
- Vous pouvez avoir trois cartes réseau externes au lieu d’une, et affecter l’une des adresses IP de service à chacune d’entre elles. Pourquoi procéder ? Il sépare les services et en cas de problème, cela permet de faciliter la résolution des problèmes et de laisser vos autres services continuer à fonctionner pendant que vous résolvez un problème.
    
|**Emplacement**|**Type**|**Port**|**Nom de domaine complet ou enregistrement DNS**|**Adresse IP ou nom de domaine complet**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |Enregistrement A  <br/> |N/A  <br/> |sip.contoso.com  <br/> |**public :** 131.107.155.10 et 131.107.155.11 <br/> **privé :** 10.45.16.10 et 10.45.16.11 <br/> |Une interface externe pour votre service Edge d’accès. Vous en aurez besoin un pour chaque domaine SIP avec des utilisateurs de Skype entreprise.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |N/A  <br/> |webcon.contoso.com  <br/> |**public :** 131.107.155.20 et 131.107.155.21 <br/> **privé :** 10.45.16.20 et 10.45.16.21 <br/> |Une interface externe pour votre service Edge de conférence Web.  <br/> |
|DNS externe  <br/> |Enregistrement A  <br/> |N/A  <br/> |av.contoso.com  <br/> |**public :** 131.107.155.30 et 131.107.155.31 <br/> **privé :** et 10.45.16.30 et 10.45.16.31 <br/> |Une interface externe pour votre service Edge A/V.  <br/> |
|DNS externe  <br/> |enregistrement SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour que les clients Skype entreprise Server, Lync Server 2013 et Lync Server 2010 fonctionnent en externe. Vous en aurez besoin un pour chaque domaine avec Skype entreprise.  <br/> |
|DNS externe  <br/> |enregistrement SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Une interface externe pour votre service Edge d’accès. Cet enregistrement SRV est requis pour la découverte DNS automatique des partenaires fédérés appelés domaines SIP autorisés. Vous en aurez besoin un pour chaque domaine avec Skype entreprise.  <br/> |
|DNS interne  <br/> |Enregistrement A  <br/> |N/A  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 et 172.25.33.11  <br/> |Interface interne de votre serveur Edge consolidé.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Enregistrement DNS pour la Fédération (tous les scénarios)

|**Emplacement**|**Type**|**Port**|**FQDN**|**Enregistrement d’hôte de nom de domaine complet**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Interface externe du serveur Edge d’accès SIP requise pour la découverte DNS automatique. Utilisé par vos autres partenaires de Fédération potentiels. Elle est également appelée « autoriser les domaines SIP ». Vous en aurez besoin pour chaque domaine SIP avec des utilisateurs de Skype entreprise.  <br/><br/> **Remarque :** Vous aurez besoin de cet enregistrement SRV pour la mobilité et le centre d’échanges de notifications d’envoi. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Enregistrements DNS pour le protocole de messagerie et de présence extensible

|**Emplacement**|**Type**|**Port**|**FQDN**|**Enregistrement d’adresse IP ou d’hôte de nom de domaine complet**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externe  <br/> |SRV  <br/> |5269  <br/> |_xmpp-Server. _tcp. contoso. com  <br/> |xmpp.contoso.com  <br/> |Interface de proxy XMPP sur votre service Edge d’accès ou pool de serveurs Edge. Vous devez répéter cette opération autant que nécessaire pour tous les domaines SIP internes avec Skype entreprise Server activés, lorsque le contact avec les contacts XMPP est autorisé par le biais des éléments suivants :  <br/> • une stratégie globale  <br/> • une stratégie de site où l’utilisateur est activé  <br/> • stratégie utilisateur appliquée à l’utilisateur de Skype entreprise Server  <br/> Une stratégie XMPP autorisée doit également être configurée dans la stratégie des utilisateurs fédérés XMPP.  <br/> |
|DNS externe  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Adresse IP du service Edge d’accès sur le serveur Edge ou le pool de serveurs Edge hébergeant votre service proxy XMPP  <br/> |Cela pointe vers le service Edge d’accès sur le serveur Edge ou le pool de serveurs Edge qui héberge le service proxy XMPP. En règle générale, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).  <br/> |
   
> [!NOTE]
> Les passerelles XMPP et les proxys sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la rubrique migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

## <a name="certificate-planning"></a>Planification de certificat
<a name="CertPlan"> </a>

Skype entreprise Server utilise des certificats pour les communications chiffrées sécurisées entre les serveurs et entre les serveurs et les clients. Comme vous pouvez vous y attendre, vos certificats doivent avoir des enregistrements DNS pour que vos serveurs correspondent à tout nom de sujet (SN) et autre nom de sujet (SAN) sur vos certificats. Cette opération va fonctionner à l’étape de planification afin de s’assurer que les noms de domaine complets corrects sont enregistrés dans DNS pour les entrées SN et SAN de vos certificats.
  
Nous aborderons séparément les besoins des certificats internes et externes, puis examinons un tableau fournissant les conditions requises pour les deux.
  
### <a name="external-certificates"></a>Certificats externes

Au minimum, le certificat affecté à vos interfaces de serveur Edge externe doit être fourni par une autorité de certification publique (CA). Nous ne pouvons pas recommander une autorité de certification spécifique à votre CAs, mais nous disposons d’une liste de [partenaires de certificat de communications unifiées](/SkypeForBusiness/certification/services-ssl) que vous pouvez consulter pour voir si votre autorité de certification préférée est répertoriée.
  
Quand devez-vous soumettre une demande à une autorité de certification pour ce certificat public et comment procéder ? Il existe deux façons de procéder :
  
- Vous pouvez passer en revue l’installation de Skype entreprise Server, puis le déploiement du serveur Edge. L’Assistant Déploiement de Skype entreprise Server dispose d’une étape permettant de générer une demande de certificat, que vous pouvez ensuite envoyer à votre autorité de certification sélectionnée.
    
- Vous pouvez également utiliser les commandes Windows PowerShell pour générer cette demande, si cela est plus Inline avec les besoins de votre entreprise ou la stratégie de déploiement.
    
- Enfin, votre autorité de certification peut avoir son propre processus d’envoi, qui peut également impliquer Windows PowerShell ou une autre méthode. Dans ce cas, vous devez vous appuyer sur leur documentation, en plus des informations fournies ici à des fins de référence.
    
Une fois que vous avez obtenu le certificat, vous devez l’attribuer à ces services dans Skype entreprise Server :
  
- Interface du service Edge d’accès
    
- Interface de service Edge de conférence Web
    
- Service d’authentification audio/vidéo (ne confondez pas cela avec le service Edge A/V, car cela n’utilise pas de certificat pour chiffrer les flux audio et vidéo)
    
> [!IMPORTANT]
> Tous les serveurs Edge (s’ils appartiennent au même pool de serveurs Edge) doivent avoir exactement le même certificat avec la même clé privée pour le service d’authentification du serveur relais multimédia. 
  
### <a name="internal-certificates"></a>Certificats internes

Pour l’interface de serveur Edge interne, vous pouvez utiliser un certificat public provenant d’une autorité de certification publique ou un certificat émis par l’autorité de certification interne de votre organisation. La personne à retenir concernant le certificat interne est qu’elle utilise une entrée SN et aucune entrée SAN, de sorte que vous n’avez pas à vous soucier du SAN sur le certificat interne.
  
### <a name="required-certificates-table"></a>Tableau des certificats requis

Nous disposons d’un tableau pour vous aider dans vos demandes. Les entrées de nom de domaine complet ici ne concernent que les exemples de domaine. Vous allez devoir effectuer des demandes en fonction de vos propres domaines publics et privés, mais voici un guide sur ce que nous avons utilisés :
  
- Contoso <span></span> . com : nom de domaine complet public
    
- Fabrikam <span></span> . com : deuxième nom de domaine complet public (ajouté en tant que démonstration des éléments à demander si vous avez plusieurs domaines SIP)
    
- Contoso <span></span> .net : domaine interne
    
#### <a name="edge-certificate-table"></a>Table de certificat Edge

Qu’il s’agisse d’un serveur Edge unique ou d’un pool de serveurs Edge, c’est ce dont vous aurez besoin pour votre certificat :
  
|**Composant**|**Nom du sujet (SN)**|**Autres noms du sujet (SAN)/Order**|**Notes**|
|:-----|:-----|:-----|:-----|
|Serveur Edge externe  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Il s’agit du certificat que vous devez demander à une autorité de certification publique. Il doit être attribué aux interfaces Edge externes pour les éléments suivants :  <br/> • Serveur Edge d’accès  <br/> • Serveur Edge de conférence Web  <br/> • Authentification audio/vidéo  <br/> <br/>La bonne nouvelle est que le San est automatiquement ajouté à votre demande de certificat, et par conséquent à votre certificat après avoir soumis la demande, en fonction de ce que vous avez défini pour ce déploiement dans le générateur de topologies. Vous devrez uniquement ajouter des entrées SAN pour les domaines SIP supplémentaires ou d’autres entrées que vous devez prendre en charge. Pourquoi sip.contoso.com est-il répliqué dans cette instance ? Cela se produit automatiquement et il est nécessaire pour que les choses fonctionnent correctement.  <br/><br/> **Remarque :** Ce certificat peut également être utilisé pour la connectivité de messagerie instantanée publique. Vous n’avez pas besoin d’effectuer une opération différente avec elle, mais ce n’est pas le cas dans les versions précédentes de cette documentation. <br/> |
|Serveur Edge interne  <br/> |sfbedge.contoso.com  <br/> |N/A  <br/> |Vous pouvez obtenir ce certificat auprès d’une autorité de certification publique ou interne. Il doit contenir l’utilisation améliorée de la clé du serveur (utilisation améliorée de la clé) et vous pouvez l’affecter à l’interface Edge interne.  <br/> |
   
Si vous avez besoin d’un certificat pour le protocole XMPP (extensible Messaging and Presence Protocol), il aura la même apparence que les entrées de la table de serveur Edge externe, mais aura les deux entrées SAN supplémentaires suivantes :
  
- XMPP. <span></span> Contoso <span></span> . com
    
- \*. contoso <span></span> . com
    
N’oubliez pas que la fonctionnalité XMPP actuellement n’est prise en charge que dans Skype entreprise Server pour Google Talk, si vous voulez ou devez l’utiliser pour quoi que ce soit d’autre, vous devez vérifier que la fonctionnalité a été utilisée avec le fournisseur tiers impliqué.
  
## <a name="port-and-firewall-planning"></a>Planification des ports et des pare-feu
<a name="PortFirewallPlan"> </a>

L’obtention de votre droit de planification pour les ports et les pare-feu pour les déploiements de serveur Edge de Skype entreprise Server vous permet d’économiser des jours ou des semaines de dépannage et de stress. Par conséquent, nous allons répertorier quelques tableaux qui indiquent l’utilisation de votre protocole et les ports que vous devez avoir ouverts, entrants et sortants, à la fois pour les scénarios NAT et IP publics. Nous aurons également des tables distinctes pour les scénarios de charge matérielle équilibrée (charge matérielle) et d’autres conseils sur cette fonction. Pour plus d’informations à ce sujet, nous avons également des [scénarios de serveur Edge dans Skype entreprise Server](scenarios.md) que vous pouvez consulter pour vos problèmes de déploiement spécifiques.
  
### <a name="general-protocol-usage"></a>Utilisation générale du protocole

Avant d’examiner les tableaux de synthèse pour les pare-feu externes et internes, examinons également le tableau suivant :
  
|**Transport audio/vidéo**|**Usage**|
|:-----|:-----|
|DATAGRAMME  <br/> |Protocole de couche de transport préféré pour l’audio et la vidéo.  <br/> |
|TCP  <br/> |Protocole de couche transport de secours pour l’audio et la vidéo.  <br/> Le protocole de couche transport requis pour le partage d’application vers Skype entreprise Server, Lync Server 2013 et Lync Server 2010.  <br/> Le protocole de couche transport requis pour le transfert de fichiers vers Skype entreprise Server, Lync Server 2013 et Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tableau de synthèse du pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiennent des informations pour les utilisateurs qui utilisent des adresses IP privées avec NAT, ainsi que pour les personnes qui utilisent des adresses IP publiques. Cela concerne toutes les permutations dans nos [scénarios de serveur Edge dans la section Skype entreprise Server](scenarios.md) .
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non pris en charge dans Skype entreprise Server 2019 |TCP  <br/> |5269  <br/> |N'importe lequel  <br/> |Service proxy XMPP (partage une adresse IP avec le service Edge d’accès  <br/> |Le service proxy XMPP accepte le trafic provenant de contacts XMPP dans les fédérations XMPP définies.  <br/> |
|Accès/HTTP  <br/> |TCP  <br/> |80  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N'importe lequel  <br/> |Vérification et extraction de la liste de révocation de certificats.  <br/> |
|Accès/DNS  <br/> |TCP  <br/> |53  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N'importe lequel  <br/> |Requête DNS sur TCP.  <br/> |
|Accès/DNS  <br/> |DATAGRAMME  <br/> |53  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N'importe lequel  <br/> |Requête DNS sur UDP.  <br/> |
|Accès/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |Trafic SIP client à serveur pour l’accès des utilisateurs externes.  <br/> |
|Accès/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |Pour la connectivité de messagerie instantanée fédérée et publique à l’aide de SIP.  <br/> |
|Accès/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N'importe lequel  <br/> |Pour la connectivité de messagerie instantanée fédérée et publique à l’aide de SIP.  <br/> |
|Conférence Web/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge de conférence Web de serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge de conférence Web du serveur Edge <br/> |Support de conférence Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge A/V du serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |N'importe lequel  <br/> |Il est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |DATAGRAMME  <br/> |50000-59999  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge A/V du serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |N'importe lequel  <br/> |Il est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/STUN. MSTURN  <br/> |DATAGRAMME  <br/> |3478  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge A/V du serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |N'importe lequel  <br/> |3478 sortant est :  <br/> • Utilisé par Skype entreprise Server pour déterminer la version du serveur Edge avec lequel il communique.  <br/> • Utilisé pour le trafic multimédia entre les serveurs Edge.  <br/> • Obligatoire pour la Fédération avec Lync Server 2010.  <br/> • Nécessaire si plusieurs pools Edge sont déployés au sein de votre organisation.  <br/> |
|A/V/STUN. MSTURN  <br/> |DATAGRAMME  <br/> |3478  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge A/V du serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |STUN/activer la négociation des candidats via UDP sur le port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge A/V du serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |STUN/activer la négociation des candidats sur TCP sur le port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge A/V du serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |N'importe lequel  <br/> |STUN/activer la négociation des candidats sur TCP sur le port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tableau de synthèse du pare-feu de port interne

|**Protocol (Protocole)**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des opérations suivantes exécute le service de passerelle XMPP :  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic XMPP sortant provenant de votre service de passerelle XMPP s’exécutant sur le serveur frontal ou le pool frontal.  <br/> **Remarque :** Les passerelles XMPP et les proxys sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la rubrique migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Chaque  <br/> • Directeur  <br/> • Pool directeur  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic SIP sortant de votre directeur, pool Directeur, serveur frontal ou pool frontal vers votre interface interne de serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interne du serveur Edge  <br/> |Chaque  <br/> • Directeur  <br/> • Pool directeur  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> |Trafic SIP entrant vers votre directeur, pool Directeur, serveur frontal ou pool frontal à partir de votre interface interne de serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Chaque  <br/> • Serveur frontal  <br/> • Chaque serveur frontal  <br/>  dans votre pool frontal <br/> |Interface interne du serveur Edge  <br/> |Trafic de conférence Web à partir de votre serveur frontal ou de chaque serveur frontal (si vous avez un pool frontal) vers votre interface interne de serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Chaque  <br/> • Serveur frontal  <br/> • Pool frontal  <br/> • Tout Survivable Branch Appliance utilisant ce serveur Edge  <br/> • Un serveur Survivable Branch Server utilisant ce serveur Edge  <br/> |Interface interne du serveur Edge  <br/> |Authentification des utilisateurs A/V à partir de votre serveur frontal ou de votre pool frontal, ou de votre Survivable Branch Appliance ou de votre serveur Survivable Branch Server, à l’aide de votre serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |DATAGRAMME  <br/> |3478  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou le serveur Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Chemin de secours pour le transfert multimédia A/V entre vos utilisateurs internes et externes, votre Survivable Branch Appliance ou le serveur Survivable Branch Server, si la communication UDP ne fonctionne pas. Le protocole TCP est ensuite utilisé pour les transferts de fichiers et le partage du bureau.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Chaque  <br/> • Serveur frontal qui héberge le magasin central de gestion  <br/> • Pool frontal qui contient le magasin central de gestion  <br/> |Interface interne du serveur Edge  <br/> |Réplication des modifications de votre magasin central de gestion vers votre serveur Edge.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisée à l’aide de Skype entreprise Server Management Shell et des cmdlets du service de journalisation centralisée, ClsController Command Line (ClsController. exe) ou agent (ClsAgent. exe) et collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisée à l’aide de Skype entreprise Server Management Shell et des cmdlets du service de journalisation centralisée, ClsController Command Line (ClsController. exe) ou agent (ClsAgent. exe) et collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisée à l’aide de Skype entreprise Server Management Shell et des cmdlets du service de journalisation centralisée, ClsController Command Line (ClsController. exe) ou agent (ClsAgent. exe) et collection de journaux.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Programmes d’équilibrage de la charge matérielle pour les tables de ports Edge

Nous accordons des programmes d’équilibrage de la charge matérielle (équilibreurs) et de ports Edge à leur propre section, car les choses sont un peu plus complexes avec le matériel supplémentaire. Pour obtenir des conseils pour ce scénario particulier, consultez les tableaux ci-dessous :
  
#### <a name="external-port-firewall-summary-table"></a>Tableau de synthèse du pare-feu de port externe

L’adresse IP source et l’adresse IP de destination contiennent des informations pour les utilisateurs qui utilisent des adresses IP privées avec NAT, ainsi que pour les personnes qui utilisent des adresses IP publiques. Cela concerne toutes les permutations dans nos [scénarios de serveur Edge dans la section Skype entreprise Server](scenarios.md) .
  
|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accès/HTTP  <br/> |TCP  <br/> |80  <br/> |Adresse IP publique du service Edge d’accès au serveur Edge  <br/> |N'importe lequel  <br/> |Vérification et extraction de la liste de révocation de certificats.  <br/> |
|Accès/DNS  <br/> |TCP  <br/> |53  <br/> |Adresse IP publique du service Edge d’accès au serveur Edge  <br/> |N'importe lequel  <br/> |Requête DNS sur TCP.  <br/> |
|Accès/DNS  <br/> |DATAGRAMME  <br/> |53  <br/> |Adresse IP publique du service Edge d’accès au serveur Edge  <br/> |N'importe lequel  <br/> |Requête DNS sur UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Adresse IP du service Edge A/V du serveur Edge  <br/> |N'importe lequel  <br/> |Il est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/RTP  <br/> |DATAGRAMME  <br/> |50000-59999  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |N'importe lequel  <br/> |Il est utilisé pour relayer le trafic multimédia.  <br/> |
|A/V/STUN. MSTURN  <br/> |DATAGRAMME  <br/> |3478  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |N'importe lequel  <br/> |3478 sortant est :  <br/> • Utilisé par Skype entreprise Server pour déterminer la version du serveur Edge avec lequel il communique.  <br/> • Utilisé pour le trafic multimédia entre les serveurs Edge.  <br/> • Obligatoire pour la Fédération.  <br/> • Nécessaire si plusieurs pools Edge sont déployés au sein de votre organisation.  <br/> |
|A/V/STUN. MSTURN  <br/> |DATAGRAMME  <br/> |3478  <br/> |N'importe lequel  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |STUN/activer la négociation des candidats via UDP sur le port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |STUN/activer la négociation des candidats sur TCP sur le port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Adresse IP publique du service Edge A/V du serveur Edge  <br/> |N'importe lequel  <br/> |STUN/activer la négociation des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tableau de synthèse du pare-feu de port interne

|**Protocol (Protocole)**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |L’une des opérations suivantes exécute le service de passerelle XMPP :  <br/> • Serveur frontal  <br/> • Adresse IP virtuelle du pool frontal exécutant le service de passerelle XMPP  <br/> |Interface interne du serveur Edge  <br/> |Trafic XMPP sortant provenant de votre service de passerelle XMPP s’exécutant sur le serveur frontal ou le pool frontal.  <br/><br/> **Remarque :** Les passerelles XMPP et les proxys sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la rubrique migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Chaque  <br/> • Serveur frontal qui héberge le magasin central de gestion  <br/> • Pool frontal qui contient le magasin central de gestion  <br/> |Interface interne du serveur Edge  <br/> |Réplication des modifications de votre magasin central de gestion vers votre serveur Edge.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Chaque  <br/> • Serveur frontal  <br/> • Chaque serveur frontal de votre pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic de conférence Web à partir de votre serveur frontal ou de chaque serveur frontal (si vous avez un pool frontal) vers votre interface interne de serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |DATAGRAMME  <br/> |3478  <br/> |Chaque  <br/> • Serveur frontal  <br/> • Chaque serveur frontal de votre pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes et votre Survivable Branch Appliance ou le serveur Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Chaque  <br/> • Serveur frontal  <br/> • Chaque serveur frontal de votre pool  <br/> |Interface interne du serveur Edge  <br/> |Chemin de secours pour le transfert multimédia A/V entre vos utilisateurs internes et externes, votre Survivable Branch Appliance ou le serveur Survivable Branch Server, si la communication UDP ne fonctionne pas. Le protocole TCP est ensuite utilisé pour les transferts de fichiers et le partage du bureau.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisée à l’aide de Skype entreprise Server Management Shell et des cmdlets du service de journalisation centralisée, ClsController Command Line (ClsController. exe) ou agent (ClsAgent. exe) et collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisée à l’aide de Skype entreprise Server Management Shell et des cmdlets du service de journalisation centralisée, ClsController Command Line (ClsController. exe) ou agent (ClsAgent. exe) et collection de journaux.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Contrôleur de service de journalisation centralisée à l’aide de Skype entreprise Server Management Shell et des cmdlets du service de journalisation centralisée, ClsController Command Line (ClsController. exe) ou agent (ClsAgent. exe) et collection de journaux.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Adresses IP virtuelles d’interface externe

|**Rôle ou protocole**|**TCP ou UDP**|**Port de destination ou plage de ports**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non pris en charge dans Skype entreprise Server 2019 |TCP  <br/> |5269  <br/> |N'importe lequel  <br/> |Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)  <br/> |Le service proxy XMPP accepte le trafic provenant de contacts XMPP dans les fédérations XMPP définies.  <br/> |
|XMPP  <br/>Non pris en charge dans Skype entreprise Server 2019 |TCP  <br/> |5269  <br/> |Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)  <br/> |N'importe lequel  <br/> |Le service proxy XMPP envoie le trafic de contacts XMPP dans les fédérations XMPP définies.  <br/> |
|Accès/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |Trafic SIP client à serveur pour l’accès des utilisateurs externes.  <br/> |
|Accès/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |Pour la connectivité de messagerie instantanée fédérée et publique à l’aide de SIP.  <br/> |
|Accès/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge d’accès au serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge d’accès au serveur Edge <br/> |N'importe lequel  <br/> |Pour la connectivité de messagerie instantanée fédérée et publique à l’aide de SIP.  <br/> |
|Conférence Web/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge de conférence Web de serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge de conférence Web du serveur Edge <br/> |Support de conférence Web.  <br/> |
|A/V/STUN. MSTURN  <br/> |DATAGRAMME  <br/> |3478  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge A/V du serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |STUN/activer la négociation des candidats via UDP sur le port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |**Adresse IP privée utilisant la traduction d’adresses réseau :** Service Edge A/V du serveur Edge <br/> **Adresse IP publique :** Adresse IP publique du service Edge A/V du serveur Edge <br/> |STUN/activer la négociation des candidats sur TCP sur le port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Adresses IP virtuelles d’interface interne

Nos conseils vont bientôt être légèrement différents. En réalité, dans une situation charge matérielle, nous vous recommandons désormais de n’utiliser le routage par le biais d’une adresse IP interne que dans les circonstances suivantes :
  
- Si vous utilisez Exchange 2007 ou Exchange 2010 Unified Messaging (UM).
    
- Si vous avez des clients hérités qui utilisent le serveur Edge.
    
Le tableau suivant fournit des instructions pour ces scénarios, mais dans le cas contraire, vous devez être en mesure de dépendre du magasin central de gestion (CMS) pour acheminer le trafic vers le serveur Edge qu’il prend en charge (cela fait que le CMS est tenu à jour des informations du serveur Edge, bien évidemment).
  
|**Protocol (Protocole)**|**TCP ou UDP**|**Port**|**Adresse IP source**|**Adresse IP de destination**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accès/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Chaque  <br/> • Directeur  <br/> • Adresse VIP du pool directeur  <br/> • Serveur frontal  <br/> • Adresse IP virtuelle du pool frontal  <br/> |Interface interne du serveur Edge  <br/> |Trafic SIP sortant provenant de votre directeur, de votre adresse IP de pool Directeur, de votre serveur frontal ou de votre adresse VIP de pool frontal vers votre interface interne de serveur Edge.  <br/> |
|Accès/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface VIP interne du serveur Edge  <br/> |Chaque  <br/> • Directeur  <br/> • Adresse VIP du pool directeur  <br/> • Serveur frontal  <br/> • Adresse IP virtuelle du pool frontal  <br/> |Trafic SIP entrant vers votre directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP virtuelle du pool frontal à partir de votre interface interne de serveur Edge.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Chaque  <br/> • Adresse IP du serveur frontal  <br/> • Adresse IP du pool frontal  <br/> • Tout Survivable Branch Appliance utilisant ce serveur Edge  <br/> • Un serveur Survivable Branch Server utilisant ce serveur Edge  <br/> |Interface interne du serveur Edge  <br/> |Authentification des utilisateurs A/V à partir de votre serveur frontal ou de votre pool frontal, ou de votre Survivable Branch Appliance ou de votre serveur Survivable Branch Server, à l’aide de votre serveur Edge.  <br/> |
|STUN/MSTURN  <br/> |DATAGRAMME  <br/> |3478  <br/> |N'importe lequel  <br/> |Interface interne du serveur Edge  <br/> |Chemin préféré pour le transfert multimédia A/V entre vos utilisateurs internes et externes.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |N'importe lequel  <br/> |Interface VIP interne du serveur Edge  <br/> |Chemin de secours pour le transfert multimédia A/V entre vos utilisateurs internes et externes si la communication UDP ne fonctionne pas. Le protocole TCP est ensuite utilisé pour les transferts de fichiers et le partage du bureau.  <br/> |
