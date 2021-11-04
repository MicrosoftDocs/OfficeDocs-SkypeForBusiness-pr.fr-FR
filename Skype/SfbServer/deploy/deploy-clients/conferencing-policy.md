---
title: Stratégie de conférence pour les comptes Skype Room System
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Lisez cette rubrique pour découvrir comment affecter des stratégies de conférence pour Skype comptes Room System.
ms.openlocfilehash: 9e6bab608ab68b3f0e0d5075ae1caf8cb16d4c0b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771676"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Stratégie de conférence pour les comptes Skype Room System
 
Lisez cette rubrique pour découvrir comment affecter des stratégies de conférence pour Skype comptes Room System.
  
## <a name="conferencing-policy-features"></a>Fonctionnalités de stratégie de conférence

La stratégie de conférence attribuée au compte Skype Room System doit avoir certaines caractéristiques. La plupart du temps, le client Skype Room System rejoint une réunion programmée et, par conséquent, la stratégie de conférence de l’organisateur de la réunion affecte la conférence. Toutefois, dans Skype Entreprise Server, certaines fonctionnalités dépendent de la configuration du participant. Par exemple, si la stratégie du participant autorise une résolution vidéo maximale de 1080 p, les participants auront besoin de cette fonctionnalité vidéo de résolution supérieure dans la conférence, même si la stratégie de l’organisateur ne l’autorise pas. Le tableau suivant décrit plusieurs de ces paramètres que vous devez connaître lors de la configuration des stratégies de conférence pour les comptes Skype Room System dans votre organisation. 
  
|Fonctionnalité  <br/> |Valeur  <br/> |Commentaire  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Doit être vrai pour l’audio Skype Room System  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Doit être true pour que Skype’audio Room System fonctionne dans les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permet à Skype Room System de restituer plusieurs flux vidéo à plusieurs vues  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Dépend si le compte est activé Voix Entreprise (EV) (voir la section Activation Skype Room System pour Skype Entreprise)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Dépend si le compte est activé Voix Entreprise (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A dans les réunions Conférence maintenant (ad hoc), mais Skype Room System peut répondre aux sondages à l’écran à l’avant de la salle  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A dans les réunions Conférence maintenant (ad hoc), mais Skype Room System peut répondre aux sondages à l’écran à l’avant de la salle  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|EnableAppDesktopSharing  <br/> |Ordinateur de bureau  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A pour Skype Room System. Si la valeur est TRUE, une partie distante peut enregistrer  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A pour Skype Room System. Si la valeur est TRUE, une partie distante peut enregistrer  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permet au client Skype Room System de participer à des sessions vidéo d’égal à égal  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/A  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignoré par Skype Entreprise Server, Skype Room System utilise HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Affecte les sessions de tableau blanc Conférence maintenant (ad hoc) dans Skype Room System  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Voir la remarque à la fin du tableau\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Il s’agit de la vitesse de bits vidéo sortante maximale autorisée. Skype Room System peut envoyer un flux de 1 080 avec le volet (si RoundTable est utilisé) à cette vitesse de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Voir la remarque à la fin du tableau\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/A  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Nous vous recommandons de définir cette valeur aussi élevée que possible. La bande passante effective dépend des conditions réseau au moment des conférences.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Doit être TRUE pour Skype Room System pour garantir des flux vidéo à plusieurs vues  <br/> |
   
* Pour plus d’informations sur la planification de la bande passante, voir [La bande passante réseau requise pour le trafic multimédia.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Si le client Skype Room System tente de participer à une réunion programmée organisée par un utilisateur qui est homed sur un pool Lync Server 2010, la stratégie de conférence de l’organisateur de la réunion peut empêcher le client Skype Room System d’effectuer la collaboration. 
  
## <a name="meeting-authentication"></a>Authentification de réunion

Skype Le système de salle invite les utilisateurs à s’authentifier lorsqu’ils utilisent le lien de rejoindre une réunion pour participer à une réunion restreinte . par exemple, une réunion pour laquelle les options de salle d’Outlook. Ce paramètre est toujours en cours pour les réunions personnalisées et les utilisateurs sont toujours invités. Toutefois, pour les réunions non restreintes, les utilisateurs peuvent participer à la réunion sans authentification. 
  
La commande suivante permet aux administrateurs d’exiger une authentification pour toutes les réunions, y compris les réunions non restreintes : 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Par défaut, RequireRoomSystemsAuthorization a la valeur FALSE. 
  

