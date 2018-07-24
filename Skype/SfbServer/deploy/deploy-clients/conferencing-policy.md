---
title: Stratégie de conférence pour les comptes Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Consultez cette rubrique pour découvrir comment attribuer des stratégies de conférence pour Skype Room System.
ms.openlocfilehash: a9eb05c8e29a3db216bc74e5e016c2c6a8413a33
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973422"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Stratégie de conférence pour les comptes Skype Room System
 
Consultez cette rubrique pour découvrir comment attribuer des stratégies de conférence pour Skype Room System.
  
## <a name="conferencing-policy-features"></a>Fonctionnalités de stratégie de conférence

La stratégie de conférence affectée au compte Skype salle système doit avoir certaines caractéristiques. La plupart du temps, le client Skype salle système joint à une réunion planifiée, et par conséquent, la stratégie de conférence de l’organisateur de la réunion a une incidence sur la conférence. Toutefois, dans Skype pour Business Server, certaines fonctionnalités dépendent de configuration du participant. Par exemple, si la stratégie du participant autorise une résolution vidéo maximale de 1080p, les participants rencontrer cette fonctionnalité de vidéo de résolution supérieure à la conférence même si elle ne permet pas la stratégie de l’organisateur. Le tableau suivant décrit plusieurs paramètres dont vous devez être informé lors de la configuration des stratégies de conférence pour les comptes Skype salle système dans votre organisation. 
  
|Fonctionnalité  <br/> |Valeur  <br/> |Commentaire  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Doit être vraie pour son système de salle de Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Doit être vraie pour l’audio Skype salle système fonctionnent dans les sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permet de système de salle Skype restituer MULTIVUE, plusieurs flux vidéo  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Varie selon que le compte est Enterprise Voice (EV) activé (voir les comptes système de salle activation Skype pour Skype pour section de l’entreprise)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Varie selon que le compte est-activé pour Voix Entreprise ou non  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/a (ad hoc) réunions Conférence maintenant, mais Skype salle système peuvent répondre à des sondages dans l’écran au début de la salle  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/a (ad hoc) réunions Conférence maintenant, mais Skype salle système peuvent répondre à des sondages dans l’écran au début de la salle  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Bureau  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/a pour le système de salle Skype. Lorsqu’elle est définie comme TRUE, un interlocuteur distant peut enregistrer  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/a pour le système de salle Skype. Lorsqu’elle est définie comme TRUE, un interlocuteur distant peut enregistrer  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permet au client de système de salle Skype participer aux sessions vidéo d’égal à égal  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/A  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignoré par Skype pour Business Server, le système de salle de Skype utilise HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Affecte des sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Voir la Remarque à la fin de la table\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Il s’agit de la vitesse maximale de transmission vidéo sortante autorisée. Système de salle Skype peut envoyer un flux 1080 ainsi que l’utilisation (si RoundTable est utilisé) à cette vitesse de transmission. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Voir la Remarque à la fin de la table\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/A  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Nous vous conseillons de régler ce paramètre à un niveau aussi élevé que possible. Conditions de réseau dépend de la bande passante effective au moment de la conférence.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Doit avoir la valeur TRUE pour système de salle Skype garantir le flux vidéo multivue  <br/> |
   
* Pour plus d’informations sur la planification de la bande passante, voir les [besoins en bande passante pour le trafic multimédia](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Si le client Skype salle système tente de participer à une réunion planifiée organisée par un utilisateur hébergé sur un pool Lync Server 2010, stratégie de conférence de l’organisateur de la réunion peut empêcher le client de système de salle Skype d’effectuer la collaboration. 
  
## <a name="meeting-authentication"></a>Authentification pour une réunion

Système de salle Skype invite l’utilisateur pour l’authentification lorsqu’ils utilisent la réunion lien participer à participer à une réunion restreinte ; par exemple, une réunion pour la salle options ont été configurées dans Outlook. Ce paramètre est toujours activé pour les réunions personnalisées, et les utilisateurs sont toujours invités. Cependant, pour les réunions non restreintes, les utilisateurs peuvent participer à la réunion sans authentification. 
  
La commande suivante permet aux administrateurs d’exiger une authentification pour toutes les réunions, y compris les réunions non restreintes : 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Par défaut, RequireRoomSystemsAuthorization est définie comme FALSE. 
  

