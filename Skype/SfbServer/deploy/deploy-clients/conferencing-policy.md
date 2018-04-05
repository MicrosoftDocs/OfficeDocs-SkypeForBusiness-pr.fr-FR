---
title: Stratégie de conférence pour les comptes Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Consultez cette rubrique pour découvrir comment attribuer des stratégies de conférence pour Skype Room System.
ms.openlocfilehash: 07ce5031bd053837d69d3ed3da27aabb344c3a65
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Stratégie de conférence pour les comptes Skype Room System
 
Consultez cette rubrique pour découvrir comment attribuer des stratégies de conférence pour Skype Room System.
  
## <a name="conferencing-policy-features"></a>Fonctionnalités de stratégie de conférence

La stratégie de conférence affectée au compte système local de Skype doit présenter certaines caractéristiques. La plupart du temps, le client Skype espace système joint à une réunion planifiée, et par conséquent la conférence de l’organisateur de la réunion affectera la conférence. Toutefois, dans Skype pour Business Server, certaines fonctionnalités dépendent de configuration sa. Par exemple, si les stratégies du participant permet une résolution vidéo maximale de 1080p, les participants rencontrer cette fonctionnalité vidéo de résolution supérieure à la conférence même si la stratégie de l’organisateur ne l’autorise. Le tableau suivant décrit plusieurs paramètres dont vous devez être informé lors de la configuration des stratégies de conférence pour les comptes Skype espace système dans votre organisation. 
  
|Fonctionnalité  <br/> |Valeur  <br/> |Commentaire  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Doivent être remplies pour l’audio du système de salle de Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Doivent être remplies pour son système de salle Skype fonctionne dans les sessions de tableau blanc (ad hoc) Conférence maintenant dans le système de salle de Skype  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permet de système de salle Skype restituer des vues multiples, plusieurs flux de données vidéo  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Varie selon que le compte est de Voix Entreprise (EV) (voir les comptes système de salle activation Skype pour Skype pour la section de l’entreprise)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Varie selon que le compte est-activé pour Voix Entreprise ou non  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/a dans des réunions Conférence maintenant (ad hoc), mais Skype espace système peuvent répondre à des sondages sur l’écran à l’avant de la salle  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/a dans des réunions Conférence maintenant (ad hoc), mais Skype espace système peuvent répondre à des sondages sur l’écran à l’avant de la salle  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Bureau  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/a pour système de salle de Skype. Lorsqu’elle est définie comme TRUE, un interlocuteur distant peut enregistrer  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/a pour système de salle de Skype. Lorsqu’elle est définie comme TRUE, un interlocuteur distant peut enregistrer  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permet au client de système de salle Skype participer à des sessions vidéo de peer-to-peer  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/A  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignoré par Skype pour Business Server, le système de salle de Skype utilise HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Affecte la conférence maintenant les sessions de tableau blanc (ad hoc) dans le système de salle de Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Voir la Remarque à la fin de la table\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Il s’agit de la vitesse maximale de transmission vidéo sortante autorisée. Système de chambre de Skype peut envoyer un flux 1080 ainsi que de l’utilisation (si RoundTable est utilisée) à cette vitesse de transmission. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Voir la Remarque à la fin de la table\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/A  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Nous vous conseillons de régler ce paramètre à un niveau aussi élevé que possible. La bande passante effective dépend des conditions du réseau au moment de conférences.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Doit avoir la valeur TRUE pour système de salle Skype garantir le flux de données vidéo multivue  <br/> |
   
* Pour plus d’informations sur la planification de la bande passante, consultez les [Besoins en bande passante pour le trafic multimédia](https://technet.microsoft.com/en-us/library/jj688118%28v=ocs.15%29.aspx).
  
> [!NOTE]
> Si le client Skype espace système essaie de participer à une réunion planifiée organisée par un utilisateur qui est hébergé sur un pool Lync Server 2010, stratégie de conférence de l’organisateur de la réunion peut empêcher le client de Skype espace système de réalisation de collaboration. 
  
## <a name="meeting-authentication"></a>Authentification pour une réunion

Système de salle Skype demande à l’utilisateur pour l’authentification lorsqu’ils utilisent la réunion lien de jointure pour joindre une réunion restreinte ; par exemple, il s’agit d’une réunion pour la salle d’options ont été configurées dans Outlook. Ce paramètre est toujours activé pour les réunions personnalisées, et les utilisateurs sont toujours invités. Cependant, pour les réunions non restreintes, les utilisateurs peuvent participer à la réunion sans authentification. 
  
La commande suivante permet aux administrateurs d’exiger une authentification pour toutes les réunions, y compris les réunions non restreintes : 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Par défaut, RequireRoomSystemsAuthorization est définie comme FALSE. 
  

