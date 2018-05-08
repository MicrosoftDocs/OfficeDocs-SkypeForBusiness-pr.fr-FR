---
title: Routage géodépendant pour les conférences dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/13/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planification de routage par emplacement pour les conférences dans Skype pour Business Server Enterprise Voice, y compris appel consultatif transfère.
ms.openlocfilehash: 778f8156d2d4ab4cf6613975567a88e80c1e6b9c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server-2015"></a>Routage géodépendant pour les conférences dans Skype Entreprise Server 2015
 
Planification de routage par emplacement pour les conférences dans Skype pour Business Server Enterprise Voice, y compris appel consultatif transfère.
  
Routage basé sur l’emplacement rend possible de restreindre le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC basées sur l’emplacement des parties de l’appel. En fonction de routage pour la conférence vous permet d’appliquer les règles de routage basé sur l’emplacement sur réunions (c'est-à-dire des conférences) afin d’empêcher PSTN payant contournement de média. L’application surveille une conférence active et applique les restrictions de routage basé sur l’emplacement en fonction de l’emplacement des utilisateurs participant. En outre, le routage basé sur l’emplacement pour l’application de conférence permet la mise en œuvre des restrictions de routage basé sur un emplacement pour les transferts consultatifs impliquant des points de terminaison RTC.
  
L’application en fonction de conférence routage fournit à Skype pour des conférences est un mécanisme de prévention de numéro payant PSTN de contournement. L’application surveille les conférences actives et applique les restrictions de routage basé sur l’emplacement en fonction de l’emplacement de la Skype pour les utilisateurs professionnels participant. 
  
L’application de conférence de routage basée sur l’emplacement détermine routage basé sur l’emplacement à appliquer sur un Skype pour une réunion d’affaires si les conditions suivantes sont réunies :
  
- L’organisateur de la réunion est activé pour le routage basé sur l’emplacement. En fonction des restrictions de routage seront appliquées uniquement à des conférences sont organisées par les utilisateurs activés pour le routage basé sur l’emplacement.
    
- Au moins un participant à la réunion est un point de terminaison PSTN. En fonction des restrictions de routage sont applique uniquement aux conférences qui incluent des points de terminaison RTC.
    
- Le site réseau sur lequel la passerelle PSTN utilisée pour relier la conférence au réseau téléphonique commuté est localisée, de même que les sites réseau depuis lesquels les organisateurs et les participants se connectent. 
    
Routage basé sur un emplacement pour l’application de conférence empêche la participation de Skype pour les utilisateurs et les systèmes d’extrémité PSTN à partir des sites de réseau différent pour la même conférence. Si l’organisateur d’une réunion est activé pour le routage basé sur l’emplacement, l’application de conférence impose les restrictions suivantes :
  
- Les points de terminaison qui peuvent participer à une Skype pour une réunion d’affaires varient selon les points de terminaison qui a déjà rejoint la conférence, et cette restriction ajuste en congé liés à des points de terminaison et nouveaux points de terminaison de joindre la conférence. Si les organisateurs et les participants rejoignent une Skype pour la réunion d’entreprise à partir du même site réseau, puis un point de terminaison RTC, un autre participant à partir du même site réseau, un autre participant à partir d’un site réseau différent ou un participant à partir d’un site réseau inconnu sont autorisés à participer.
    
- Si les organisateurs et les participants rejoignent la réunion à partir d’autres sites réseaux ou de sites réseau inconnus, un point de terminaison PSTN n’est pas autorisé à rejoindre la réunion si l’appel PSTN provient d’une jonction SIP pour laquelle le routage géodépendant est activé.
    
- Si les organisateurs et les participants sont tous les accès à la réunion à partir du même site réseau et les participants à la même réunion à partir de la passerelle PSTN, un Skype pour point de terminaison métiers à partir d’un site autre réseau n’est pas autorisé à participer à la réunion.
    
Ces restrictions de routage en fonction de conférence sont résumées dans le tableau suivant. 
  
| |
|**Utilisateurs dans une conférence à un moment donné**|**Utilisateurs autorisés à participer à la conférence**|**Utilisateurs non autorisés à participer à la conférence**|
|:-----|:-----|:-----|
|Skype pour VoIP Business client ou les utilisateurs d’un site réseau unique  <br/> |Skype pour l’utilisateur du client à partir du même site réseau VoIP d’entreprise  <br/> Skype pour l’utilisateur du client à partir d’un site autre réseau VoIP d’entreprise  <br/> Skype pour l’utilisateur du client VoIP d’entreprise à partir d’un site réseau inconnu  <br/> Skype fédéré pour l’utilisateur du client VoIP d’entreprise  <br/> Utilisateur rejoignant la conférence à partir d’un point de terminaison PSTN  <br/> |Aucune  <br/> |
|Skype pour VoIP Business client ou les utilisateurs à partir d’un site réseau inconnu  <br/> |Skype pour l’utilisateur du client VoIP d’entreprise à partir de n’importe quel site  <br/> Skype pour l’utilisateur du client VoIP d’entreprise à partir d’un site inconnu  <br/> Skype fédéré pour l’utilisateur du client VoIP d’entreprise  <br/> |Utilisateur rejoignant la conférence via un point de terminaison PSTN  <br/> |
|Skype pour les utilisateurs de client VoIP d’entreprise à partir des sites de réseau  <br/> |Skype pour l’utilisateur du client à partir de n’importe quel site réseau VoIP d’entreprise  <br/> Skype pour l’utilisateur du client VoIP d’entreprise à partir d’un site réseau inconnu  <br/> Skype fédéré pour l’utilisateur du client VoIP d’entreprise  <br/> |Utilisateur rejoignant la conférence via un point de terminaison PSTN  <br/> |
|Skype pour les utilisateurs de client VoIP d’entreprise à partir d’un site réseau unique et les utilisateurs qui rejoignent à partir d’un point de terminaison RTC  <br/> |Skype pour l’utilisateur du client à partir du même site réseau VoIP d’entreprise  <br/> |Skype pour l’utilisateur du client à partir d’un site autre réseau VoIP d’entreprise  <br/> Skype pour l’utilisateur du client VoIP d’entreprise à partir d’un site réseau inconnu  <br/> Skype fédéré pour l’utilisateur du client VoIP d’entreprise  <br/> |
   
Autres caractéristiques de la gamme en fonction de l’application de conférence sont les suivantes :
  
- Lorsqu’un utilisateur n’est pas autorisé à participer à une conférence, compte tenue de restrictions de routage basé sur l’emplacement, l’appel à la conférence sera rejeté et le Skype pour le client Business rapport l’appel n’a pas terminé ou qu’elle est terminée.
    
- Un point de terminaison PSTN participer à qu'une conférence avec des applications de routage basé sur l’emplacement ne seront pas limitée à rejoindre la conférence quel que soit son état si le point de terminaison joint via une jonction n’est pas activée pour le routage basé sur l’emplacement.
    
- Un système PBX connecté à un serveur de médiation via une jonction SIP qui ne pas sortie les appels RTC aura les mêmes applications en tant que Skype pour les utilisateurs professionnels situé dans le même site réseau dans lequel la jonction SIP est définie. Par exemple, un point de terminaison RTC sera en mesure de participer à une conférence avec un utilisateur PBX et un Skype pour utilisateur professionnel si elles se trouvent dans le même site réseau ; dans le cas contraire, le point de terminaison RTC pas autorisé à participer à la conférence si l’utilisateur PBX est dans un site autre réseau que le Skype pour l’utilisateur d’entreprise.
    
> [!NOTE]
> Avec la mise à jour cumulative 4 de Skype Entreprise, vous devriez observer le comportement décrit dans le tableau suivant : 
  
|**Utilisateur**|**Autre partie**|**Action**|**Résultat**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype Entreprise Mobile est en appel RTC. Skype Entreprise Mobile transforme ensuite l'appel en standard automatique des conférences (CAA).  <br/> |L’appel est bloqué, avec un message d’erreur correspondant.  <br/> |
|Skype Entreprise Mobile  <br/> |Client ou utilisateur fédéré Skype Entreprise  <br/> |Le Client ou un utilisateur fédéré est sur un appel VoIP une Skype pour utilisateur Business Mobile Location-Based routage, et chaque partie est transmise à un CAA.  <br/> |La transformation de l’appel est bloquée, avec un message d’erreur correspondant.  <br/> |
   
## <a name="consultative-call-transfers"></a>Transferts d’appel consultatifs

En plus de l’application en fonction de routage à Skype pour les réunions d’entreprise, le routage basé sur l’emplacement pour l’application de conférence applique les restrictions de routage basé sur l’emplacement du transfert consultatif appel qui sortie aux points de terminaison RTC. Un transfert d’appel consultatif est un appel établi entre deux parties dans lequel une des parties transfère l’appel vers un nouvel utilisateur. Par exemple, un point de terminaison RTC appelle l’utilisateur (Skype pour appelé Business). L’utilisateur A détermine que l’utilisateur RTC doit être transféré à l’utilisateur B (Skype pour utilisateur professionnel). L’utilisateur A passe l’appel avec l’utilisateur PSTN en attente, et appelle l’utilisateur B. L’utilisateur B accepte de parler à l’utilisateur PSTN. L’utilisateur A transfère l’appel en attente à l’utilisateur B.
  
**Flux d’appels transfert consultatif d’appel**

![Diagramme Routage géodépendant pour les conférences](../../media/LocationBasedRoutingForConferencing.jpg)
  
Lorsqu’un utilisateur activé pour le routage basé sur l’emplacement lance un transfert consultatif appel d’un point de terminaison RTC (comme illustré dans la figure précédente), cette opération crée deux appels actifs et l’autre entre Skype pour un appel entre l’utilisateur RTC et Skype pour un utilisateur d’entreprise Un utilisateur d’entreprise et Skype pour l’utilisateur B. le comportement suivant est appliqué par le routage basé sur l’emplacement pour l’application de conférence :
  
- Si l’appel de la jonction SIP routage RTC est autorisé à rediriger l’appel PSTN au site réseau où se trouve Skype pour l’utilisateur B (c'est-à-dire cible de transfert), puis le transfert d’appel est autorisé ; Sinon, le transfert d’appel consultatif est bloqué. Cette autorisation est effectuée en fonction de sur l’emplacement de la partie transférés en cours dans le même site réseau en tant que la jonction SIP qui envoie l’appel actif au point de terminaison RTC. 
    
- Si la jonction SIP routage des appels PSTN entrants n’est pas autorisée à acheminer les appels vers le site de réseau où se trouve la partie transférée (Skype pour l’utilisateur B) ou la partie transférée se trouve dans un site réseau inconnu, puis l’appel consultatif transférer vers le point de terminaison RTC (c'est-à-dire cible de transfert d’appels) est bloquée.
    
Le tableau suivant décrit comment basé sur l’emplacement de routage restrictions sont appliquées par le routage basé sur l’emplacement pour l’application de conférence pour les transferts consultatifs appel. Si les points de terminaison PBX ne sont pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau. Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.
  

|**Site de réseau d’un appel transféré tiers**|**Site de réseau de la cible de transfert d’appel**|**Comportement**|
|:-----|:-----|:-----|
|Point de terminaison RTC  <br/> |Skype pour l’utilisateur d’entreprise dans le même site réseau (autrement dit, le site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Skype pour l’utilisateur d’entreprise dans les sites de réseau différents (autrement dit, le site 2)  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Skype pour l’utilisateur d’entreprise dans un site réseau inconnu  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Skype fédéré pour l’utilisateur d’entreprise  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans le même site (site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans un autre site (site 2)  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PBX dans le même site (site 1)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un autre site (site 2)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Skype pour l’utilisateur d’entreprise dans le même site réseau (autrement dit, le site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Skype pour l’utilisateur d’entreprise dans les sites de réseau différents (autrement dit, le site 2)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Skype pour l’utilisateur d’entreprise dans un site réseau inconnu  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Skype fédéré pour l’utilisateur d’entreprise  <br/> |Le transfert consultatif est autorisé  <br/> |
   
## <a name="requirements"></a>Configuration requise

Routage basé sur un emplacement pour l’application de conférence requiert que Skype pour Business Server ou Lync Server 2013 Cumulative Update 2 est déployée sur tous les pools frontaux et les serveurs Standard Edition Server dans votre topologie. Si ces versions du serveur ne sont pas installées sur certains serveurs de votre topologie, les restrictions de routage basé sur l’emplacement ne peut pas être entièrement appliqué aux réunions et consultatif transfert d’appel.
  
Le tableau suivant indique les combinaisons de rôles de serveur et les versions qui prennent en charge le routage basé sur l’emplacement.
  

|**Version du Pool frontale**|**Version de serveur de médiation**|**Prise en charge**|
|:-----|:-----|:-----|
|Skype pour Business Server ou Lync Server 2013 mise à jour Cumulative 2  <br/> |Skype pour Business Server ou Lync Server 2013 mise à jour Cumulative 2  <br/> |Oui  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Mise à jour cumulative 1 de Lync Server 2013  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Non  <br/> |
|Mise à jour cumulative 1 de Lync Server 2013  <br/> |Indifférente  <br/> |Non  <br/> |
|Lync Server 2010  <br/> |Indifférente  <br/> |Non  <br/> |
|Office Communications Server 2007 R2  <br/> |Indifférente  <br/> |Non  <br/> |
   
## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuration de routage en fonction d’emplacement pour la conférence

Routage basé sur un emplacement pour l’application de conférence s’appuie sur la configuration du routage basé sur l’emplacement. Les configurations principales suivantes sont disponibles : 
  
- L’emplacement des participants rejoignant une réunion est déterminé sur la base de leur site réseau. Un site réseau et sous-réseaux de son réseau associé doit être défini dans Skype pour Business Server afin d’appliquer le routage basé sur l’emplacement.
    
- Pour appliquer en fonction de routage des réunions, Skype pour les participants de l’entreprise doit être activé pour le routage basé sur l’emplacement.
    
- Pour appliquer le routage emplacement de points de terminaison RTC participer à des réunions, la jonction SIP permet de connecter les points de terminaison RTC doit être configurée pour le routage basé sur l’emplacement.
    
## <a name="enabling-the-location-based-routing-for-conferencing"></a>Activer le routage en fonction de la conférence

Routage basé sur un emplacement pour l’application de conférence est désactivé par défaut. Avant d’activer cette application, vous devez déterminer la priorité adaptée à affecter à l’application. Pour déterminer la priorité, exécutez la cmdlet suivante dans Skype pour Business Server Management Shell :
  
Get-CsServerApplication-identité Service : Registrar :<Pool FQDN>dans cette applet de commande, \<nom complet du Pool\> est le pool dans lequel le routage basé sur l’emplacement pour l’application de conférence doit être activé.
  
Cette applet de commande renvoie la liste des applications hébergées par Skype pour Business Server et la valeur de priorité pour chacun d’eux. Routage basé sur un emplacement pour l’application de conférence doit être assigné une valeur de priorité supérieure de l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ». Nous vous recommandons d’affecter une valeur de priorité qui est un point supérieur à la valeur de priorité de l’application « UdcAgent » le routage basé sur l’emplacement pour l’application de conférence.
  
Par exemple, si l’application « UdcAgent » a une valeur de priorité de « 2 », l’application « DefaultRouting » a une valeur de priorité de « 8 », l’application « ExumRouting » a une valeur de priorité de « 9 » et l’application « OutboundRouting » a une valeur de priorité de « 10 » puis une valeur de priorité de « 3 », vous devez affecter le routage basé sur l’emplacement pour l’application de conférence. En procédant ainsi placez la priorité des applications dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence de routage basée sur l’emplacement (priorité : 3), autres applications (priorités : 4 à 8), » DefaultRouting » (priorité : 9), « ExumRouting » (priorité : 10) et « OutboundRouting » (priorité : 11).
  
Après avoir trouvé la valeur de priorité approprié pour le routage basé sur l’emplacement pour l’application de conférence, tapez l’applet de commande pour chaque pool frontal ou serveur Standard Edition Server que les utilisateurs particuliers activés pour le routage basé sur l’emplacement suivant :
  
New-CsServerApplication-identité Service : Registrar :<Pool FQDN>/LBRouting-priorité <Application Priority> -Enabled $true-critique $true - Uri http://www.microsoft.com/LCS/LBRoutingFor exemple :
  
New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-priorité 3 - $true activé-critique $true - Uri http://www.microsoft.com/LCS/LBRoutingAfter à l’aide de cette applet de commande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition Server où le Emplacement de routage pour l’application de conférence a été activé.
  
> [!IMPORTANT]
> En fonction des applications de routage pour les conférences ou les transferts consultatifs ne sont pas appliquées jusqu'à ce que tous les serveurs frontaux dans les pools applicables ou les serveurs Standard Edition Server sont redémarrés. Si vous définissez **-critique** sur **$true** dans les applets de commande ci-dessus, votre Skype pour les services Business Server va être redémarré immédiatement. Si vous ne souhaitez pas que ces services pour redémarrer immédiatement, définissez **-critique** sur **$false** pour maintenant, puis utilisez **Set-CsServerApplication** pour modifier **-critique** sur **$true** ultérieurement, une fois que les services ont été redémarrés.
  
Une fois le routage basé sur l’emplacement pour l’application de conférence a été correctement activé et tous les serveurs applicables ont été redémarrés, toutes les conférences organisées par Skype pour les utilisateurs activés pour le routage basé sur l’emplacement seront surveillés pour empêcher Numéro payant PSTN de contournement
  

