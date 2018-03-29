---
title: Routage géodépendant pour les conférences dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/13/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Appel de consultation, y compris la planification basée sur l’emplacement de routage pour les conférences dans Skype pour Business Server Voix Entreprise, transfère.
ms.openlocfilehash: 4cfa76e10ed0107c1dc1fe4c1759a89536529ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server-2015"></a>Routage géodépendant pour les conférences dans Skype Entreprise Server 2015
 
Appel de consultation, y compris la planification basée sur l’emplacement de routage pour les conférences dans Skype pour Business Server Voix Entreprise, transfère.
  
Fondée sur l’emplacement de routage permet de restreindre le routage des appels entre les points de terminaison VoIP et les points de terminaison RTPC en fonction de l’emplacement des parties dans l’appel. Routage pour la conférence fondée sur l’emplacement vous permet d’appliquer des règles de routage basé sur l’emplacement de réunions (c'est-à-dire des conférences) pour empêcher les RTPC payant de contournement. L’application analyse une conférence active et applique les restrictions de routage basé sur l’emplacement en fonction de l’emplacement des utilisateurs participant. Le routage basé sur l’emplacement pour l’application de conférence permet en outre la mise en œuvre du routage basé sur l’emplacement des restrictions aux transferts de consultation impliquant les points de terminaison TLS.
  
L’application de conférence de routage basées sur l’emplacement fournit à Skype pour des conférences, un mécanisme pour la prévention de l’appel de RTPC ignorer. L’application analyse les conférences actives et applique les restrictions de routage basé sur l’emplacement en fonction de l’emplacement de la Skype pour les utilisateurs professionnels participant. 
  
L’application de conférence de routage basées sur l’emplacement détermine si routage basé sur l’emplacement doit être appliquée sur un Skype pour une réunion d’affaires si les conditions suivantes sont réunies :
  
- L’organisateur de la réunion est activé pour le routage basé sur l’emplacement. Fondée sur l’emplacement des restrictions de routage s’appliquera uniquement aux conférences organisées par les utilisateurs qui sont activés pour le routage basé sur l’emplacement.
    
- Au moins un participant à la réunion est un point de terminaison PSTN. Fondée sur l’emplacement des restrictions de routage ne sont applicables que pour les conférences qui incluent des points de terminaison TLS.
    
- Le site réseau sur lequel la passerelle PSTN utilisée pour relier la conférence au réseau téléphonique commuté est localisée, de même que les sites réseau depuis lesquels les organisateurs et les participants se connectent. 
    
Le routage basé sur l’emplacement pour l’application de conférence empêche la participation de Skype pour les utilisateurs et les points de terminaison PSTN à partir des sites de réseau différent à la même conférence. Si l’organisateur d’une réunion est activé pour le routage basé sur l’emplacement, l’application de conférence impose les restrictions suivantes :
  
- Les points de terminaison qui peuvent joindre un Skype pour une réunion d’affaires dépendent les points de terminaison qui a déjà joint la conférence, et cette restriction ajuste en congé de points de terminaison joints et nouveaux points de terminaison de joindre la conférence. Si les organisateurs et les participants rejoignent un Skype pour une réunion d’affaires à partir du même site de réseau, puis un point de terminaison du réseau RTPC, un autre participant à partir du même site de réseau, un autre participant d’un site de réseau différent ou un participant d’un site réseau inconnu sont autorisés à accéder.
    
- Si les organisateurs et les participants rejoignent la réunion à partir d’autres sites réseaux ou de sites réseau inconnus, un point de terminaison PSTN n’est pas autorisé à rejoindre la réunion si l’appel PSTN provient d’une jonction SIP pour laquelle le routage géodépendant est activé.
    
- Si les organisateurs et les participants sont tous joindre la réunion à partir du même site de réseau et aux participants de joindre la réunion même de RTC, un Skype pour point de terminaison Business à partir d’un site de réseau différent ne permet pas de joindre la réunion.
    
Ces restrictions de routage basé sur l’emplacement de conférence sont résumées dans le tableau suivant. 
  
| |
|**Utilisateur (s) dans une conférence à un moment donné**|**Utilisateurs autorisés à joindre la conférence**|**Utilisateurs non autorisés à joindre la conférence**|
|:-----|:-----|:-----|
|Skype pour les utilisateurs de client VoIP d’entreprise à partir d’un site de réseau unique  <br/> |Skype pour l’utilisateur du client à partir du même site de réseau VoIP d’entreprise  <br/> Skype pour l’utilisateur du client à partir d’un site de réseau VoIP d’entreprise  <br/> Skype pour utilisateur de client VoIP d’entreprise à partir d’un site réseau inconnu  <br/> Skype fédéré pour utilisateur de client VoIP d’entreprise  <br/> Utilisateur rejoignant la conférence à partir d’un point de terminaison PSTN  <br/> |Aucune  <br/> |
|Skype pour les utilisateurs de client VoIP d’entreprise à partir d’un site réseau inconnu  <br/> |Skype pour utilisateur de client VoIP d’entreprise à partir de n’importe quel site  <br/> Skype pour utilisateur de client VoIP d’entreprise à partir d’un site inconnu  <br/> Skype fédéré pour utilisateur de client VoIP d’entreprise  <br/> |Utilisateur rejoignant la conférence via un point de terminaison PSTN  <br/> |
|Skype pour les utilisateurs de client VoIP d’entreprise à partir des sites de réseau différent  <br/> |Skype pour l’utilisateur du client à partir de n’importe quel site de réseau VoIP d’entreprise  <br/> Skype pour utilisateur de client VoIP d’entreprise à partir d’un site réseau inconnu  <br/> Skype fédéré pour utilisateur de client VoIP d’entreprise  <br/> |Utilisateur rejoignant la conférence via un point de terminaison PSTN  <br/> |
|Skype pour les utilisateurs de client VoIP d’entreprise à partir d’un site de réseau unique et aux utilisateurs de joindre à partir d’un point de terminaison du réseau RTPC  <br/> |Skype pour l’utilisateur du client à partir du même site de réseau VoIP d’entreprise  <br/> |Skype pour l’utilisateur du client à partir d’un site de réseau VoIP d’entreprise  <br/> Skype pour utilisateur de client VoIP d’entreprise à partir d’un site réseau inconnu  <br/> Skype fédéré pour utilisateur de client VoIP d’entreprise  <br/> |
   
Caractéristiques supplémentaires de routage basées sur l’emplacement pour l’application de conférence sont les suivantes :
  
- Lorsqu’un utilisateur n’est pas autorisé à participer à une conférence, compte tenue des restrictions de routage basé sur l’emplacement, l’appel à la conférence sera rejetée et la Skype pour client d’entreprise rapport que l’appel n’a pas été terminée ou a expiré.
    
- Un RTPC point de terminaison rejoindre qu'une conférence avec applications de routage basé sur l’emplacement ne sera pas limitée à joindre la conférence, quel que soit son état si le point de terminaison joint via une ligne qui n’est pas activée pour le routage basé sur l’emplacement.
    
- Un système PBX connecté à un serveur de médiation via un SIP trunk qui ne pas sortie appels au RTC aura les mêmes applications que Skype pour les utilisateurs professionnels qui se trouvent dans le même site de réseau où est défini le SIP trunk. Par exemple, un point de terminaison du réseau RTPC pourront participer à une conférence avec un utilisateur PBX et un Skype pour l’utilisateur professionnel s’ils sont situés dans le même site de réseau ; dans le cas contraire, le point de terminaison du réseau RTPC pourra pas participer à la conférence si l’utilisateur PBX se trouve dans un site de réseau autre que le Skype pour l’utilisateur professionnel.
    
> [!NOTE]
> Avec la mise à jour cumulative 4 de Skype Entreprise, vous devriez observer le comportement décrit dans le tableau suivant : 
  
|**Utilisateur**|**Autre partie**|**Action**|**Résultat**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype Entreprise Mobile est en appel RTC. Skype Entreprise Mobile transforme ensuite l'appel en standard automatique des conférences (CAA).  <br/> |L’appel est bloqué, avec un message d’erreur correspondant.  <br/> |
|Skype Entreprise Mobile  <br/> |Client ou utilisateur fédéré Skype Entreprise  <br/> |Le Client ou l’utilisateur de fédérés est sur un appel VoIP un Skype pour le routage des Business Mobile Location-Based l’utilisateur, et des parties est transmise à un TCHA.  <br/> |La transformation de l’appel est bloquée, avec un message d’erreur correspondant.  <br/> |
   
## <a name="consultative-call-transfers"></a>Transferts d’appel consultatifs

En plus de la mise en œuvre basée sur l’emplacement de routage à Skype pour les réunions d’entreprise, le routage basé sur l’emplacement pour l’application de conférence applique les restrictions de routage basé sur un emplacement sur les transferts d’appel consultatif qui "sortie" aux points de terminaison TLS. Un transfert d’appel consultatif est un appel établi entre deux parties dans lequel une des parties transfère l’appel vers un nouvel utilisateur. Par exemple, un point de terminaison du réseau RTPC appelle utilisateur (Skype pour appelé d’entreprise). L’utilisateur A détermine que l’utilisateur PSTN doit être transmis à l’utilisateur B (Skype pour utilisateurs des entreprises). L’utilisateur A passe l’appel avec l’utilisateur PSTN en attente, et appelle l’utilisateur B. L’utilisateur B accepte de parler à l’utilisateur PSTN. L’utilisateur A transfère l’appel en attente à l’utilisateur B.
  
**Flux d’appels de transfert consultatif d’appel**

![Diagramme Routage géodépendant pour les conférences](../../media/LocationBasedRoutingForConferencing.jpg)
  
Lorsqu’un utilisateur activé pour le routage basé sur l’emplacement lance un transfert consultatif d’appel d’un point de terminaison PSTN (comme illustré dans la figure précédente), il crée deux appels actifs, un seul appel entre l’utilisateur PSTN et Skype pour l’utilisateur d’entreprise A et l’autre entre Skype pour L’utilisateur A entreprise et Skype pour l’utilisateur professionnel B. le comportement suivant est appliquée par le routage basé sur l’emplacement pour l’application de conférence :
  
- Si le SIP trunk routage RTC appeler est autorisé de rediriger l’appel RTPC vers le site de réseau où se trouve Skype pour l’utilisateur de l’entreprise B (c'est-à-dire target de transfert),, puis le transfert d’appel sera autorisé ; dans le cas contraire, le transfert d’appel consultatif est bloqué. Cette autorisation est effectuée en fonction sur l’emplacement de la partie transfert en cours dans le même site de réseau que le tronc SIP qui distribue l’appel actif, au point de terminaison du réseau RTPC. 
    
- Si le routage des appels entrants RTPC SIP trunk n’est pas autorisé à acheminer les appels vers le site de réseau où se trouve la partie transférée (Skype pour l’utilisateur professionnel B) ou la partie transférée est située dans un site de réseau inconnu, puis l’appel de consultation transférer vers le point de terminaison du réseau RTPC (c'est-à-dire cible de transfert d’appels) sera bloquée.
    
Le tableau suivant décrit comment fondée sur l’emplacement de routage restrictions sont appliquées par le routage basé sur l’emplacement pour l’application de conférence pour les transferts d’appel consultatif. Si les points de terminaison PBX ne sont pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau. Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.
  

|**Site de réseau de la partie de l’appel transféré**|**Site de réseau de la cible de transfert d’appel**|**Comportement**|
|:-----|:-----|:-----|
|Point de terminaison RTC  <br/> |Skype pour les utilisateurs des entreprises sur le même site de réseau (c'est-à-dire le site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Skype pour l’utilisateur professionnel dans les sites de réseau différents (c'est-à-dire le site 2)  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Skype pour les utilisateurs des entreprises dans un site de réseau inconnu  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Skype fédéré pour l’utilisateur professionnel  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans le même site (site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans un autre site (site 2)  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PBX dans le même site (site 1)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un autre site (site 2)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Skype pour les utilisateurs des entreprises sur le même site de réseau (c'est-à-dire le site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Skype pour l’utilisateur professionnel dans les sites de réseau différents (c'est-à-dire le site 2)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Skype pour les utilisateurs des entreprises dans un site de réseau inconnu  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Skype fédéré pour l’utilisateur professionnel  <br/> |Le transfert consultatif est autorisé  <br/> |
   
## <a name="requirements"></a>Configuration requise

Le routage basé sur l’emplacement pour l’application de conférence requiert que soit Skype pour Business Server soit 2 de mise à jour Cumulative de Lync Server 2013 est déployé sur tous les pools frontaux et des serveurs Standard Edition dans votre topologie. Si ces versions de serveur ne sont pas installées sur certains serveurs de votre topologie, restriction de routage basé sur l’emplacement ne peut pas être entièrement appliqué aux réunions et conseils appeler des transferts.
  
Le tableau suivant répertorie la combinaison des rôles de serveur et des versions qui prennent en charge le routage basé sur l’emplacement.
  

|**Version de Pool frontale**|**Version de serveur de médiation**|**Prise en charge**|
|:-----|:-----|:-----|
|Skype pour Business Server ou Lync Server 2013 mise à jour Cumulative 2  <br/> |Skype pour Business Server ou Lync Server 2013 mise à jour Cumulative 2  <br/> |Oui  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Mise à jour cumulative 1 de Lync Server 2013  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Non  <br/> |
|Mise à jour cumulative 1 de Lync Server 2013  <br/> |Indifférente  <br/> |Non  <br/> |
|Lync Server 2010  <br/> |Indifférente  <br/> |Non  <br/> |
|Office Communications Server 2007 R2  <br/> |Indifférente  <br/> |Non  <br/> |
   
## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuration de routage emplacement pour la conférence

Le routage basé sur l’emplacement pour l’application de conférence dépend de la configuration de routage basé sur l’emplacement. Les configurations principales suivantes sont disponibles : 
  
- L’emplacement des participants rejoignant une réunion est déterminé sur la base de leur site réseau. Un site de réseau et de sous-réseaux de son réseau associé doit être défini dans Skype pour Business Server afin de mettre en œuvre le routage basé sur l’emplacement.
    
- Pour appliquer des emplacement de routage des réunions, Skype pour les participants de l’entreprise doit être activé pour le routage basé sur l’emplacement.
    
- Pour appliquer le service de routage basées sur l’emplacement des points de terminaison du réseau RTPC participation à des réunions, le SIP trunk utilisé pour connecter les points de terminaison du réseau RTPC doit être configuré pour le routage basé sur l’emplacement.
    
## <a name="enabling-the-location-based-routing-for-conferencing"></a>L’activation de la gamme fondée sur l’emplacement pour la conférence

Le routage basé sur l’emplacement pour l’application de conférence est désactivé par défaut. Avant d’activer cette application, vous devez déterminer la priorité adaptée à affecter à l’application. Pour déterminer cette priorité, exécutez l’applet de commande suivante dans Skype pour Business Server Management Shell :
  
Get-CsServerApplication-Identity Service : Registrar :<Pool FQDN>dans cette applet de commande, \<FQDN du Pool\> est le pool dans lequel le routage basé sur l’emplacement pour l’application de conférence doit être activé.
  
Cette applet de commande renvoie la liste des applications hébergées par Skype pour Business Server et la valeur de priorité pour chacun d’eux. Le routage basé sur l’emplacement pour l’application de conférence doit être affectée à une valeur de priorité plus grande que l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ». Nous recommandons d’attribuer une valeur de priorité qui est un point supérieur à la valeur de priorité de l’application « UdcAgent » le routage basé sur l’emplacement pour l’application de conférence.
  
Par exemple, si l’application « UdcAgent » a une valeur de priorité de « 2 », l’application « DefaultRouting » a une valeur de priorité de « 8 », l’application « ExumRouting » a une valeur de priorité de « 9 », et l’application « OutboundRouting » a une valeur de priorité de « 10 » puis une valeur de priorité de « 3 », vous devez affecter le routage basé sur l’emplacement pour l’application de conférence. Cela placerait la priorité des applications dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence de routage basées sur l’emplacement (priorité : 3), autres applications (priorités : 4 à 8), » DefaultRouting » (priorité : 9), « ExumRouting » (priorité : 10) et « OutboundRouting » (priorité : 11).
  
Après avoir trouvé la valeur de priorité correct pour le routage basé sur l’emplacement pour l’application de conférence, tapez l’applet de commande suivante pour chaque pool frontal ou un serveur Standard Edition Server que les utilisateurs de maisons activés pour le routage basé sur l’emplacement :
  
Nouvelle-CsServerApplication-Identity Service : inscription :<Pool FQDN>/LBRouting-priorité <Application Priority> -activé $true-critique $true - Uri http://www.microsoft.com/LCS/LBRoutingFor exemple :
  
Nouvelle-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-priorité 3 - $true activé-critique $true - Uri http://www.microsoft.com/LCS/LBRoutingAfter à l’aide de cette applet de commande, de redémarrer tous les serveurs frontaux dans le pool ou les serveurs Standard Edition Server où le Fondée sur l’emplacement de routage pour l’application de conférence a été activée.
  
> [!IMPORTANT]
> Fondée sur l’emplacement des applications de routage aux conférences ou transferts consultatifs ne sera pas respectées jusqu'à ce que tous les serveurs frontaux dans les pools applicables ou les serveurs Standard Edition sont redémarrés. Si vous définissez **-critique** sur **$true** dans les applets de commande précédente, votre Skype pour les services de serveur d’entreprise est immédiatement redémarré. Si vous ne souhaitez pas que ces services pour redémarrer immédiatement, la valeur **-critique** sur **$false** pour aujourd'hui et puis utiliser **Set-CsServerApplication** pour modifier **-critique** sur **$true** ultérieurement, une fois que les services ont été redémarrés.
  
Une fois le routage basé sur l’emplacement pour l’application de conférence a été activée et tous les serveurs applicables ont été redémarrés, organisées par Skype pour les utilisateurs professionnels activés pour le routage basé sur l’emplacement de toutes les conférences seront analysés pour éviter Numéro payant de RTPC ignorer
  

