---
title: Stratégie de conférence pour les comptes Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Consultez cette rubrique pour découvrir comment attribuer des stratégies de conférence pour Skype Room System.
ms.openlocfilehash: 1ffa0065f6df27edb4b5e0bfd39564728ee0a582
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769097"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Stratégie de conférence pour les comptes Skype Room System
 
Consultez cette rubrique pour découvrir comment attribuer des stratégies de conférence pour Skype Room System.
  
## <a name="conferencing-policy-features"></a>Fonctionnalités de stratégie de conférence

La stratégie de conférence attribuée au compte système de salle Skype doit présenter certaines caractéristiques. La plupart du temps, le client de système de salle Skype rejoint une réunion planifiée et la stratégie de conférence de l’organisateur de la réunion affectera donc la Conférence. Néanmoins, dans Skype entreprise Server, certaines fonctions dépendent de la configuration du participant. Par exemple, si la stratégie de la personne autorise une résolution vidéo maximale de 1080p, les participants bénéficieront de cette fonctionnalité vidéo de haute résolution dans la Conférence, même si la stratégie de l’organisateur ne l’autorise pas. Le tableau suivant décrit les différents paramètres que vous devez connaître lors de la configuration des stratégies de conférence pour les comptes de systèmes de salle Skype dans votre organisation. 
  
|Fonctionnalité  <br/> |Valeur  <br/> |Commentaire  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |VRAI  <br/> |Doit être vrai pour la partie audio du système de salle Skype  <br/> |
|AllowIPVideo  <br/> |VRAI  <br/> |Doit être vrai pour que l’audio du système de salle Skype fonctionne dans les sessions de tableau blanc de Conférence maintenant (ad hoc) dans le système de salle Skype  <br/> |
|AllowMultiView  <br/> |VRAI  <br/> |Permet au système de salle Skype de générer des flux vidéo multiples  <br/> |
|AllowParticipantControl  <br/> |VRAI  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AllowAnnotations  <br/> |VRAI  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FAUX  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |VRAI  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FAUX  <br/> |Dépend du mode d’activation du compte (EV) (reportez-vous à la section activation de comptes système de salle Skype pour Skype entreprise)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FAUX  <br/> |Varie selon que le compte est-activé pour Voix Entreprise ou non  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |VRAI  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |VRAI  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AllowExternalUserControl  <br/> |FAUX  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FAUX  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AllowPolls  <br/> |VRAI  <br/> |Non applicable dans les réunions Conférence maintenant (ad hoc), mais le système de salle Skype peut répondre à des sondages sur l’écran au premier plan.  <br/> |
|AllowSharedNotes  <br/> |VRAI  <br/> |Non applicable dans les réunions Conférence maintenant (ad hoc), mais le système de salle Skype peut répondre à des sondages sur l’écran au premier plan.  <br/> |
|EnableDialInConferencing  <br/> |VRAI  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Bureau  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AllowConferenceRecording  <br/> |FAUX  <br/> |Non applicable pour les systèmes de salle Skype. Lorsqu’elle est définie comme TRUE, un interlocuteur distant peut enregistrer  <br/> |
|EnableP2PRecording  <br/> |FAUX  <br/> |Non applicable pour les systèmes de salle Skype. Lorsqu’elle est définie comme TRUE, un interlocuteur distant peut enregistrer  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PVideo  <br/> |VRAI  <br/> |Permet au client de votre système de salle Skype de participer à des sessions d’égal à égal vidéo.  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/A  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignoré par Skype entreprise Server, le système de salle Skype utilise HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |A un impact sur les sessions de tableau blanc de la réunion Skype dans le système de salle Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Voir la note à la fin du tableau\*  <br/> |
|VideoBitRateKB  <br/> |5000  <br/> |Il s’agit de la vitesse maximale de transmission vidéo sortante autorisée. Le système de salle Skype peut envoyer 1 1080 flux, ainsi que l’utilisation de la fonction Panose (si la fonction RoundTable est utilisée) à ce taux de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Voir la note à la fin du tableau\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/A  <br/> |
|TotalReceiveVideoBitRateKB  <br/> |20000  <br/> |Nous vous conseillons de régler ce paramètre à un niveau aussi élevé que possible. La bande passante effective dépend de l’état du réseau au moment de la Conférence.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Doit être vrai pour les systèmes de salle Skype pour s’assurer que les flux vidéo multivues  <br/> |
   
* Pour plus d’informations sur la planification de la bande passante, voir [besoins en bande passante réseau pour le trafic multimédia](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Si le client système de salle Skype essaie de rejoindre une réunion planifiée organisée par un utilisateur qui est hébergé sur un pool Lync Server 2010, la stratégie de conférence de l’organisateur de la réunion peut empêcher le client de système de salle Skype de procéder à la collaboration. 
  
## <a name="meeting-authentication"></a>Authentification pour une réunion

Le système de salle Skype demande aux utilisateurs de s’authentifier quand ils utilisent le lien de participation à une réunion pour participer à une réunion restreinte ; par exemple, une réunion pour laquelle les options d’salle d’attente ont été configurées dans Outlook. Ce paramètre est toujours activé pour les réunions personnalisées, et les utilisateurs sont toujours invités. Cependant, pour les réunions non restreintes, les utilisateurs peuvent participer à la réunion sans authentification. 
  
La commande suivante permet aux administrateurs d’exiger une authentification pour toutes les réunions, y compris les réunions non restreintes : 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Par défaut, RequireRoomSystemsAuthorization est définie comme FALSE. 
  

