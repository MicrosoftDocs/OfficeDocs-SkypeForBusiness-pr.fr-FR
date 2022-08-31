---
title: Données de diagnostic de mobiles requises pour Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Une liste des propriétés de mobiles et des événements de contrôles des stratégies pour Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91203a9e35954e695bea5482c41674137320b487
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674236"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Données de diagnostic de mobiles requises pour Microsoft Teams

L’article suivant contient une liste des événements de mobiles Microsoft Teams, et pour chacun de ces événements la liste des propriétés collectées.

Pour plus d’informations sur les données de diagnostic, notamment sur la façon de contrôler les données de diagnostic envoyées à Microsoft, consultez [Données de diagnostic envoyées de l’application Teams à Microsoft](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft). Pour afficher les données de diagnostic envoyées à Microsoft, vous pouvez utiliser la [Visionneuse de données de diagnostic](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

## <a name="events"></a>Événements

> [!NOTE]
> Il existe des propriétés communes pour tous les événements répertoriés ci-dessous, pour les découvrir, consulter la section [Propriétés envoyées avec tous les événements](#properties-sent-with-all-events).

### <a name="panelaction"></a>PanelAction

> [!NOTE]
> Pour en savoir plus sur les propriétés des événements PanelAction, consulter la section [Propriétés envoyées avec les événements PanelAction](#properties-sent-with-panelaction-events).

- **acceptUser** : l’utilisateur a accepté une conversation 1:1.
- **accessibilityUserConfiguration** : lorsqu’un utilisateur bascule une fonctionnalité d’accessibilité.
- **acknowledgeSettingChange** : l’utilisateur prend connaissance d’une mise à jour dans la boîte de dialogue Nous avons mis à jour un paramètre de notification. Ceci est un indicateur de performance de fonctionnalité utilisé pour la prise de connaissance de notifications et pour déterminer la fiabilité globale des notifications.
- **actionComposeMenu**
  - Utilisation d’extension de message de création.
  - Utilisation d’extension de message d’action.
- **active_session_banner_dismissed** : la bannière de rappel active de partage de position a été masquée.
- **activityChatClicked** : appui sur une conversation non-directe dans l’onglet **Activité** ou affichage en mode fractionné.
- **activityContextMenu** : actions de dépassement de capacité dans le flux d’activités.
- **activityFeedClick** : l’utilisateur appuie sur un élément de flux d’activités et accède à une conversation avec un robot.
- **activityFeedLongPress** : capture des gestes de pression longue sur des éléments du flux.
- **activityFeedSwipe** : capture des gestes de balayage sur des éléments du flux.
- **activityFilterClick** : capture l’utilisation des filtres d’activités.
- **activityFilterOptionsClick** : capture l’utilisation des filtres d’activités.
- **activityFilterOptionsClicked** : capture l’utilisation des filtres d’activités.
- **activityLiveChatClicked** : appui sur une conversation dans une réunion en cours dans l’onglet **Activité**.
- **activityLiveDetailsClicked**: appui sur **Détails** dans une réunion en cours dans l’onglet **Activité**.
- **activityTabClicked** permet de déterminer si :
  - l’onglet **Activité** est affiché ;
  - Teams capture un événement dans l’onglet **Activité**.
- **activityTypeDropdown** : capture de l’utilisation de filtres d’activités pour basculer entre **Mon activité** et **Flux**.
- **addChannel** : un canal est ajouté. Cet élément fournit des données de performance sur la création réussie d’un canal.
- **addMember** : appui sur **Inviter des contacts** dans le menu **Plus**.
- **addMembers** : Ajouter des membres à une équipe ou à un canal privé.
- **addToCalendar** : appui sur **Ajouter au calendrier** pour les événements du calendrier manquants dans le calendrier privé.
- **addToList** : un contact est ajouté à la liste des contacts.
- **addToMeeting** : appui sur **Ajouter à la réunion** dans la liste des participants à une réunion (pour les participants qui font partie de la conversation).
- **addUserAsContact** : un contact est ajouté en appuyant sur l’icône **Ajouter le contact** depuis la carte de visite du contact.
- **admitAll** : nombre de fois que le bouton **Autoriser tout le monde** est appuyé dans la salle d'attente.
- **admitParticipant** : nombre de fois qu’une personne est admise dans une réunion depuis la liste de présence de la réunion.
- **alertsNavAlert** : appui sur un élément de flux.
- **aliasDiscoverabilitySettingOpened** : point d’entrée des paramètres de discoverabaility.
- **Android : null** : Activer ou Désactiver une conversation de robot. Ceci améliore la télémétrie existante concernant les conversations, et ne fait qu’ajouter des informations sur l’application.
- **anonymousMeetingJoinappui** - appui sur **Participer à la réunion** sur une page d’indication du nom pour rejoindre anonymement, ou sur **OK** dans la boîte de dialogue de nom.
- **anonymousMeetingJoinWelcomeJoin** - appui sur **Rejoindre en tant qu’invité** sur une page d’arrivée pour rejoindre anonymement une réunion.
- **anonymousMeetingPostMeetingChat** : nombre d’affichages de la conversation par les utilisateurs depuis l’écran de fin d’appel.
- **anonymousMeetingPostMeetingRejoin** : nombre de fois que l’utilisateur anonyme essaye de rejoindre une réunion.
- **anonymousMeetingSignIn** : nombre de fois que l’utilisateur accède à la connexion depuis l’écran d’entrée du nom.
- **anonymousMeetingSignInWelcome** : appui sur **Me connecter et rejoindre** sur une page d’arrivée pour rejoindre anonymement une réunion.
- **anonymousMeetingToggleMuted** : nombre de fois que le bouton bascule de désactivation du son a été sélectionné.
- **anonymousMeetingToggleVideo** : nombre de fois que le bouton bascule de désactivation de l’image a été sélectionné.
- **appKilled** : l’application est interrompue.
- **approveTimeOffRequest** : Lorsqu’une demande de congé d’un travailleur de première ligne est approuvée par le manager des travailleurs de première ligne.
- **assigneeChange** : une nouvelle personne affectée est ajoutée à un élément de tâche.
- **assignmentPickerClicked** : appui sur **Affecter à**, ce qui ouvre une page de sélecteur de personnes à affecter à un élément de tâche.
- **assignmentRemoved** : une personne affectée est retirée d’un élément de tâche par l’appui sur **x** (ce qui est la seule façon de retirer une personne affectée).
- **attachmentAdded** : confirmation de l’ajout réussi d’un document dans la tâche.
- **attachmentDeleted** : confirmation de la suppression réussie d’un document dans la tâche.
- **attachmentUpdated** : confirmation de la mise à jour réussie d’un document dans la tâche.
- **audioOnlyLowBatteryBanner** : appui sur l’option **Audio uniquement** en raison d’une bannière de batterie faible.
- **audioOnlyPoorNetworkBanner** : appui sur l’option **Vidéo désactivée** en raison d’une bannière de connexion médiocre.
- **audioUserDoubleTap** : appui double sur un participant audio.
- **autoReconnectCallmebackCallDrop** : nombre de fois que le bouton **Me rappeler** a été appuyé sur l’écran de fin d’appel.
- **autoReconnectDialIn** se déclenche lorsque :
  - appui sur **Composer** sur le diagnostic convivial (UFD) de reconnexion ;
  - nombre de fois que le bouton **Composer** a été appuyé lors d’une reconnexion.
- **autoReconnectDialInonCallDrop** : appui sur **Composer** sur le diagnostic convivial (UFD) d’appel interrompu.
- **autoReconnectDialOut** : appui sur **Me rappeler** sur le diagnostic convivial (UFD) de reconnexion.
- **autoReconnectRejoinonCallDrop** : nombre de fois que les bouton **Rejoindre** ou **Recomposer** ont été appuyés sur l’écran de fin d’appel.
- **backFromCallMePSTN** : débit de nombres RTCP Me rappeler inachevé.
- **backToPhotoShare** : l’utilisateur retourne à une caméra.
- **backToStageFromWhiteboard** : l’utilisateur retourne à un écran d’appel depuis un tableau blanc.
- **backToWhiteboardFromStage** : l’utilisateur accède à un tableau blanc depuis un écran d’appel.
- **blockAnonymous** se déclenche lorsque :
  - le paramètre d’appel pour bloquer les appels sans ID de l’appelant est activé depuis les paramètres ;
  - le paramètre d’appel pour bloquer les appels sans ID de l’appelant est désactivé depuis les paramètres ;
  - le paramètre d’appel pour bloquer les appels sans ID de l’appelant est activé depuis une feuille d’action ;
  - le paramètre d’appel pour bloquer les appels sans ID de l’appelant est désactivé depuis une feuille d’action.
- **blockCaller** : l’utilisateur bloque :
  - un numéro et contact depuis la nouvelle feuille d’action d’appels iOS ;
  - un contact et un numéro depuis la carte de visite ;
  - des numéros depuis les paramètres.
- **blockChat** : une conversation de robot est bloquée. Ceci améliore la télémétrie existante concernant les conversations, et ne fait qu’ajouter des informations sur l’application.
- **botClickCardAction** : utilisation de la carte de connecteur.
- **brbFormOpened** : l’utilisateur a demandé à envoyer des commentaires.
- **brbFormSubmit** : l’utilisateur a envoyé des commentaires.
- **breakStartEndClicked** : appui sur **Début** ou **Fin de la pause** sur l’écran de pointage.
- **breakStartEndTriggered** : choix de l’utilisateur de prendre ou terminer sa pause.
- **bucketSelected** : confirmation de la sélection réussie d’un compartiment.
- **bucketUnselected** : confirmation de la désélection réussie d’un compartiment.
- **bucketPickerClicked** : confirmation du démarrage réussi du sélecteur de compartiments.
- **BYOELiveEventJoin** : l’utilisateur rejoint un événement en direct BYOE (Broadcast your own event).
- **calendarLiveChatClicked** : Conversation d’une réunion en cours dans l’onglet **Planification**.
- **calendarMeetingJoinMeeting** - appui sur **Participation à une réunion** depuis le calendrier.
- **calendarTab** : appui sur l’onglet **Réunions** dans le rail inférieur. Utile pour la compréhension de l’utilisation du calendrier et pour la comparaison avec d’autres applications sur le rail inférieur, ou pour déterminer si une défaillance s’est produite lors du rendu du billet de calendrier après sélection à partir de la barre inférieure.
- **calendarTabClicked** : Dans les circonstances décrites ci-dessous, l’utilisation du calendrier s’affiche et permet de comparer avec d’autres applications de la barre de navigation sur le rail inférieur. Aide à déterminer si une défaillance s’est produite lorsque :
  - l’onglet **Planification** s’affiche ;
  - l’onglet **Réunions** est sélectionné sur le rail inférieur.
- **calendarUpcomingChatClicked** : Conversation d’une réunion prochaine dans l’onglet **Planification**.
- **callAccepted** : un appel est accepté.
- **callAcceptedSFB** : un appel est accepté.
- **callappPreference** : une application d’appel préférée est sélectionnée.
- **callControlsManualDismiss** : les contrôles d'appel sont masqués manuellement.
- **callControlsManualInvoke** : les contrôles d'appel sont invoqués manuellement.
- **callHistoryItemExpand** : un élément d’historique d’appels est développé.
- **callHistory** - appui sur l’onglet **Historique d’appels** dans Appels.
- **callInProgressShown** : une bannière **_Appel en cours_* est affichée.
- **callMePSTNConnected** - réussite de **M’appeler**.
- **callOrMeetUpAddParticipants** se déclenche lorsque :
  - Ajouter un participant est appuyé sur un écran d’appel à deux ;
  - une personne est sélectionnée (VoIP) dans Ajouter des participants ;
  - un RTCP est sélectionné dans Ajouter des participants ;
  - des personnes sont ajoutées dans une réunion privée en cours ;
  - un RTCP est sélectionné dans une réunion privée en cours ;
  - un contact de la société est sélectionné dans une réunion privée en cours ;
  - un contact de l’appareil est sélectionné dans une réunion privée en cours ;
  - l’ajout de participants est effectué dans une réunion privée en cours ;
  - des personnes sont ajoutées dans une réunion de canal en cours ;
  - un RTCP est sélectionné dans une réunion de canal en cours ;
  - un membre d’équipe est sélectionné dans une réunion de canal en cours ;
  - un contact de l’appareil est sélectionné dans une réunion de canal en cours ;
  - l’ajout de participants est effectué dans une réunion de canal en cours.
- **callOrMeetUpAddParticipantsDone** : l’utilisateur finalise l’ajout de participants.
- **callOrMeetUpAddRoom** se déclenche lorsque :
  - **Ajouter une salle** est sélectionné dans la liste de présence ;
  - un résultat de recherche est sélectionné dans Ajouter une salle ;
  - **Masquer** est sélectionné pour À proximité ;
  - **Activer BlueTooth** ou **Position** sont sélectionnés pour À proximité ;
  - un résultat de salle à proximité est sélectionné dans Ajouter une salle ;
  - un résultat de salle suggérée est sélectionné dans Ajouter une salle ;
  - **Terminé** est sélectionné dans Ajouter une salle.
- **callOrMeetUpAudioOffSwitch** : actionnement du bouton **Son désactivé** en mode de participation compagnon dans un appel en cours ou un meet-up.
- **callOrMeetUpAutoReconnect** : mode de reconnexion automatique activé sur l’appareil de l’utilisateur en raison de performances réseau médiocres.
- **callOrMeetUpCallAccepted** se déclenche lorsque :
  - un appel est accepté ;
  - un appel RTCP est accepté.
- **callOrMeetUpCallEnded** se déclenche lorsque :
  - un bouton **Raccrocher** est appuyé ;
  - un bouton **Appel terminé** est appuyé lors de callOrMeetupLive ;
  - un bouton **Appel terminé** est appuyé lors de lockScreen ;
  - un bouton **Appel terminé** est appuyé lors de notification ;
  - un bouton **Appel terminé** est appuyé lors d’inApp ;
  - un bouton **Appel terminé** est appuyé lors de callKit ;
  - un bouton **Appel terminé** est appuyé pour un appel RTCP.
- **callOrMeetUpChatWithParticipants** : bascule de conversations lors d’une réunion en cours ou d’un appel.
- **callOrMeetUpDeviceAudioSwitch** se déclenche lorsque :
  - passage de la source audio vers le haut-parleur ;
  - passage de la source audio vers l’appareil ;
  - passage de la source audio vers Bluetooth ;
  - passage de la source audio vers Son désactivé ;
  - passage du haut-parleur lors d’une réunion en cours ou d’un appel ;
  - passage du haut-parleur vers Son désactivé lors d’une réunion en cours ou d’un appel ;
  - actionnement du bouton **Son désactivé** en mode de participation compagnon lors d’un appel en cours ou un meet-up ;
  - bascule du son de l’appareil lors d’un appel RTCP.
- **callOrMeetUpEnterDriveMode** : passage manuel au mode Conduite depuis le menu **…**.
- **callOrMeetupExitDriveMode** - appui sur le bouton **Quitter le mode Conduite**.
- **callOrMeetUpHold** se déclenche lorsque :
  - **Mettre en attente** est appuyé lors d’une réunion en cours ou d’un appel ;
  - Mise en attente d’un appel RTCP.
- **callOrMeetUpIncomingVideoSwitch** : IncomingVideo est désactivé lors d’une réunion en cours ou d’un appel.
- **callOrMeetUpInvitedParticipants** se déclenche lorsque :
  - **Tout afficher** est appuyé en bas d’un groupe de participants **Autres invités** lors d’une réunion privée en cours ;
  - **Tout afficher** est appuyé en bas d’un groupe de participants **Autres invités** lors d’une réunion de canal en cours ;
- **callOrMeetUpJoinedParticipants** se déclenche lorsque :
  - **Tout afficher** est appuyé en bas d’un groupe de participants **Participants de la réunion** lors d’une réunion privée en cours ;
  - **Tout afficher** est appuyé en bas d’un groupe de participants **Participants de la réunion** lors d’une réunion de canal en cours ;
- **callOrMeetUpLobbyParticipants** se déclenche lorsque :
  - **Tout afficher** est appuyé en bas d’un groupe de participants **Salle d'attente** lors d’une réunion privée en cours ;
  - **Tout afficher** est appuyé en bas d’un groupe de participants **Salle d'attente** lors d’une réunion de canal en cours.
- **callOrMeetUpMicrophoneSwitch** se déclenche lorsque :
  - le microphone est activé ;
  - le microphone est désactivé ;
  - le bouton **Microphone** est appuyé lors d’une réunion en cours ou d’un appel ;
  - l’état du microphone est basculé lors d’un appel RTCP.
- **callOrMeetUpMuteParticipant** : un participant distant est désactivé.
- **callOrMeetUpMuteParticipants** : tous les participants d’une réunion en cours ou d’un appel sont désactivés.
- **callOrMeetUpParticipants** : bascule de participants lors d’une réunion en cours ou d’un appel.
- **callOrMeetUpRemoteMuteUFD** : diagnostic convivial (UFD) Votre micro a été désactivé.
- **callOrMeetUpResume** se déclenche lorsque :
  - le bouton **Reprendre** est appuyé lors d’une réunion en cours ou d’un appel ;
  - un appel RTCP est repris.
- **callOrMeetUpSearchParticipants** se déclenche lorsque :
  - **Rechercher** est appuyés dans les participants d’une réunion lors d’une réunion privée en cours ;
  - **Rechercher** est appuyé après affichage du groupe de participants **Salle d'attente** lors d’une réunion privée ;
  - **Rechercher** est appuyé après affichage du groupe de participants **Participants de la réunion** lors d’une réunion privée ;
  - **Rechercher** est appuyé après affichage du groupe de participants **Autres invités** lors d’une réunion privée ;
  - **Rechercher** est appuyé dans les participants d’une réunion lors d’une réunion de canal en cours ;
  - **Rechercher** est appuyé après affichage du groupe de participants **Salle d'attente** lors d’une réunion de canal en cours ;
  - **Rechercher** est appuyé après affichage du groupe de participants **Participants de la réunion** lors d’une réunion de canal en cours ;
  - **Rechercher** est appuyé après affichage du groupe de participants **Autres invités** lors d’une réunion de canal en cours.
- **callOrMeetUpVideoSwitch** se déclenche lorsque :
  - la vidéo est activée ;
  - la vidéo est désactivée ;
  - le bouton de vidéo est appuyé lors d’une réunion en cours ou d’un appel.
- **callPark** se déclenche lorsque :
  - **Park Call** est sélectionné dans le menu **...** .
  - **Récupérer** est appuyé ;
  - **Décrocher** est appuyé dans la boîte de dialogue de récupération ;
  - **Annuler** est appuyé dans la boîte de dialogue de récupération.
- **callPreferenceSetting** : paramètre d’application de préférence d’appel.
- **callsTabNewCall** - appui sur **Nouvel appel** dans l’onglet **Appels**.
- **callTransfer** : un transfert d’appel est commencé.
- **callVoicemailTab** - appui sur l’onglet **Message vocal** dans Appels.
- **cameraPermissionCancel** - appui sur **Annuler** dans la boîte de dialogue d’autorisation d’accès à la caméra.
- **cameraPermissionGoToSettings** - l’utilisateur accède aux **Paramètres** depuis la boîte de dialogue d’autorisation d'accès à la caméra.
- **cancelEditMeeting** : appui sur **Fermer** sur la page de planificateur de réunion après avoir appuyé sur **Modifier la réunion**. Ceci permet de journaliser l’abandon par l’utilisateur de la sélection de la modification de la réunion.
- **cancelFileShare** - appui sur **Annuler** dans la boîte de dialogue de confirmation.
- **cancelFileUpload** - appui sur **x** dans la boîte de dialogue de chargement de fichier.
- **cancelMeeting** : appui sur **Annuler l’événement** depuis la page Détails de la réunion. Utilisé pour l’obtention de données agrégées sur le nombre de réunions annulées.
- **cancelNavigationToLink** : Annuler la navigation est choisi.
- **cancelRequestToJoinTeam** : Annuler la demande de participation à une équipe.
- **cancelRequestToJoinTeamError** : erreur lors d’une annulation de demande de participation.
- **cancelNewMeeting** : journalise les abandons de sélections de Créer une réunion et en vérifie les raisons :
  - le bouton **Fermer** est appuyé sur la page de planificateur de réunions.
  - le bouton **Fermer** est appuyé sur la page de planificateur de réunions après avoir appuyé sur **Modifier la réunion en ligne**.
- **cardView – aucun AS affecté** : affichage et rendu de la carte. Les cartes sont des constructions de plateforme clés et la mesure de leur utilisation et de leur motif est nécessaire à la compréhension de l’utilisation de la plateforme et à la surveillance de l’apparition de problèmes potentiels du côté client. Cet élément est requis pour mesurer toute erreur survenant lorsque l’utilisateur rejoint une équipe.
- **castPpt** se déclenche lorsque :
  - une option PowerPoint est sélectionnée ;
  - un PowerPoint en particulier est sélectionné ;
  - le dossier Équipes et Canaux est sélectionné sur la page de sélecteur de fichiers ;
  - un dossier OneDrive est sélectionné sur la page de sélecteur de fichiers ;
  - la session de diffusion est interrompue ;
  - un appui est effectué sur une incrustation d’image multitâche ;
  - une option d’affichage est sélectionnée depuis l’affichage des fichiers.
- **castScreen** se déclenche lorsque :
  - un appui est effectué sur l’option de partage d’écran ;
  - la session de partage d'écran est interrompue ;
  - une option d’affichage est sélectionnée depuis l’affichage des fichiers.
- **center_on_team_clicked** : l’utilisateur effectue un recentrage réussi de la carte sur des groupes.
- **channelFollow** : Activer les notifications pour un canal.
- **channelUnfollow** : Désactiver les notifications pour un canal.
- **channelsActiveSetting** : le paramètre de notification **M’avertir lorsque je suis actif sur le bureau** est modifié.
- **chatCreation** : une conversation est créée.
- **changeIsActiveSetting** : notification basée sur l’activité de bureau.
- **channel** : bouton ou zone de texte Nouveau message dans la conversation.
- **channelDetails** : informations de navigation dans le canal lorsque :
  - un en-tête de canal est appuyé ;
  - l’utilisateur accède à la page Détails du canal.
- **channelFollow/channelUnfollow** : Suivre ou Arrêter de suivre un  canal.
- **channelNav** : l’utilisateur accède au canal, quelle que soit sa provenance.
- **channelNavTab** : fournit des données de performance et de détectabilité pour les fichiers Teams lorsque :
  - l’onglet **Fichiers** est sélectionné dans un canal ;
  - il y a une réponse de carte de connecteur.
- **channelNotificationSettings** se déclenche lorsque :
  - la boîte de dialogue **Nouveaux paramètres de notification** est sélectionnée ;
  - le bouton Paramètres de notification du canal est sélectionné dans la vue du canal ;
  - un paramètre de notification du canal est sélectionné.
- **channelSelected** : confirmation de la sélection réussie d’un canal pour un nouveau plan.
- **channelSendMessage** se déclenche lorsque :
  - un message de canal est envoyé ;
  - un robot est @mentionné dans une zone de rédaction.
- **channelTabOverflow** : appui sur l’onglet **Plus** dans un canal.
- **chat** se déclenche lorsque :
  - bouton ou zone de texte Nouveau message dans la conversation ;
  - une conversation à deux est sélectionnée dans un élément de l’historique d’appels ;
  - une conversation à deux est sélectionnée dans la liste d’appels.
- **chat – aucun AS affecté** : une conversation non lue est affichée ou la liste de présence de la conversation est modifiée, en particulier lorsque :
  - le bouton **Terminé** est appuyé lors de l’ajout d’un utilisateur à une conversation ;
  - un filtre de liste des conversations est sélectionné pour filtrer par messages non lus.
- **chatAddChat** : appui sur le bouton Ajouter un membre à la conversation (identique pour les conversations à deux et les conversations de groupes).
- **chatAllowJoinViaLink** : les fonctionnalités de liens de participation sont activés ou désactivés sur la page Détails de la conversation.
- **chatAvatarEdit** : nombre de groupes ayant changé leurs avatars depuis la page Détails de la conversation.
- **chatAvatarEditCamera** : l’utilisateur modifie son avatar depuis le flux d’une caméra en direct.
- **chatAvatarEditGallery** : l’utilisateur modifie son avatar depuis la galerie de son téléphone.
- **chatAvatarEditView** : l’utilisateur affiche l’image d’avatar existante.
- **chatListNavConversations** : appui sur un élément de la liste des conversations.
- **chatCancelAudioCall** : un appel audio de groupe est annulé – boîte de dialogue de confirmation.
- **chatCancelVideoCall** : un appel vidéo de groupe est annulé – boîte de dialogue de confirmation.
- **chatCM_CopyText** : appui sur **Copier le texte** dans un menu contextuel de conversation.
- **chatCM_DeleteMessage** : appui sur **Supprimer le message** dans un menu contextuel de conversation.
- **chatCM_edit** : appui sur **Modifier** dans un menu contextuel de conversation.
- **chatCM_Forward** : appui sur **Transférer** dans un menu contextuel de conversation.
- **chatCM_markUnread** : appui sur **Marquer comme non lu** dans un menu contextuel de conversation.
- **chatCM_save** : appui sur **Enregistrer** dans un menu contextuel de conversation.
- **chatCM_SeenBy** : appui sur **Lu** dans une option de menu contextuel. Confirmations de lecture, telles que « lu par » (readby).
- **chatContactsEnter** : l’utilisateur accède à l’onglet **Contacts de conversation**.
- **chatDetails** : fournit des données de performance et de détectabilité pour la page Détails de la conversation lorsque :
  - un en-tête de conversation est appuyé ;
  - l’utilisateur accède à la page Détails de la conversation.
- **chatRecentEnter** : l’utilisateur accède à l’onglet **Conversation récente**.
- **chatSendMessage** : un message de conversation est envoyé.
- **chatShareLink** : nombre d’utilisateurs ayant envoyé un lien d’invitation à un groupe.
- **chatStartAudioCall** se déclenche lorsque :
  - un appui est effectué sur le bouton d’appel audio à deux ;
  - un appui est effectué sur le bouton **Audio** sur un résultat de recherche ;
  - un appui est effectué sur le bouton **Démarrer l’appel** à droite ;
  - un appui est effectué sur le bouton d’appel audio à deux depuis un élément de l’historique d’appels ;
  - un appui est effectué sur le bouton d’appel audio à deux depuis un élément de messagerie vocale ;
  - un appel audio de groupe est effectué – boîte de dialogue de confirmation.
- **chatStartAudioCallOnBehalfOf** : le délégué démarre un appel depuis la feuille d’action en tant que Patron.
- **chatStartAudioCallOnBehalfOfMyself** : le délégué démarre un appel depuis la feuille d’action en tant que Moi.
- **chatStartAudioCallSFB** : appui sur le bouton d’appel audio à deux.
- **chatStartVideoCall** se déclenche lorsque :
  - un appui est effectué sur le bouton d’appel vidéo à deux ;
  - un appui est effectué sur le bouton d’appel vidéo dans un résultat de recherche ;
  - un appui est effectué sur le bouton d’appel vidéo à deux depuis l’historique d’appels ;
  - un appel vidéo de groupe est effectué – boîte de dialogue de confirmation.
- **chatStartVideoCallSFB** : appui sur le bouton d’appel vidéo.
- **chatWithMeetingParticipants** : appui sur l’onglet **Conversation** depuis la page Détails de la réunion.
- **checkListAddClicked** - appui sur **Ajouter un élément** dans l’affichage des détails d’une tâche pour la section de liste de contrôle.
- **checkListItemAdded** : un élément de liste de contrôle est créé pour une tâche.
- **checkListItemDeleted** : un élément de liste de contrôle est supprimé d’une tâche.
- **checkListItemUpdated** : un élément de liste de contrôle est mis à jour pour une tâche.
- **channelPickerClicked** : confirmation du démarrage réussi du sélecteur de canaux.
- **checklistSeeAllClicked** : appui sur **Tout afficher** dans les détails d’une tâche afin d’afficher tous les éléments de la liste de contrôle.
- **chicletExpand** : aide à la compréhension de la prévisualisation des cartes sur mobiles et du comportement à la fermeture de ces prévisualisations.
- **clearFilter** : tous les filtres sont retirés lors de l’affichage d’une liste de contrôle.
- **clickPhotoOfficeLens** : appui sur **Prendre une photo** ; la caméra est démarrée (Android uniquement).
- **clockInEntryTeamSelectionShown** : l’utilisateur sélectionne une équipe pour la pointeuse sans avoir pointé.
- **clockInOutClicked** : appui sur **Pointer l'arrivée** ou **Pointer la sortie** sur l’écran de pointage.
- **clockInOutTriggered** : enregistrement du pointage d’arrivée ou de sortie de l’utilisateur ; ne se déclenche qu’une fois la position vérifiée (si la position est requise).
- **closedBannerMessage** : le message de bannière d’une notification est fermé.
- **closeLobbyBanner** : nombre de fois que le toast de salle d’attente est fermé à l’aide du bouton **Fermer**.
- **commentAdded** : confirmation de l’ajout d’un commentaire à une tâche.
- **commentsClicked** : confirmation du démarrage réussi de l’affichage des commentaires.
- **commentUpdated** : confirmation de la mise à jour réussie d’un commentaire sur une tâche.
- **companionBannerJoin** : appui sur **Rejoindre** sur la bannière de niveau supérieur.
- **companionDismiss** : la bannière du compagnon est masquée.
- **companionDismissProximity** : la bannière du compagnon est masquée.
- **companionJoin** : appui sur l’option Rejoindre en tant que compagnon sur la feuille.
- **companionJoinProximity** : l’utilisateur a rejoint par le biais de la bannière de compagnon.
- **completeVaultFRE** : l’utilisateur termine le processus de génération d’une clé principale utilisée pour chiffrer ses données fiables.
- **completionStateChange** : appui sur un filtre bascule d’état Achevé ou Inachevé dans l’affichage de filtres de la liste des tâches.
- **composeExpandComposer** - appui sur **Mise en forme**.
- **composeFilePick** : le sélecteur de fichier natif est démarré.
- **composeImagePicker** - appui sur **Image**.
- **composeLocation** - appui sur **Position** dans la zone de rédaction.
- **composeMention** : @mention.
- **composeOpenEmoticonPicker** : appui sur le sélecteur d’émoticônes.
- **composeOpenFunPicker** : appui sur le sélecteur Fun.
- **composeParticipantAdded** : un participant est ajouté à l’application Shifts.
- **composeSearchResult** : sélection de résultats d’extension de message ; utile pour comprendre la pertinence des résultats de la recherche d’application. Permet également d’améliorer le message Envoyer des données de télémétrie avec les données de l’application.
- **composeSelectExtension** : appui sur une application ME.
- **composeSendSmartreply** : un clic sur un élément de réponse intelligente.
- **composeSendMessage** : améliore le message Envoyer des données de télémétrie avec les données de l’application.
- **confirmAudioOn** : l’utilisateur confirme que le son doit être activé.
- **confirmFileShare** - appui sur **Partager** dans la boîte de dialogue de confirmation.
- **consultTransfer** se déclenche lorsque :
  - **Transférer** > **Consulter d’abord** est sélectionné ;
  - Cible du transfert est défini sur une personne ;
  - Cible du transfert est défini sur un numéro de téléphone.
- **consultTransferCall** se déclenche lorsque :
  - un appel de consultation a commencé ;
  - Confirmer est sélectionné dans une boîte de dialogue de confirmation de trasnfert ;
  - Annuler est sélectionné dans une boîte de dialogue de confirmation de transfert ;
  - un appui est effectué sur le bouton **Transfert de bannière** ;
  - un appui est effectué sur le bouton **Reprise de bannière**.
- **consultTransferChat** se déclenche lorsque :
  - une conversation de consultation a commencé ;
  - Confirmer est sélectionné dans une boîte de dialogue de confirmation de trasnfert ;
  - Annuler est sélectionné dans une boîte de dialogue de confirmation de transfert.
  - un appui est effectué sur les boutons **Transfert de bannière** ou **Reprise de bannière**.
- **consumeVoiceMessage** : un message vocal est lu.
- **ContactCard_SeeMoreOOF** : Afficher plus d’un long message d’absence du bureau (OOF).
- **contactOrganizer** : appui sur **Contacter l’organisateur**.
- **conversation, tabs** : appui sur un onglet.
- **copyLink** : un lien est copié vers une publication de canal.
- **contactActivity** : appui sur le bouton permettant d’afficher l’activité d’un utilisateur à partir de sa carte de visite.
- **conversation** : l’utilisateur accède aux onglets **Conversation** ou **Publications**.
- **cortanaFerment** : lorsqu’un utilisateur fait disparaître manuellement la zone de dessin Cortana.
- **cortanaEduCategorySelect** : lorsqu’un utilisateur clique sur un élément de catégorie Conseils pour l’éducation.
- **cortanaEduOpen** : la page Éducation s’affiche dans la zone de dessin Cortana.
- **cortanaInvoke** : lorsque Cortana démarre l’écouter.
- **cortanaKWSWSwortanaToggle** : lorsqu'un utilisateur appuie sur le commutateur KWS dans la page des paramètres de Cortana.
- **cortanaMicPermissionDialogButtonClick** : lorsqu’un utilisateur accorde ou refuse l’autorisation de micro dans la zone de dessin Cortana.
- **cortanaOpen** : lorsqu’un utilisateur ouvre la zone de dessin de Cortana.
- **cortanaOptionsOpen** : lorsque l’utilisateur appuye sur le bouton Options dans la zone de dessin Cortana.
- **cortanaSafetyFirstActions** : lorsque l’utilisateur accepte la déclaration de sécurité en premier.
- **cortanaSafetyFirstLaunch** : lorsque l'utilisateur ouvre Cortana pour la première fois une fois l'EPE terminé.
- **cortanaSettingsOpen** : lorsqu’un utilisateur ouvre la page des paramètres de Cortana via un clic sur le bouton Paramètres de Cortana dans la zone de dessin Cortana.
- **CortanaStopResponding** : lorsqu’un utilisateur clique sur le bouton Annuler dans la zone de dessin Cortana.
- **cortanaUserSettingsLaunch** : lorsque l’utilisateur ouvre les paramètres de Cortana dans les paramètres Teams.
- **cortanaVoiceSelect** : lorsqu’un utilisateur sélectionne la police vocale Cortana dans la page des paramètres de Cortana.
- **createChannel** : fournit des données de performance sur l’action réussie de création ou de suppression pour la création d’un canal, lorsque :
  - un appui est effectué sur le bouton **Terminé** sur la page **Créer un canal** ;
  - un appui est effectué sur le bouton **Annuler** sur la page **Créer un canal**.
- **createComposeExtension** : utilisation d’extension de message de création ou d’action ME.
- **createConversationClicked** : une conversation est créée avec d’autres employés.
- **createDefaultPlannerPlan** : une liste partagée est créée automatiquement quand l’application Tâches est ouverte pour la première fois par un membre de ce groupe ; vérifie que la liste automatique est créée avec le service Planificateur. Confirme que la liste de tâches partagée par défaut est correctement créée dans le Planificateur la première fois que l’utilisateur essaye de créer une liste de tâches partagée.
- **createOrJoinTeam** : appui sur **+** pour créer ou rejoindre une équipe.
- **createPersonalPlan** : une liste personnelle est créée ; vérifie la liste créée avec le service ToDo. Confirme qu’une nouvelle liste de tâche personnelle est créée dans ToDo.
- **createPersonalSubtask** : confirme la création réussie d’une sous-tâche personnelle.
- **createPersonalTask** : confirme la création réussie d’une tâche personnelle.
- **createPlan** : confirme la création réussie d’une liste de tâches partagée. Confirme la création réussie d’un plan partagé par le niveau intermédiaire.
- **createPlannerPlan** : une liste partagée est créée ; vérifie que la liste est créée avec le service Planificateur. Confirme que la nouvelle liste de tâches partagée est créée dans le Planificateur.
- **createPlannerTask** : vérifie un appel auprès du service Planificateur. Confirme la création réussie d’une tâche dans une liste de tâches partagée.
- **createShiftClicked** : le manager appuie sur **Créer un shift**.
- **createShiftOrTimeOffClicked** : appui sur **Créer un shift** ou **Congé**.
- **createTask** : utilisé lors de l’échec de Créer une action ; vérifie un appel auprès du service Planificateur. Confirme l’échec de l’opération de création d’une tâche.
- **createTaskList** : l’utilisateur accède à l’affichage Créer un plan depuis la vue d’accueil.
- **createTeam** : fournit des données de performance sur l’action réussie de création ou de suppression pour la création d’une équipe lorsque :
  - un appui est effectué sur le bouton **Terminé** sur la page **Créer une équipe** ;
  - un appui est effectué sur le bouton **Annuler** est sélectionné sur la page **Créer une équipe**.
- **createTeam, createChannel** : fournit des données de performance concernant l’ajout réussi de membres dans une équipe et la création réussie d’une nouvelle équipe lorsque :
  - un appui est effectué sur le bouton **Ignorer** sur la page **Ajouter des membres** (vérifie préalablement les membres existants) ;
  - un appui est effectué sur le bouton **Terminé** est sélectionné sur la page **Ajouter des membres** (vérifie préalablement les membres existants).
  - Affiche la confirmation de création d’un canal ou d’une équipe.
- **crossCloudDialogCancel** - appui sur **Annuler** dans une boîte de dialogue cross-cloud.
- **crossCloudDialogJoin** - appui sur **Rejoindre en tant qu’invité** dans une boîte de dialogue cross-cloud.
- **dashboardNav** : l’utilisateur accède à une vignette sur le tableau de bord de la conversation.
- **dataChanged** : l’utilisateur modifie une date de shift.
- **datePickerLaunch** : confirmation du démarrage réussi du sélecteur de dates.
- **dayClicked** : l’affichage par journée est sélectionné alors que l’utilisateur visualise ses shifts.
- **daySaved** : l’utilisateur enregistre sa disponibilité pour un jour ou enregistre un jour de shifts.
- **declineTimeOffRequest** : l’utilisateur refuse la demande de congé. Ceci est une fonctionnalité essentielle permettant au manager de refuser une demande de congé.
- **deleteClicked** : appui sur **Supprimer** dans les détails de tâche ; affiche la boîte de dialogue de confirmation.
- **deleteContact** : l’utilisateur supprime un contact privé existant.
- **deleteMeeting** : appui sur **Supprimer** depuis la page Détails de la réunion.
- **deletePersonalTask** : confirme la suppression réussie d’une tâche personnelle.
- **deletePersonalSubtask** : confirme la suppression réussie d’une sous-tâche personnelle.
- **deletePersonalVaultItem** : l’utilisateur demande à supprimer son coffre-fort personnel.
- **deletePlannerTask** : confirme l’opération réussie de suppression d’une tâche partagée.
- **deleteShift** : un shift est supprimé.
- **duration_picker_dismissed** : le sélecteur de durée est masqué.
- **deleteTask** : vérifie auprès du service Planificateur si l’action de suppression a réussi ou échoué. Confirme l’échec de la suppression d’une tâche.
- **deleteVoicemail** : appui sur Supprimer l’élément de messagerie vocale.
- **demotedToAttendee** : l’utilisateur rétrograde un présentateur ; bouton **Modifier** dans la boîte de dialogue.
- **denyParticipant** : nombre de fois que l’utilisateur refuse à une personne l’entrée depuis la liste de présence.
- **descriptionChanged** : confirme la modification réussie de la description de la tâche partagée.
- **descriptionClicked** : appui sur **Afficher la description** dans les détails de tâche.
- **detailsTabClicked** : appui sur l’onglet **Détails** sur la réunion.
- **deviceAddressBookSync** : activation de la synchronisation du carnet d'adresses depuis la page de paramètres.
- **deviceAddressBookUnsync** : désactivation de la synchronisation du carnet d'adresses depuis la page de paramètres.
- **deviceSyncEnabled** - Synchronisation des appareils activée.
- **deviceSyncDisabled - Synchronisation de l’appareil** désactivée.
- **dialIn** : l’utilisateur choisit Composer pour participer à une réunion (divers emplacements).
- **dialInBadNetworkBanner** - appui sur **Composer** sur la bannière de connexion médiocre.
- **dialInBadNetworkBannerCancel**: l’action **Composer** est annulée dans la boîte de dialogue native.
- **dialInBadNetworkBannerConfirm** : l’action **Composer** est confirmée dans la boîte de dialogue native.
- **dialInCall** - appui sur **Appeler** sur la fenêtre contextuelle **Composer**.
- **dialInCancel** - appui sur **Annuler** sur la fenêtre contextuelle **Composer**.
- **dialOutCall** se déclenche lorsque :
  - l’utilisateur rejoint en mode Conduite ;
  - un appui est effectué sur **Appeler** sur la fenêtre contextuelle **Me rappeler**.
- **dialOutCallAAD** : un numéro est sélectionné depuis **Mes numéros** dans la feuille d’action.
- **dialOutCallRecent** : un numéro est sélectionné depuis les derniers numéros dans la feuille d’action.
- **dialOutCancel** - appui sur **Annuler** sur la fenêtre contextuelle **Me rappeler**.
- **dialOutDialog** - **Nouveau numéro** est sélectionné sur la feuille d’action.
- **dialOutFailRetry** - appui sur **Réessayer** depuis une bannière d’échec.
- **dialPad** : appui sur **Pavé numérique** depuis la liste d’appels.
- **directShare** : a partagé un lien d’invitation vers une application native Sms/Email.
- **disableCategory** : Désactiver un type de notification ou Désactiver les notifications d’appels entrants.
- **disabled** - appui sur **Ignorer les notifications** dans l’expérience de première exécution (FRE). Fournit des données de performance essentielles pour les cas où l’utilisateur ignore les notifications dans le flux FRE.
- **disableQuietDays** : Jours de déconnexion est désactivé. Données de télémétrie de performance de fonctionnalité pour les jours de déconnexion.
- **disableQuietHours** : Heures de déconnexion est désactivé.
- **discoverTeams** : l’utilisateur accède à la page Parcourir et Rejoindre Teams.
- **dismiss_earlycancelledCQF** : le formulaire CQF Appel annulé précocement est masqué.
- **dismiss_ratemycallCQF** : le formulaire CQF Évaluer mon appel est masqué.
- **dismiss_ratemyliveeventCQF** : le formulaire CQF Évaluer mon événement en direct est masqué.
- **dismissBadNetworkBanner** - appui sur **Masquer** sur une bannière de connexion médiocre.
- **dismissFlyout** - appui sur **Masquer**.
- **dismissModality** : le sélecteur de modalité est fermé sans partage.
- **dismissModalityPicker** : appui sur **Sélecteur de modalité**.
- **dismissReadReceiptsNotice** - appui sur **Ok** dans un avis de fonctionnalité.
- **dismissStartRecording** : Ignorer l’erreur lors du démarrage de l’enregistrement.
- **dismissStopRecording** : Ignorer l’erreur lors de l’arrêt de l’enregistrement.
- **dismissUseWifiForVideoBanner** : l’utilisateur masque une bannière l’informant que :
  - la vidéo des participants distants est bloquée et les utilisateurs doivent activer le WiFi pour l’afficher ;
  - les utilisateurs doivent activer le WiFi pour partager la vidéo.
- **DLPDelete** : l’utilisateur a supprimé un message bloqué.
- **DLPEdit** : l’utilisateur a modifié un message bloqué.
- **DLPOverride** : l’utilisateur a remplacé un message bloqué.
- **DLPOverrideReport** : l’utilisateur a signalé un faux positif et a remplacé le message.
- **DLPReport** : l’utilisateur a signalé un faux positif.
- **DLPResolve** : l’utilisateur a tenté de résoudre un message de protection contre la perte de données (DLP).
- **DLPSeeOriginal** : l’utilisateur a appuyé pour afficher un message d’origine.
- **downloadFile** permet de déterminer si :
  - une opération de téléchargement a été démarrée ;
  - le téléchargement d’un fichier a réussi.
- **dragDatePickerHandle**
- **dtmfPSTNCall** : appui sur le bouton de numérotation en fréquences vocales (DTMF) sur le pavé numérique.
- **dueDateChanged** : l’utilisateur attribue une date d’échéance à une tâche.
- **dueDatePickerClicked** : appui sur **Date d'échéance** dans les détails de tâche, ce qui ouvre la page de sélecteur de date d’échéance.
- **dueDateSelected** : l’utilisateur applique un filtre de dates d’échéance lors de l’affichage d’une liste de tâches.
- **dueDateUnselected** : l’utilisateur retire un filtre de dates d’échéance lors de l’affichage d’une liste de tâches.
- **edit** - appui sur **Modifier** dans un message de conversation.
- **editChannel** : l’utilisateur appuie sur un bouton pour modifier un canal dont il est le propriétaire ou l’administrateur.
- **editContact** : l’utilisateur modifie un contact privé existant, ce qui peut être effectué en accédant à sa carte de visite.
- **editMeetingResponse** : Modifier la réponse à une demande de réunion depuis la page Détails de la réunion.
- **editNavigation** - appui sur **Réorganiser** dans le menu **Plus** pour modifier l’ordre des applications de la barre inférieure.
- **editRsvpMeetingOptions** : appui sur **RSVP** pour modifier la sélection précédente.
- **editShiftClicked** : Modifier un shit.
- **editSmartReply** : un élément de réponse intelligente est modifié.
- **editTeam** : l’utilisateur appuie sur un bouton pour modifier une équipe dont il est le propriétaire ou l’administrateur.
- **editTeam, editChannel** : des membres sont correctement ajoutés dans une équipe et une équipe existante est correctement créée lorsque :
  - un appui est effectué sur **Annuler** sur la page **Ajouter des membres** (équipe ou canal existant).
  - un appui est effectué sur **Terminé** est sélectionné sur la page **Ajouter des membres** (équipe ou canal existant).
- **emergencyCall** : un appel d'urgence est effectué – forfait d'appels.
- **emergencyCallDirectRouting** : un appel d'urgence est effectué – routage direct.
- **emergencyCallLocationPolicyBased** : composition de numéro d’urgence en utilisant le pavé numérique.
- **emergencycallSecurityDeskNotify** : un appel d'urgence est effectué – centre de sécurité informé.
- **enableCategory** : concerne les paramètres de notification, lorsque l’utilisateur active :
  - un type de notification ;
  - les notifications d’appels entrants.
- **enabled** : concerne l’activation de la notification dans le flux d’expérience de première exécution (FRE) lorsque :
  - un appui est effectué sur **Activer les notifications** dans l’expérience de première exécution (FRE) ;
  - un appui est effectué sur Activer dans un rappel.
- **enabed/disabled** : autorisations d’appels ou de contacts (Android uniquement).
- **enabled, notNow** : bouton **Accepter** dans l’invite d’autorisation de notification ; autorisation de notifications de l’expérience de première exécution (FRE) (iOS). Ceci permet de compter le nombre de personnes ayant activé la fonctionnalité de notification et fournit des informations.
- **enablediOSPrompt** : l’utilisateur active les notifications dans l’invite d’autorisation de notifications iOS. Ceci fournit des informations sur les utilisateurs qui activent réellement les notifications dans iOS depuis l’invite d’autorisation de notifications.
- **enabledQuietDays** : Jours de déconnexion est activé.
- **enableLocationPermission** : l’utilisateur active les autorisations de position pour la fonctionnalité de partage de position.
- **enableQuietDays** : l’utilisateur active Jours de déconnexion.
- **enableQuietHours** : Heures de déconnexion est activé.
- **endEditing** - appui sur **Enregistrer**.
- **endFileShare** - appui sur **Retour** dans une boîte de dialogue de partage de fichiers.
- **endMyShift** : nombre d’appareils en mode partagé, ou nombre de déconnexions.
- **endPhotoShare** - appui sur **x** pour sortir du partage de photos.
- **entryPointClicked** : sélection des **Demandes** dans l’onglet **Planification**. Les demandes concernent les heures de shift des travailleurs de première ligne, etc.
- **endPSTNCallSelected** : l’utilisateur termine un appel RTCP ou de contenu.
- **endPSTNCallShown** : l’utilisateur est invité à terminer un appel RTCP ou de contenu.
- **endVideoShare** - appui sur **x** pour sortir du partage de vidéo.
- **errorShown** : une erreur est affichée.
- **expand/collapse** : section de contacts de l’appareil ou de l’entreprise.
- **expandCollapseSection** : appui sur l’en-tête de section pour la développer ou le réduire.
- **Attendu : atMention – Android : chatSendMessage – iOS : sendMsg** : @mention d’un robot dans une zone de rédaction.
- **Attendu : botClickCardAction – Android : showCard – iOS : inexistant** : appui sur les boutons d’une carte. Les cartes sont des constructions de plateforme clés et la mesure de leur utilisation et de leur motif est nécessaire à la compréhension de l’utilisation de la plateforme et à la surveillance de l’apparition de problèmes potentiels du côté client.
- **Attendu : chatSendMessage – iOS : composeSendMessage** : appui sur **Répondre** pour répondre à une conversation de robot dans un canal.
- **Attendu : composeSendMessage – Android : replyChannel – iOS : inexistant** : appui sur **Répondre** pour répondre à une conversation de robot dans un canal.
- **Attendu : messageLike – Android : reactLike_CM** : mention J’aime sur un message de robot.
- **Attendu : messageUnread – Android : markAsLastUnread** : options de menu contextuel de message pour un message de robot.
- **federatedUpgradeNewChat** : une conversation héritée est mise à niveau vers une conversation native.
- **files** : indique si le listage des fichiers s’est correctement effectué dans la conversation et dans l’onglet Fichiers du canal.
- **fileSelected** : une présentation PowerPoint est sélectionnée.
- **fileThumbnailPreviewDownloaded** : aide à vérifier qu’une miniature d’un fichier a correctement été rendue.
- **fileThumbnailPreviewFromCache** : indique si une miniature s’affiche correctement depuis le cache et aide à vérifier qu’une miniature d’un fichier a correctement été rendue.
- **fileThumbnailPreviewNotAvailable** : aide à vérifier qu’une miniature d’un fichier a correctement été rendue.
- **fillFrameVideo** : appui sur Remplir l’image depuis la feuille d’action.
- **firstTimeSignedIn** : événement de connexion ou de d’inscription déclenché lorsque :
  - une connexion a réussi ;
  - une première connexion a réussi ;
  - des erreurs de connexion sont affichées à l’utilisateur.
  - Enregistre des données de télémétrie sur les stratégies GAM/GPM implémentées lors de la première connexion.
  - Enregistre les paramètres de référence de l’installation de l’application après une première connexion réussie.
- **fitToFrameVideo** : appui sur Ajuster à l’image depuis la feuille d’action.
- **flipCamera** : Faire pivoter la caméra.
- **forcedUpdateAccept** : l’utilisateur accepte de mettre à jour la version de l’application dans la boîte de dialogue de forçage de mise à jour.
- **forcedUpdateExit** : l’utilisateur ferme l’application plutôt que de mettre à jour la version de l’application dans la boîte de dialogue de forçage de mise à jour.
- **forcedUpdatePrompt** : utilisé dans les situations dans lesquelles des utilisateurs de versions antérieures ne possédant pas les derniers correctifs de sécurité et de confidentialité doivent être contactés.
- **formattingBold** : l’utilisateur sélectionne la mise en forme Gras.
- **formattingHighlight** : l’utilisateur sélectionne la mise en forme Surligner.
- **formattingImportant** : l’utilisateur sélectionne la mise en forme Important.
- **formattingItalics** : l’utilisateur sélectionne la mise en forme Italique.
- **formattingTextColor** : l’utilisateur sélectionne la mise en forme Couleur de texte.
- **formattingUnderline** : l’utilisateur sélectionne la mise en forme Souligner.
- **FRE – aucun AS affecté** : enregistre des données de télémétrie sur les stratégies GAM/GPM lors du démarrage de l’application. Données de télémétrie pour l’intégration Intune pour GAM et GPM. Fournit des données de performance sur l’échec lors de l’expérience de première exécution (FRE).
- **freActionClickedGet** - appui sur **Prise en main**, **Essayer plus tard** ou **Fermer** (GPS) dans l’expérience de première exécution (FRE).
- **freDone** : l’expérience de première exécution (FRE) a été effectuée.
- **freTriggered** : l’utilisateur affiche la pointeuse sur l’expérience de première exécution (FRE).
- **funSearchQueryEntered** : une requête Giphy a été entrée. Données de performance pour la fonctionnalité de pièce jointe Giphy sur Teams.
- **funSelectItem** : une image Giphy a été choisie. Données de performance pour la fonctionnalité de pièce jointe Giphy sur Teams.
- **galleryImage** : une image a été chargée – galerie.
- **get_directions_clicked** : appui sur **Obtenir un itinéraire**.
- **giphyUserDisabled** : l’utilisateur choisit de refuser les conditions générales Giphy.
- **giphyUserEnabled** : l’utilisateur choisit d’accepter les conditions générales Giphy.
- **goToNotificationSettings** : l’utilisateur accède à la page de paramètres de notification depuis la boîte de dialogue **Nous avons mis à jour les paramètres de notification**.
- **GPSPromptClicked** : appui sur **Autoriser** ou **Refuser** dans une invite du système d’exploitation. Autorise le GPS ou non.
- **group_map_closed** : l’utilisateur ouvre l’affichage de carte géographique depuis une conversation.
- **group_map_open** : l’utilisateur ferme l’affichage de carte géographique.
- **groupCallJoin** : l’utilisateur rejoint un appel de groupe.
- **groupClicked** : l’utilisateur sélectionne le groupe de shifts.
- **guideMe** : l’utilisateur appuie sur une bannière l’informant qu’une application tierce bloque les notifications et lui proposant des conseils de dépannage.
- **hamburgerMenu** : l’utilisateur accède au menu hamburger. Le menu hamburger contient des actions importantes, telles que le changement de compte, les paramètres de notification, de données et de profil.
- **handoffComplete** : la réunion ou l’appel a été transféré sur cet appareil.
- **handoffJoin** : une option de transfert de réunion est sélectionnée dans la feuille d’action.
- **hardwareAudioOff** : le son est désactivé via les boutons matériels.
- **hardwareAudioOn** : le son est activé via les boutons matériels.
- **hide** : Masquer la conversation.
- **hideChannel** : Masquer un canal depuis la liste des équipes et canaux.
- **image** : image.
- **inAppNotification**: déclenché lorsqu’une notification est activée lorsque l’utilisateur est actif dans l’application.
- **immediateCallForward** : la cible de transfert d’appel immédiat est définie, ou le transfert d’appel immédiat est activé (Sonnerie d’appel est désactivé).
- **importanceToggleClicked** : le champ **!** est basculé dans les détails de l’élément de tâche.
- **importantMessage_select** : un message important est sélectionné depuis le menu contextuel de priorité par un utilisateur.
- **importantMessageSend** : l’utilisateur envoie un message important.
- **inCallDialOut** : appui sur **Me rappeler** depuis les options Plus lors d’un appel en cours.
- **initiatePhotoShare** : Commencer un partage de photo.
- **initiateVideoShare** : Commencer un partage de vidéo.
- **install** : Installer ou événement d’installation.
- **installReferrer** : enregistrement des paramètres de référence d’installation de l’application après la première installation.
- **invisionWhiteboardClicked** : appui sur le tableau blanc Invision depuis :
  - l’onglet **Fichiers du canal** ;
  - l’onglet **Fichier de la conversation** de la réunion.
- **inviteFreemium** : appui sur le bouton **+** sur l’écran d’invitation.
- **inviteGuest** : appui sur le bouton **+** sur l’écran d’invitation.
- **joinFromDeeplinkInTeams** : l’utilisateur a rejoint via un lien profond provenant de l’application Teams.
- **joinFromDeeplinkOutsideTeams** : l’utilisateur a rejoint via un lien profond ne provenant pas de l’application Teams.
- **joinFromJoinLauncher** : l’utilisateur a rejoint à partir d’un lanceur de participation.
- **joinFromNudge** : l’utilisateur a rejoint depuis Nudge.
- **joinFromStore** : l’utilisateur a rejoint après le téléchargement de l’application depuis le magasin d’applications.
- **joinMeeting** : indique la réussite ou l’échec de la participation à des réunions depuis le calendrier lorsque l’utilisateur :
  - a rejoint la réunion par le bouton Composer ;
  - a rejoint la réunion par le bouton Me rappeler ;
  - a rejoint le contenu de la réunion seulement ;
  - a appuyé sur le bouton **Participation à une réunion** depuis la vue de l’agenda.
- **joinOptionsEdu** : l’utilisateur EDU sélectionne des options pour rejoindre une réunion planifiée et les options appropriées lui sont affichées.
- **joinTeam** : appui sur **Rejoindre**.
- **joinViaCode** : l’utilisateur rejoint une réunion via un code.
- **labelPickerClicked** : le sélecteur d’étiquettes a été démarré.
- **labelSelected** : une étiquette a été sélectionnée.
- **labelUnselected** : une étiquette a été désélectionnée.
- **launchLinksGallery** : l’utilisateur accède à la galerie depuis le tableau de bord.
- **launchSlideshow** : l’utilisateur lance la visionneuse d’images en plein écran du diaporama à partir de l’un des trois emplacements de fonctionnalités d’application possibles. 
- **Source de l’exécution, par exemple : directement, par un lien, par appShortcut** : s’exécute directement ou par un lien (enregistre la télémétrie de gestion des applications mobiles (GAM) ou de Gestion des périphériques mobiles (GPM) lors du démarrage de l’application pour collecter des données sur les utilisateurs actifs).
- **lastSearchableAliasTurnedOff** : l’utilisateur a désactivé tous les alias pouvant faire l’objet d’une recherche pour le compte.
- **leaveChat** : l’utilisateur quitte la conversation.
- **legacyChatLink** : un lien vers une conversation héritée est sélectionné.
- **link** : l’utilisateur a lancé l’échange du lien d’invitation en entrant dans l’application Teams.
- **likeAppDismiss** : l’invite demandant à l’utilisateur s’il aime l’application ou non est masquée sans réponse donnée.
- **likeAppNo** : l’invite demandant à l’utilisateur s’il aime l’application ou non reçoit la réponse Non.
- **likeAppYes** : l’invite demandant à l’utilisateur s’il aime l’application ou non reçoit la réponse Oui.
- **likeMsg** : appui sur **J’aime**.
- **linkPreviewCancel** : aide à la compréhension du comportement préalable à la fermeture de la prévisualisation.
- **listUserClicked** : l’utilisateur sélectionne un utilisateur dans Au travail.
- **liveCaptions** : les sous-titres en direct sont activés ou désactivés.
- **liveEventAdditonalLink** : un lien supplémentaire est sélectionné.
- **liveEventInfo** : appui sur **Infos**.
- **liveEventJoin** : l’utilisateur rejoint un événement en direct.
- **liveEventLeave** : appui sur **Quitter**.
- **liveEventPresenterJoin** : un événement en direct est rejoint par un présentateur.
- **liveEventPresenterJoinAsAttendee** : un présentateur d’événement en direct rejoint en tant que participant.
- **liveEventQnA** : appui sur l’icône **Q&A**.
- **liveEventYammer** : appui sur l’icône **Yammer**.
- **liveMeetingPushNotificationClicked** : appui sur la notification Push.
- **liveMeetingToastClicked** : appui sur le toast dans l’application.
- **live_location_in_chats_from_profile_clicked** - appui sur **Position en direct** dans l’affichage du profil.
- **lobbyPickAudio** : nombre de fois que l’utilisateur a changé de sortie audio dans la salle d'attente.
- **lobbyToggleMuted** : nombre de fois que l’utilisateur a allumé ou éteint son micro dans la salle d’attente.
- **lobbyToggleVideo** : nombre de fois que l’utilisateur a allumé ou éteint sa caméra dans la salle d’attente.
- **logOutClicked** : l’utilisateur se déconnecte.
- **location_active_tracking** : l’appareil de l’utilisateur est basculé en mode suivi actif.
- **locationCard** : une carte d’emplacement est sélectionnée.
- **location_family_sync** : les membres d’un groupe familial créés dans l’application familiale MSA sont affichés. Confirme que tous les membres de la famille pouvant bénéficier d’un consentement sont affichés.
- **location_data_use_privacy_denied** : l’utilisateur a refusé l’acceptation des conditions de confidentialité.
- **location_group_map_sync** : l’affichage de la carte géographique est ouvert.
- **location_map_load** : l’affichage de la carte géographique est chargée.
- **location_map_markers_load** : l’affichage de la carte est chargée. Confirme que les marqueurs de position de tous les utilisateurs en partage actif sont correctement déployés sur l’affichage de la carte géographique.
- **location_message_send** : l’utilisateur initie une session de partage de position.
- **location_data_use_privacy_denied** : l’utilisateur appuie sur **Plus tard** ou masque une fenêtre contextuelle expliquant l’utilisation des données d’emplacement par TFL.
- **location_data_use_privacy_granted** : l’utilisateur appuie sur **Autoriser** sur une fenêtre contextuelle expliquant l’utilisation des données d’emplacement par TFL.
- **location_settings_open** : l’utilisateur ouvre les paramètres de localisation.
- **location_sharing_start** : l’utilisateur partage sa position en direct dans une conversation.
- **location_sharing_stop** : l’utilisateur arrête le partage de sa position dans une conversation.
- **loginFailed** : l’utilisateur n’a pas pu se connecter.
- **loginSuccess** : l’utilisateur a pu se connecter.
- **logoutVault** : l’utilisateur se déconnecte de l’application et se déconnecte à son tour du coffre-fort. 
- **manageBlockedNumbers** : l’utilisateur accède aux numéros bloqués par les paramètres.
- **manageVaultKey** : l’utilisateur modifie son choix de gestion des clés sécurisées (MSA ou auto-suivi).
- **ManuelSendMessage** : un message est envoyé manuellement.
- **mapAppPicker** : l’utilisateur sélectionne l’application de cartes géographiques qui doit être utilisée à l’appui d’une carte d’emplacement.
- **markAsRead** : Marquer comme Lu.
- **markAsUnread** : Marquer comme Non lu.
- **markChannelRead** : l’utilisateur marque le canal comme Lu.
- **messageBookmarkMessage** : carte de connecteur enregistrée. Utilise les données de télémétrie existantes avec les données spécifiques de l’application. Ou message de robot enregistré.
- **markAsLastUnread** : menu contextuel d’une carte de connecteur.
- **maskCallerId** : l’utilisateur active ou désactive le paramètre d’appel pour masquer l’ID d’appelant.
- **meetingAttachmentFileClick** : un clic sur un élément joint à la réunion.
- **meetingAttachmentFileOptions** : un clic sur les options d'un élément de pièce jointe de réunion.
- **meetingAttachmentSeeMoreClick** : un clic sur le bouton « Afficher plus » de la pièce jointe d'une réunion.
- **meetingDetailCalendarList** : appui sur la page Détails de la réunion depuis la liste de calendriers, ou sur l’onglet **Détails** sur la page Détails de la réunion.
- **meetingDetailChatWithParticipants** : Discuter avec les participants depuis la page Détails de la réunion.
- **meetingDetailDeleteMeetingforSelf** : Supprimer une réunion depuis la page Détails de la réunion.
- **meetingDetailJoin** : appui sur **Participation à une réunion** depuis la page Détails de la réunion.
- **meetingDetailParticipants** : Afficher tous les participants depuis la page Détails de la réunion.
- **meetingDetailScheduledMeeting** - Page détails de la réunion sélectionnée à partir de l’objet de réunion planifié (**...**), ou sélectionnez l’onglet **Détails** d’une réunion planifiée.
- **meetingDetailSearchParticipants** : appui sur **Rechercher** dans Participants à la réunion sur le planning de réunion.
- **meetingInsightFileClick** : un clic sur un élément de fichier lié à la réunion.
- **MeetingInsightFileLocatorClick** : un clic sur le bouton de conseil du localisateur de contenu lié à la réunion.
- **meetingInsightFileOptions** : un clic sur les options d’un élément de fichier lié à la réunion.
- **meetingInsightSeeMoreClick** : un clic sur le bouton « Afficher plus » d'un contenu lié à une réunion.
- **meetingJoinLeave** : appui sur Quitter -> appui sur **x** après un appui sur le bouton **Rejoindre**.
- **meetingJoinNow** - appui sur **Rejoindre maintenant pour VoIP**.
- **meetingJoinNowWithCallMe** : l’utilisateur rejoint une réunion avec **M’appeler**.
- **meetingJoinNowWithPSTN** : l’utilisateur rejoint la réunion avec Composer.
- **meetingLeaveChat** : Quitter la conversation.
- **meetingMuteChat** : Désactiver la conversation.
- **meetingNotesCreatedInChatLink** : le chicklet **Notes de réunion créées** est sélectionnée dans une conversation de réunion privée ou dans une conversation de réunion de canal.
- **meetingNotesMentionCharLink** : le lien de @mention est sélectionné dans une conversation de réunion privée.
- **meetingNotesMentionChatLink** : le lien de @mention est sélectionné dans une conversation de réunion de canal.
- **meetingNotesTabEntryPoint** : appui sur l’onglet **Notes de réunion** dans une réunion privée ou de canal.
- **meetingNotificationSettingsAccepted** : l’option Paramètres de notification est changé pour Autorisées seulement.
- **meetingNotificationSettingsAll** : l’option Paramètres de notification est changé pour Toutes.
- **meetingNotificationSettingsNone** : l’option Paramètres de notification est changé pour Aucune.
- **messagePriority_select** : un point d’entrée Message prioritaire est sélectionné.
- **messageSeeOriginal** : l’utilisateur retourne un message traduit à son original.
- **meetingSeeParticipantsChatDetails** : Afficher tous les participants.
- **memberListLoadMore** : Faire défiler vers le bas pour charger plus.
- **messageEditMessage** : l’utilisateur modifie un message.
- **messageShareMessage** : Partager un message.
- **messageTranslate** : l’utilisateur traduit un message.
- **messageUnabletoEdit** : l’utilisateur ne parvient pas à modifier un message.
- **meetingUserAnonB2B** : un anonyme B2B rejoint la réunion.
- **meetingUserAnonB2C** : un anonyme B2C rejoint la réunion.
- **meetingUserDialIn** : un utilisateur RTCP (Composer) rejoint la réunion.
- **meetingUserDialOut** : un utilisateur a rejoint la réunion par le bouton RTCP Me rappeler.
- **meetingUserFederated** : un utilisateur fédéré a rejoint la réunion.
- **meetingUserFreemium** : un utilisateur freemium a rejoint la réunion.
- **meetingUserGuest** : un utilisateur invité a rejoint la réunion.
- **meetingUserTenant** : un utilisateur dans le client a rejoint la réunion.
- **memeGenerated** : lorsqu’un mème est généré en fonction d’une entrée utilisateur de données d’image et de texte. 
- **meProfileFetch** : indique une extraction et une création de profil réussies.
- **messageCopyMessage** : Copier le message.
- **messageDelete** : Supprimer le message.
- **messageEditMessage** : Modifier le message.
- **messageForwardMessage** : l’utilisateur sélectionne un point d’entrée Transférer depuis le menu contextuel du message.
- **messageLike/messageUnlike** : J’aime / Je n’aime plus le message.
- **messageMuteSender** : Activer / Désactiver l’expéditeur.
- **messageLike** : mention J’aime sur une carte de connecteur. Utilise les données de télémétrie existantes avec les données spécifiques de l’application.
- **messageScheduledMeeting** : le sujet de la réunion dans le canal est sélectionné (pas seulement des réunions planifiées).
- **messageTriggered** : une notification est déclenchée pour un message.
- **micPermissionCancel** - appui sur **Annuler** sur la boîte de dialogue d’autorisation d’accès au micro.
- **micPermissionGoToSettings** : l’utilisateur accède aux paramètres depuis la boîte de dialogue d’autorisation d'accès au micro.
- **MicrosoftWhiteboardClicked** : appui sur le tableau blanc Microsoft dans les onglets **Fichiers du canal** ou **Fichiers de la conversation de réunion**.
- **moreOptionsClicked** : appui sur le menu **…** en haut à droite sur l’écran d’édition de l’élément de tâche.
- **moveTaskClicked** : une option dans la liste Plus d’options de l’élément de tâche.
- **msaAddDeleteAliasLinkClicked** : lien vers la configuration d’un alias sur la page profil MSA.
- **multiCallEndFromUFD** : nombre de fois que l’utilisateur termine l’appel en attente dans un scénario d’appel multiple.
- **multiCallResumeFromUFD** : nombre de fois que l’utilisateur appuie pour reprendre un appel en attente.
- **multiCallSwitch** : nombre de fois que l’utilisateur appuie sur une option pour basculer l’appel, ce qui affiche la liste d’appels en attente.
- **multipleAccounts** : nombre de comptes de l’utilisateur.
- **multipleTenants** : nombre de locataires par compte.
- **mute** : Désactiver la conversation.
- **muteOnWhiteboard** : l’utilisateur active ou désactive depuis l’écran du tableau blanc.
- **muteParticipant** : Désactiver le micro du participant (accède à la page d’action).
- **my_location_button_clicked** : l’utilisateur centre la carte sur sa position en appuyant sur **Ma position** .
- **my_location_clicked** : l’utilisateur centre la carte sur sa position en appuyant sur le **point bleu** sur la carte.
- **myShiftPickerClicked** : journalisé uniquement si la demande envoyée concerne un échange ou une proposition. Sélecteur **Mon Shift** est sélectionné.
- **nameGroupChat** : Attribuer un nom à la conversation de groupe.
- **nativeTimeClockBreak** : une pause sur la pointeuse.
- **nativeChatLink** : un lien vers une conversation native est sélectionné.
- **navActivity** : Accéder à la page Flux d’activités.

- **navBookmark** : l’utilisateur accède à l’onglet ou l’application **Enregistrés** sur la barre inférieure ou le tiroir d’applications.
- **navCalendar** : l’utilisateur accède à un calendrier.
- **navCallingSettings** : l’utilisateur accède aux paramètres d’appel.
- **navCalls** - appui sur l’onglet **Appels**.
- **navCamera** : l’utilisateur accède à l’onglet ou l’application **Caméra** sur la barre inférieure ou le tiroir d’applications.
- **navChat** : l’utilisateur accède à l’onglet ou l’application **Conversation** sur la barre inférieure ou le tiroir d’applications.
- **navContacts** : l’utilisateur accède à l’onglet ou l’application **Contacts** ou **Personnes** sur la barre inférieure ou le tiroir d’applications.
- **navDashboardTab** : l’utilisateur accède à l’onglet **Tableau de bord** dans une conversation.
- **navDynamics365** : l’application Dynamics365 est ouverte.
- **navFiles** : l’application de fichiers est sélectionnée ; indique si l’utilisateur peut démarrer l’application de fichiers depuis le tiroir des applications (iOS).
- **navFilesTab** : l’application de fichiers est sélectionnée ; indique si l’utilisateur peut démarrer l’application de fichiers depuis la barre de navigation inférieure (iOS).
- **navMeetings** - appui sur l’onglet **Calendrier**.
- **navNotes** : l’application Notes est ouverte.
- **navOrganization** : l’application Organisation est ouverte.
- **navOrgChart** : l’application Organigramme est ouverte.
- **navPeople** : l’application Contacts est ouverte.
- **navPeopleSettings** : l’utilisateur accède à la catégorie **Contacts** dans le menu Paramètres.
- **navPersonalFiles** : l’application de fichiers est sélectionnée ; indique si l’utilisateur peut démarrer l’application de fichiers depuis la barre de navigation (Android). 
- **navPhotoTab** - l’utilisateur accède à l’onglet **Photo**.
- **navSaved** : l’utilisateur accède à l’onglet ou l’application **Enregistrés** sur la barre inférieure ou le tiroir d’applications.
- **navSelectPlan** : l’utilisateur sélectionne un plan partagé pour y accéder depuis la vue d’accueil.
- **navSelectPersonalList** : l’utilisateur sélectionne un plan personnel pour y accéder depuis la vue d’accueil.
- **navSelectSmartList** : l’utilisateur sélectionne un plan intelligent pour y accéder depuis la vue d’accueil.
- **navTasks** : l’application Tâches est ouverte.
- **navTeams** : appui sur **Tout afficher**.
- **navVideocamera** : l’utilisateur accède à l’onglet ou l’application **Caméra** sur la barre inférieure ou le tiroir d’applications.
- **navVideoTab** - l’utilisateur accède à l’onglet **Vidéo**.
- **navVoicemail** : l’utilisateur accède à la page de messagerie vocale.
- **navWalkieTalkie** : l’application Talkie-walkie est ouverte.
- **navWiki** : l’application Wiki est ouverte.
- **newChat** : l’utilisateur crée une conversation.
- **newCall** : appui sur **Nouvel appel**.
- **newCallDialPad** : appui sur **Pavé numérique** sur l’onglet.
- **newCallPeople** : appui sur **Contacts** sur l’onglet.
- **noBGActivityDetected** : seuil d’échecs d’activités d’arrière-plan dépassé.
- **notBlockedDevice** : l’utilisateur n’a pas atteint le seuil d’échecs d’activités d’arrière-plan pendant 30 jours.
- **notNow** - appui sur **Plus tard** dans le rappel.
- **notNowUpdate** : mise à jour reportée.
- **notification/notification_clicked** : déclenché lorsqu’une notification est sélectionnée.
- **notificationNavChannelConversation** : Lancer l’application par le biais d’une notification concernant une conversation de canal.
- **notificationNavChannelThreadConversation** : Lancer l’application par le biais d’une notification concernant un message spécifique dans une conversation de canal.
- **notificationSettingTurnedOff** : Désactiver les notifications Push pour l’application Teams pour Android.
- **notificationNavPreCall** : l’utilisateur reçoit une notification Une réunion commence qui lui permet d’accéder à l’écran préalable à l’appel lorsqu’il la sélectionne.
- **ocvFeedback** : concerne les performances du formulaire de commentaires OCV.
- **ocvFormCancelled** : le formulaire de commentaires OCV est annulé et l’utilisateur revient à l’application.
- **ocvFormOpened** : le formulaire de commentaires OCV est ouvert.
- **ocvFormSubmit** : l’utilisateur envoie le formulaire de commentaires OCV en cliquant sur Envoyer.
- **offerRecipientClicked** : journalisé uniquement si la demande envoyée est une proposition. L’utilisateur accède au sélecteur de membre d’équipe pour proposer un shift. Proposer signifie proposer un congé de shift.
- **offerSwapShiftFromL1** : le type de shift que l’utilisateur tente de proposer ou d’échanger depuis une liste de shifts. L’action iOS est un **balayage vers la droite** et l’action Android est une **pression longue**.
- **offerSwapShiftFromL1Triggered** : l’utilisateur propose d’échanger un shift avec un autre utilisateur.
- **officeLens** : l’application de la fonctionnalité de caméra officeLens est démarrée, lorsque :
  - l’utilisateur tente de joindre une photo à son message ;
  - l’utilisateur tente de prendre et charger une photo directement dans la galerie.
- **officeLens ou cameraImage** : appui sur l’image d’appareil photo : un appareil photo standard ou Office Lens.
- **onBackClicked** : appui sur la flèche de retour pour revenir à la page précédente.
- **oneNote** : l’application OneNote est ouverte.
- **open** : appui sur Paramètres de notification.
- **open edit** : données de télémétrie d’utilisation de Wiki ; appui sur le bouton pour modifier le wiki.
- **openApp** : une application personnelle est ouverte.
- **openAppDrawer** - appui sur **Plus** sur la barre inférieure pour ouvrir le tiroir des applications.
- **openEditMeetingForm** : appui sur **Modifier** depuis la page Détails de la réunion.
- **openFile** aide à vérifier que :
  - un fichier a pu être correctement ouvert dans la conversation ;
  - un fichier a pu être ouvert depuis un listage de fichiers ;
  - des fichiers peuvent être ouverts depuis une liste OneDrive ;
  - des fichiers peuvent être ouverts depuis une liste de canaux ;
  - des fichiers peuvent être ouverts depuis des conversations de groupes ;
  - un fichier peut être ouvert depuis l’application de fichiers ;
  - un fichier de message peut être correctement ouvert depuis le chicklet ;
  - des fichiers peuvent être correctement ouverts depuis une liste récente ;
  - un fichier peut correctement être ouvert depuis une liste de fichiers ;
  - un fichier peut être ouvert depuis un chicklet de fichiers de messages ;
  - des fichiers peuvent être correctement ouverts depuis une liste de fichiers.
- **openInAppClicked** : option dans la liste Plus d’options d’un élément de tâche, disponible uniquement pour les tâches personnelles.
- **opensCalendarView** : appui sur le bouton **Shifts ouverts** dans l’onglet **Planification**.
- **openContactCard** : appui sur une icône de **Contact** ou sur un contact dans l’application Contacts pour ouvrir la carte de visite de ce contact.
- **openContactCard_ReactionSummary** : accès à la carte de visite depuis la page Résumé des réactions.
- **openFileInApp** : permet de déterminer si l’utilisateur a choisi d’ouvrir des fichiers à l’intérieur ou à l’extérieur de Teams.
- **openHamburgerMenu** : appui sur l’icône **hamburger** dans le coin haut gauche pour ouvrir le menu latéral et accéder aux paramètres, à la présence et au changement de locataires.
- **openInStream** : Ouvrir une vidéo dans Stream.
- **openMeetingDetails** : bouton ou page Ouvrir les détails de la réunion d’une réunion en particulier.
- **openModalityPicker** : X = ChatsAndChannels pour les conversations et les canaux.
- **openNewMeetingForm** : une sous-tâche personnelle a correctement été mise à jour.
- **openNewMeetingForm** : Ouvrir le planificateur lors de la configuration d’une nouvelle réunion.
- **openPhotoLibrary** : Sélectionner une photothèque.
- **openQuietDays** : Accéder à la page Jours de déconnexion.
- **openQuietHours** : Accéder à la page Heures de déconnexion.
- **openReactionHoverBubble** : appui sur **Ajouter une réaction** sur la page Résumé des réactions.
- **openReactionSummary** : Ouvrir le tiroir Résumé des réactions.
- **openSettingsSetUpInstructions** : Ouvrir les **Paramètres** depuis les instructions.
- **openSharedLink** : un lien est ouvert depuis une vignette de liens du tableau de bord ou depuis la galerie de liens.
- **openShiftsClicked** : nombre de personnes ayant appuyé sur l’icône **Calendrier**.
- **orgChart – aucun AS affecté** : données de télémétrie d’utilisation de base pour l’organigramme.
- **pageEntered** : l’utilisateur accède à une page.
- **parental_consent_grant** : l’utilisateur accorde à un mineur de sa famille MSF l’autorisation d’utiliser la fonctionnalité de position en direct dans TFL.
- **parental_consent_remove** : l’utilisateur retire à un mineur de sa famille MSF l’autorisation d’utiliser la fonctionnalité de position en direct dans TFL.
- **pauseVoicemail** - appui sur **Pause** sur un élément de messagerie vocale.
- **peoplePickerDismissed** : indique que le sélecteur Personnes a été ignoré.
- **peoplePickerInvoked** : le sélecteur de personnes est utilisé à sept emplacements dans Teams pour mobiles, parmi eux :
  - sélecteur de Nouvelle conversation ;
  - Transférer un message ;
  - Ajouter un participant à une réunion.
- **personalAppNavBotChat** : Accéder au robot dans une application personnelle.
- **personalAppNavTab** : Accéder à des onglets depuis une application personnelle.
- **photoLibraryPicker** - appui sur **Ouvrir la photothèque** dans le sélecteur d’images.
- **pickGalleryPhoto** : Choisir une photo depuis la galerie.
- **pickParticipantChatDetails** : Choisir un utilisateur depuis la liste.
- **pickRecentPhoto** : l’utilisateur choisit une image récente à partager.
- **pinChannel** : Épingler un canal pour l’afficher au-dessus de la liste d’équipes et de canaux.
- **pinSelf** : M’épingler depuis la feuille d’action.
- **pinUser** : Épingler un utilisateur depuis la feuille d’action.
- **place_created** : l’utilisateur a créé un emplacement partagé.
- **place_deleted** : l’utilisateur a supprimé un emplacement partagé.
- **place_edited** : l’utilisateur a modifié un emplacement partagé.
- **play** : Lire l’enregistrement.
- **playVoicemail** - appui sur **Lire** sur un élément de messagerie vocale.
- **plusButtonClicked** : appui sur **Plus** (**+**).
- **pptNextSlide** : Diapositive suivante en tant que présentateur ou dans l’affichage privé.
- **pptPreviousSlide** : Diapositive précédente en tant que présentateur ou dans l’affichage privé.
- **pptReturnToPresenter** : Accéder à la diapositive **En direct** (celle sur laquelle le présentateur et tout le monde se trouve).
- **pptStopPresenting** : Arrêter la présentation.
- **pptTakeControl** : Prendre le contrôle.
- **preJoinAddRoom** : appui sur **Ajouter une salle** dans le menu déroulant préalable à la participation, appui sur **Rejoindre** dans le scénario **Ajouter une salle**.
- **preJoinAudioOff** : appui sur **Son désactivé** dans le menu déroulant préalable à la participation.
- **preJoinAutoAddRoom** - appui sur **Rejoindre maintenant** lorsqu’une salle est à proximité.
- **preJoinBack** - appui sur **Précédent** ou **Fermer**.
- **preJoinDenied** : l’utilisateur ne peut pas rejoindre une réunion.
- **preJoinDeviceAudioJoin** - appui sur **Rejoindre en utilisant les fonctionnalités audio de l'appareil** dans le menu déroulant.
- **preJoinDialIn** : appui sur **Composer** dans le menu déroulant préalable à la participation.
- **preJoinDialInCall** : l’utilisateur confirme sa demande d’action **Composer** préalable à la participation.
- **preJoinDialInCancel** : l’utilisateur annule sa demande d’action **Composer** préalable à la participation.
- **preJoinDialOut** : appui sur **Me rappeler** dans le menu déroulant préalable à la participation.
- **preJoinDialOutCall** : l’utilisateur confirme sa demande **Me rappeler** préalable à la participation.
- **preJoinDialOutCancel** : l’utilisateur annule sa demande **Me rappeler** préalable à la participation.
- **preJoinPSTNOptions** : l’utilisateur sélectionne un menu déroulant pour obtenir d’autres options de participation.
- **priorityChange** : un filtre de priorité est appliqué lors de l’affichage d’une liste de tâches.
- **priorityPickerClicked** : l’utilisateur accède au sélecteur de filtres de priorité depuis l’écran de filtres d’une liste des tâches.
- **privateMeetingJoin** - appui sur **Participation à une réunion** depuis une conversation de réunion privée.
- **processInBG** : notification entrante de processus en arrière-plan (Android).
- **processInFG** : notification entrante de processus en premier plan (Android)
- **profileNameSaved** : le nom du profil a été mis à jour.
- **progressItemClicked** : le sélecteur de progression d’une tâche a correctement été ouvert.
- **promotedToPresenter** : l’utilisateur promeut un participant – bouton **Changer** dans une boîte de dialogue.
- **provideFeedbackDismiss** : l’utilisateur masque l’invite qui lui propose d’envoyer ses commentaires sur les raisons pour lesquelles il n’aime pas l’application.
- **provideFeedbackNo** : l’utilisateur répond négativement à l’invite qui lui propose d’envoyer ses commentaires sur les raisons pour lesquelles il n’aime pas l’application.
- **provideFeedbackYes** : l’utilisateur répond positivement à l’invite qui lui propose d’envoyer ses commentaires sur les raisons pour lesquelles il n’aime pas l’application.
- **provideRatingDismiss** : l’utilisateur masque l’invite qui lui propose de Nous évaluer sur le magasin d’applications après avoir indiqué qu’il aime l’application.
- **provideRatingNo** : l’utilisateur répond négativement à l’invite qui lui propose de Nous évaluer sur le magasin d’applications après avoir indiqué qu’il aime l’application.
- **provideRatingYes** : l’utilisateur répond positivement à l’invite qui lui propose de Nous évaluer sur le magasin d’applications après avoir indiqué qu’il aime l’application.
- **proximityPermissionDismissed** : la bannière d’autorisation est masquée.
- **proximityPermissionGranted** : l’autorisation est donnée sur la fenêtre contextuelle.
- **proximityPermissionViewed** : appui sur la bannière d’autorisation.
- **pushNotification** se déclenche lorsque :
  - un démarrage est effectué par le biais d’une notification ;
  - une notification Push est sélectionnée ;
  - un appui est effectué sur une notification Push de reconnexion ;
  - un appui est effectué sur une notification Push **Échec de reconnexion**.
- **quickNotificationAction** : l’utilisateur interagit avec une des réponses d’actions rapides sur une notification (comme la possibilité d’appliquer la mention J’aime directement depuis la notification Push).
- **quickSelectImagePicker** : Sélection rapide.
- **quickStartLiveEventJoin** : l’utilisateur rejoint un événement en direct rapide.
- **quietHoursValues** : capture l’état des Heures de déconnexion lors de la navigation par le bouton Précédent.
- **quotedReplySent** : l’utilisateur envoie un message de réponse avec le type de contexte.
- **reactAngry_CM** : Réagir avec En colère depuis le menu contextuel.
- **reactAngry_HB** : Réagir avec En colère depuis la bulle de pointage.
- **reactHeart_CM** : Réagir avec Cœur depuis le menu contextuel.
- **reactHeart_HB** : Réagir avec Cœur depuis la bulle de pointage.
- **reactLaugh_CM** : Réagir avec Rire depuis le menu contextuel.
- **reactLaugh_HB** : Réagir avec Rire depuis la bulle de pointage.
- **reactLike_CM** : Réagir avec J’aime depuis le menu contextuel ou mention J’aime sur un message de robot.
- **reactLike_doubleTap** : Réagir avec J’aime par une double pression.
- **reactLike_HB** : Réagir avec J’aime depuis la bulle de pointage.
- **reactSad_CM** : Réagir avec Triste depuis le menu contextuel.
- **reactSad_HB** : Réagir avec Triste depuis la bulle de pointage.
- **reactSurprised_CM** : Réagir avec Surprise depuis le menu contextuel.
- **reactSurprised_HB** : Réagir avec Surprise depuis la bulle de pointage.
- **reactRemoved_HB** : l’utilisateur retire une réaction par l’expérience de la page Résumé des réactions.
- **readReceipts** : fonctionnalité activée par l’utilisateur.
- **redeemInvite** : acceptation d’invitation dans l’application.
- **redeemLinkInAppStart** : l’utilisateur a initié l’échange du lien d’invitation à partir de l’application Teams.
- **refreshCalendarList** : Faire glisser vers le bas pour actualiser l’affichage de l’agenda.
- **refreshLinksGallery** : l’utilisateur fait glisser vers le bas pour actualiser la galerie de liens.
- **removeAssignee** : une personne affectée est retirée de l’affichage du sélecteur d’affectations (par opposition à *assignmentRemoved* qui se déclenche lorsque l’utilisateur appuie sur **x** en dehors de l’affichage du sélecteur d’affectations).
- **removeMeeting** : appui sur **Supprimer du calendrier** depuis la page Détails de la réunion d’une réunion annulée.
- **removeParticipantFromEditMeeting** : Retirer un participant après un appui sur **Modifier la réunion** depuis la page Détails de la réunion.
- **removeParticipantFromNewMeeting** : Retirer un participant depuis la page du planificateur lors de la configuration d’une nouvelle réunion.
- **removeReplyObject** : l’utilisateur a retiré un objet de réponse d’une zone de rédaction.
- **removeUser** : une personne affectée est retirée de l’affichage du sélecteur d’affectations (par opposition à *assignmentRemoved* qui se déclenche lorsque l’utilisateur appuie sur **x** en dehors de l’affichage du sélecteur d’affectations).
- **removeUser_CM** : l’utilisateur retire une personne par la liste de participants d’une conversation.
- **removeUserConfirm** : l’utilisateur confirme le retrait d’un utilisateur dans une boîte de dialogue.
- **removeUserContextMenu** : l’utilisateur retire un participant par un menu contextuel.
- **removeUserSwipe** : l’utilisateur retire un participant par un balayage.
- **reorderChannelItem** : l’utilisateur réarrange l’ordre des canaux épinglés.
- **reportAbuseConfirmation** : l’utilisateur appuie sur **Terminé** sur l’écran de confirmation.
- **reportAbuseOpen** : nombre d’appuis sur **Signaler un problème** dans le menu contextuel.
- **reportAbuseSend** : lorsqu’un utilisateur sélectionne le bouton **Rapport** , les données de télémétrie doivent stocker le type de rapport sélectionné.
- **replyChain** : appui sur le bouton ou zone de texte **Nouveau message** dans la chaîne de réponses (fil de discussion).
- **replyChannel** : appui sur **Répondre** dans un canal.
- **replyNavigation** : un objet Répondre est sélectionné afin d’accéder à la publication référencée.
- **replySendMessage** : Envoyer une réponse de canal.
- **replyViaMsgOptions** : l’utilisateur commence une réponse via le menu contextuel.
- **replyViaSwipe** : l’utilisateur commence une réponse via un balayage.
- **requestActedOn** : un manager agit sur des demandes de shifts ouverts.
- **requestActionClicked** : Lorsque l’utilisateur demande une action, comme la sélection d’une demande de shift (que l’affichage soit celui d’un manager de travailleurs de première ligne(FLW) ou d’un travailleur de première ligne).
- **requestDetailsClicked** : Lorsque la demande de shift est sélectionnée (que l’affichage soit celui d’un manager  de travailleurs de première ligne(FLW) ou d’un travailleur de première ligne).
- **requestJoinTeam** - appui sur **Demande**.
- **requestSent** : une demande a été envoyée.
- **requestToJoinTeam** : Demander à rejoindre l’équipe (publique ou privée).
- **requestToJoinTeamError** : erreur liée à la demande de participation.
- **requestTypeClicked** : indique le type de demandes que les utilisateurs sélectionnent depuis le sélecteur de demandes.
- **resetLocalVault** : l’utilisateur réinitialise et efface toutes les données sécurisées de son appareil.
- **resolveIssue** - appui sur **Résoudre** dans le menu volant de conseils de dépannage des notifications afin d’accéder à l’application bloquante.
- **responseClicked** : l’utilisateur appuie sur une page de réponse.
- **retryButtonClicked** : appui sur **Réessayer**.
- **returnToMessage** : appui sur **Retour** afin de revenir au message.
- **runningLate** : l’utilisateur est en retard.
- **safeLink** : un lien est vérifié fiable.
- **saveEditMeeting** : appui sur **Enregistrer** sur la page de planificateur de réunion après avoir mis à jour la réunion.
- **saveNewMeeting** : appui sur **Enregistrer** sur la page de planificateur de réunion. Utile pour journaliser les réunions correctement enregistrées et le pourcentage d’échecs de création de réunions dus à des erreurs côté client ou de service.
- **savePlanClicked** : appui sur **Créer** dans le créateur de nouveau plan à partir de l’ouverture par défaut de l’application.
- **dashboardNav** : l’utilisateur accède à une vignette sur le tableau de bord de la conversation.
- **scenarioDashboardNav** : l’utilisateur accède à l’onglet tableau de bord dans une conversation (similaire à l’onglet de conversation).
- **scheduledMeetingJoin** : appui sur **Participation à une réunion** depuis l’objet de réunion planifiée.
- **scrollCalendarList** : défilement dans le calendrier.
- **scrollDatePicker** : défilement dans le contrôle de sélecteur de dates du calendrier.
- **searchAbandoned** : une recherche a été abandonnée.
- **searchCancelled** se déclenche lorsque :
  - une recherche a réussi ou l’utilisateur a abandonné la recherche ;
  - une requête de recherche a réussi.
- **searchContacts** : Rechercher depuis la liste d’appels.
- **searchInitiated** : indique si une recherche peut être déclenchée ainsi que la source du déclencheur de recherche.
- **searchMeetingParticipants** : Rechercher des participants à ajouter depuis le formulaire du planificateur. Utilisé pour faire la distinction entre le nombre de rendez-vous créés et le nombre de réunions créées.
- **searchResultsClicked** : indique :
  - si des résultats pertinents peuvent être trouvés ;
  - si les résultats de recherche proviennent de l’onglet Tout ou d’un domaine individuel.
- **searchTabClicked** : indique :
  - les informations de domaine du résultat de recherche – pour les personnes, les conversations, les messages et les fichiers ;
  - si des résultats pertinents sont trouvés.
- **seeAllMeetingParticipants** : appui sur **Tout afficher** depuis la page Détails de la réunion, ou Voir tous les participants. Journalise les données utilisateur dans l’ensemble de l’entonnoir de calendrier où les détails des réunions du calendrier jouent un rôle primordial ; aide à la validation des sélections pour les compositions, les réunions Teams, les RSVP, etc.
- **seeMeetingDescription** : ouverture de la page Détails de la réunion ou appui sur **Afficher plus** sur Description de la réunion depuis la page Détails de la réunion. Les données sont journalisées dans l’ensemble de l’entonnoir de calendrier où les détails des réunions du calendrier jouent un rôle primordial ; aide à la validation des sélections pour les compositions, les réunions Teams, les RSVP, etc.
- **seeRsvpMeetingOptions** : appui sur **Prévenir l’organisateur** depuis la fenêtre contextuelle RSVP, ou appui sur les options **RSVP** depuis la page Détails de la réunion.
- **selectActivityType** : capture les gestes de sélection sur un élément de flux.
- **selectCalendarDate** : Sélectionner une date spécifique dans le contrôle du sélecteur de dates du calendrier.
- **selectDevice** : sélection d’un appareil dans l’application Écrans.
- **selectGeneralSetting** : Accéder aux paramètres généraux.
- **selection** : appui sur Contact de l’appareil ou Contact de l’entreprise.
- **selectMeetingChicklet** | Réunion.
- **selectMeetingRsvpOption** : appui sur **RSVP** pour choisir une option.
- **selectMeetingRsvpOptions** : appui sur **RSVP** pour choisir une option.
- **selectPersonalList** : l’utilisateur accède à une liste de tâches personnelle en appuyant dessus.
- **selectPlannerList** : l’utilisateur accède à une liste de tâches partagée en appuyant dessus.
- **selectSettingOption** : Accéder à l’onglet **Paramètres** depuis le menu hamburger.
- **selectTheme** : Activer le thème sombre.
- **selectUser** : une personne affectée est sélectionnée pour une tâche.
- **selfLongPress** : pression longue sur Moi.
- **send_earlycancelledCQF** : le formulaire CQF Appel annulé précocement est envoyé.
- **send_map_pin_clicked** : l’utilisateur envoie une position statique.
- **send_ratemycallCQF** : le formulaire CQF Évaluer mon appel est envoyé.
- **send_ratemyliveeventCQF** : le formulaire CQF Évaluer mon événement en direct est envoyé.
- **sendForward** : l’utilisateur confirme l’envoi d’un message transféré depuis le sélecteur de transfert.
- **sendImage** : Envoyer une image.
- **sendLocation** : Envoi l’emplacement.
- **sendMsg** : appui sur **Envoyer** dans une réponse.
- **sendRequestBulkClicked** : demande en bloc envoyée.
- **sendRequestClicked** - appui sur **Demande de shift envoyée**.
- **sendVoiceMessage** - le bouton **Enregistrement** est relâché.
- **setting/dismiss** : paramètre de contacts de l’appareil.
- **settingsNavReadReceiptNotice** : l’utilisateur accède aux paramètres depuis l’avis de fonctionnalité.
- **settingsOpened** : le fuseau horaire de l’appareil de l’utilisateur ne correspond pas à celui de l’équipe et l’utilisateur accède aux Paramètres.
- **setupPinVault** : l’utilisateur enregistre un code confidentiel sécurisé pour son compte. 
- **shareCharmCompleted** : l’utilisateur a terminé le partage d’un lien d’invitation via l’icône de partage d’application.
- **shareCharmOpened** : l’utilisateur a lancé le partage d’un lien d’invitation via l’icône de partage d’application. 
- **shareFile** : appui sur **Partager un fichier**. Permet également de vérifier que :
  - l’utilisateur a pu lancer l’opération de partage de fichier ;
  - l’utilisateur peut partager le fichier.
- **shareHistory** : appui sur le sélecteur d’historique de partage.
- **shareInto** : l’utilisateur partage un élément dans Teams depuis une autre application.
- **sharePlanToChat** : une liste partagée est partagée manuellement dans la conversation de groupe depuis l’application Tâches comme chicklet ; vérifie l’envoi du chicklet avec le service de messagerie principal.
- **sharePPTFromChannels** - appui sur **Équipes et canaux**.
- **sharePPTFromOneDrive** - appui sur **OneDrive**.
- **shareRecording** : Partager un enregistrement.
- **shareScreen** : Commencer ou Arrêter un partage d’écran.
- **shareShift** : les informations fournies lorsqu’un shift est partagé.
- **shareShiftsClicked** : les détails d’un shift ouvert.
- **shareTray** -  **Partager...** est sélectionné dans la feuille d’actions.
- **shiftAssigneeClicked** : l’affichage Calendrier de shifts présentant les détails des shifts particuliers.
- **shiftDetails** : permet d’afficher les détails d’un shift.
- **shiftDetailsCalendar** : l’utilisateur accède aux détails du shift.
- **shiftDetailsMyShifts** : appui sur **Calendrier** depuis l’onglet **Planifications**.
- **shiftDetailsTodaysCoworkers** : appui sur **Début** ou **Fin de la pause** depuis l’écran de pointage.
- **shortCircuitContactCount** : nombre de contacts court-circuités correspondant au carnet d'adresses reçus dans une extraction de contacts.
- **showBanner** : nombre de fois que la bannière **Connexion au WiFi, Pas d’internet** apparaît.
- **showCard** : appui sur les boutons d’une carte. Les cartes sont des constructions de plateforme clés et la mesure de leur utilisation et de leur motif est nécessaire à la compréhension de l’utilisation de la plateforme et à la surveillance de l’apparition de problèmes potentiels du côté client.
- **shownReadReceiptNotice** : un avis de fonctionnalité apparaît à l’utilisateur avec des options de paramètres.
- **signIn** - appui sur **Se connecter** sur la page d'accueil, ou appui sur **Se connecter**.
- **SignInWithOTP** : l’utilisateur sélectionne l’option permettant de se connecter en tant qu’invité avec un code secret à usage unique (OTP). 
- **signUp** - **Créer un compte gratuit** ou **S’inscrire gratuitement** est sélectionné.
- **SignUpFromSignIn**: l’utilisateur appuie sur l’option **Créer un nouveau compte** à partir de la connexion.
- **simultaneousCallForward** se déclenche lorsque :
  - une cible de transfert d’appel simultané est définie ;
  - le transfert d’appel simultané est activé (Sonnerie d’appel est activé et Activer la sonnerie pour est défini).
- **skipVerificationForLink** : l’utilisateur choisit d’ignorer la vérification.
- **smartReply** : bouton bascule Réponse intelligente est cliqué.
- **SMSSendMessage** : l’utilisateur envoie un SMS.
- **sortChanged** : l’utilisateur change l’ordre de tri lors de l’affichage d’une liste de tâches.
- **SSOAccountListItem**: déclenché lorsque l’utilisateur appuie sur un compte d’authentification unique pour se connecter.
- **startEditing** - appui sur **Modifier**.
- **startPresentPhoto** : Commencer à présenter une photo.
- **startPresentVideo** : Commencer à présenter une vidéo.
- **startPSTNCall** se déclenche lors :
  - d’un résultat RTCP dans une Recherche générale (Personnes) ;
  - d’un appel RTCP effectué à partir d’une carte de contact de l’appareil ;
  - d’un appel RTCP effectué à partir de la liste d’appels ;
  - d’un numéro DialPSTN en utilisant le pavé numérique.
- **startRecording** : Commencer l’enregistrement.
- **startVoicemailCall** - appui sur **Modifier le message d’accueil de la messagerie vocale**.
- **static_place_selected** : l’utilisateur fait glisser la carte pour sélectionner une position statique.
- **statusCheckBoxClicked** : un élément de tâche est achevé ou inachevé.
- **statusMsgCancel** : l’utilisateur annule le changement de message de statut.
- **statusMsgExpiry** : l’utilisateur définit le délai d’expiration.
- **statusMsgSet** : l’utilisateur définit un nouveau message de statut.
- **statusPageViaContactCard** : l’utilisateur entre dans l’expérience de rédaction de statut par une carte de visite.
- **statusPageViaHamburger** : l’utilisateur entre dans l’expérience de rédaction de statut par le menu hamburger.
- **stop_location_sharing_logout** : l’utilisateur se déconnecte de l’application.
- **stopMeetingButton** : nombre de fois que l’utilisateur quitte la salle d'attente sans avoir été admis dans la réunion.
- **stopPresentPhoto** : Arrêter la présentation de la photo.
- **stopPresentVideo** : Arrêter la présentation de la vidéo.
- **stopRecording** : Arrêter l’enregistrement.
- **structuredMeetingsBannerDismiss** : l’utilisateur masque la bannière l’informant de son rôle dans la réunion.
- **stuckOnConnectingDialInSelected** - appui sur **Composer** dans le tiroir.
- **stuckOnConnectingRetrySelected** - appui sur **Réessayer** dans le tiroir.
- **stuckOnConnectingShownDismissed** : l’utilisateur masque le tiroir.
- **suggested_place_selected** : l’utilisateur partage une position statique en sélectionnant un lieu suggéré.
- **Switching**: le client ou le compte est basculé de l’application. Cela est nécessaire pour mesurer les problèmes de commutateur de compte/client de manière proactive et offre une expérience de changement de compte/client fluide.
- **switchTeamAction** : l’utilisateur change d’équipe au sein de la pointeuse. Se déclenche après la sélection par l’utilisateur de l’équipe pour laquelle il souhaite changer.
- **switchTeamsDialogTriggered** : l’utilisateur affiche l’onglet **Shifts**.
- **tabActionCopyLink** : la manière dont les utilisateurs découvrent et utilisent le lien de copie de l’onglet sur mobiles.
- **tabActionMoreOptions** : permet de comprendre l’utilisation de l’ellipse (**…**) dans un onglet.
- **tabActionOpenInBrowser** : utilisation d’Ouvrir dans le navigateur. Nécessaire pour savoir si les utilisateurs préfèrent ouvrir un onglet en dehors de Teams.
- **tabActionOpenInBrowserFromTab** : aide à la compréhension de l’utilisation d’Ouvrir dans le navigateur depuis un onglet Plus d’options – détectabilité et utilisation.
- **tabActionOpenInTeams** : utilisation d’Ouvrir dans. Nécessaire pour savoir si l’ouverture de l’onglet peut être définie par défaut dans Teams.
- **tabActionRemove** : aide à la compréhension de la détectabilité de l’option Supprimer et de l’utilisation de la fonctionnalité. 
- **tabActionRename** : aide à la compréhension de la détectabilité de l’option Renommer et de l’utilisation de la fonctionnalité.
- **tabActionSetting, Android – correctif** : la manière dont les utilisateurs découvrent et utilisent la configuration des onglets sur mobiles.
- **table** : Sélectionner un tableau.
- **tabListMoreOptions** : aide à la compréhension de l’utilisation de Plus d’options pour un onglet.
- **tabOpen** : réussite de l’ouverture d’onglets, ou problèmes lors de l’ouverture d’onglets.
- **tabViewed** : journalisé uniquement si la demande envoyée concerne un échange pour les entrées du sélecteur **Shift d’équipe**.
- **takePhoto** : Prendre une photo.
- **takePhotoPicker** - appui sur **Prendre une photo** dans le sélecteur d’images.
- **tabChicletExpand** : la manière dont les utilisateurs prévisualisent les cartes sur mobiles.
- **tapDatePickerHandle** : développement du contrôle du sélecteur de dates du calendrier.
- **tapSettings** : nombre d’utilisateurs qui reconfigurent des applications sur mobiles.
- **tasksAppLaunchAdaptiveCard** : l’application Tâches est ouverte depuis une carte adaptative dans une conversation de groupe ; vérifie le démarrage de l’application par l’URL du service IC3.
- **tasksAppLaunchComposeExtension** : l’application Tâches est ouverte à partir de l’extension de rédaction dans une conversation de groupe ; vérifie le démarrage de l’application par le service MT.
- **tasksAppLaunchDashboard** : ouverture de l’application Tâches depuis sa vignette de tableau de bord ou d’un plan spécifique ; vérifie le démarrage de l’application par le service MT.
- **tasksAppLaunchDashboardSeeAll** : ouverture de l’application Tâches par le biais du bouton **Afficher tout** sur le tableau de bord ; vérifie le démarrage de l’application par le service MT.
- **tasksAppLaunchDefault** : ouverture de l’application Tâches depuis le tiroir inférieur ; vérifie le démarrage de l’application par le service MT.
- **tabCalendarClicked** : l’utilisateur choisit une équipe depuis le sélecteur d’équipes.
- **teamChannelChanged** : l’utilisateur appuie et accède à un plan depuis une liste de plans. Envoyé uniquement à appInsights, pas à Aria.
- **teamCreate** : l’utilisateur appuie sur l’option pour créer une nouvelle équipe.
- **teamEdit** : l’utilisateur modifie certains aspects d’une équipe dont il est le propriétaire ou l’administrateur.
- **teamNav** : Afficher les options du menu pour une équipe.
- **teamsDeviceCallResumed** : l’utilisateur disposant d’un périphérique Bluetooth connecté (station de téléphone mobile) réactive un appel en attente.
- **teamSelectedClicked** : l’utilisateur appuie sur **Équipe sélectionnée** pour une feuille de temps.
- **teamshiftPickerClicked** : l’utilisateur ajoute une nouvelle entrée de pause. L’événement est journalisé une fois que l’utilisateur enregistre les modifications.
- **tenantSwitch** - On Switch Tenant. Indicateurs de performance de fonctionnalité pour le Basculement entre plusieurs locataires et plusieurs comptes (MTMA), ce qui aide à l’identification des problèmes et leur résolution proactive et à offrir une expérience de changement de locataire ou de compte sans accroc.
- **tenantSwitchUnsupportedError** : erreur Client non pris en charge (lorsque l’erreur est affichée à l’utilisateur). Indicateurs de performance de fonctionnalité pour le Basculement entre plusieurs locataires et plusieurs comptes (MTMA) ; fournit des données de télémétrie sur les erreurs de bascule de locataire ou de compte, ce qui aide à l’identification des problèmes et leur résolution proactive et à offrir une expérience de changement de locataire ou de compte sans accroc.
- **timeClockClicked** : appui sur **Pointeuse** sur l’onglet Mes shifts.
- **timeOffReasonClicked** : indique si une raison est donnée pour le congé.
- **timesheetAddClicked** : l’utilisateur ajoute une note aux modifications de sa pause. L’événement est journalisé une fois que l’utilisateur enregistre les modifications.
 **timesheetBreakAdded** : une nouvelle entrée d’horloge est ajoutée. L’événement est journalisé une fois les modifications enregistrées.
- **timesheetBreakEdited** : l’utilisateur confirme sa feuille de temps. L’événement est journalisé quand l’utilisateur appuie sur Confirmer dans le modal.
- **timesheetBreakNoteAdded** : l’utilisateur supprime sa feuille de temps. L’événement est journalisé quand l’utilisateur confirme la suppression dans le modal.
- **timesheetClockAdded** : l’utilisateur appuie sur Modifier pour une feuille de temps.
- **timesheetClockEdited** : l’utilisateur appuie sur Enregistrer sur une feuille de temps modifiée.
- **timesheetConfirmed** : l’utilisateur ajoute une note aux modifications de sa feuille de temps. L’événement est journalisé une fois que l’utilisateur enregistre les modifications.
- **timesheetDeleted** : indique si l’utilisateur a un rappel de shift défini ou pas, ainsi que le nombre de minutes restantes avant ce shift.
- **timesheetEditClicked** : données de télémétrie de Configuration utilisateur.
- **timesheetEditSaved** : l’utilisateur appuie sur une feuille de temps depuis le profil d’un utilisateur pour l’ouvrir.
- **timesheetNoteAdded** : affichage d’une demande de congé approuvée.
- **titleChanged** : le titre d’un élément de tâche est changé ; se déclenche pour tout changement de caractère.
- **toast** : appui sur le toast dans l’application.
- **toggleChannelsInChat** : Activer ou Désactiver la fonctionnalité. Indicateurs de performance de fonctionnalité pour une expérience unifiée des conversations et des canaux.
- **toggleClicked** : appui sur un bouton bascule.
- **transferNow** se déclenche lorsque :
  - l’utilisateur appuie sur **Transférer** > **Transférer maintenant** ;
  - la cible de transfert est définie sur une personne ;
  - la cible de transfert est définie sur un numéro de téléphone.
- **translateFailed** : La traduction a échoué (sauf hors connexion). Indicateurs de performance de fonctionnalité pour la traduction de messages.
- **trigger_created** : l’utilisateur a créé une limite géographique.
- **trigger_deleted** : l’utilisateur a supprimé une limite géographique.
- **unansweredCallForward** : une cible de transfert d’appel sans réponse est définie. Active également le transfert d’appel sans réponse (Sonnerie d’appel est activé et En cas d’absence de réponse est activé).
- **unblockCaller** : l’utilisateur débloque :
  - un contact ou un numéro depuis la feuille d’action ;
  - un contact ou numéro provenant d’une carte de visite ;
  - un numéro depuis les paramètres.
- **unblockChat** : Débloquer une conversation de robot.
- **unpinChannel** : Désépingler un canal.
- **unpinSelf** : Me désépingler depuis la feuille d’action.
- **unpinUser** : Désépingler un utilisateur depuis la feuille d’action.
- **unsafeLink** : un lien est vérifié non-fiable.
- **updatePersonalTask** : une tâche personnelle a été mise à jour.
- **updatePlaybackSpeedVoicemail** : la valeur de vitesse de lecture d’un message vocal est changée.
- **updateTask** : l’action de mise à jour d’une tâche a échoué.
- **updateTaskState** : confirme que la tâche a été mise à jour. action.
- **upgrade** : appui sur **Mettre à niveau** dans le menu **Plus**.
- **uploadFile** : l’utilisateur appuie sur **Charger depuis l’appareil**.
- **uploadSelectedFile** se déclenche lorsque :
  - des fichiers sont correctement chargés dans le canal ;
  - des fichiers sont correctement chargés dans la conversation ;
  - des fichiers sont chargés dans la fenêtre de réponse ;
  - des fichiers sont correctement chargés dans la conversation de groupe ;
  - scénario d’usage du noyau ;
  - scénario de début de chargement dans un canal ;
  - scénario de début de chargement dans une conversation ;
  - scénario de début ou de fin de chargement dans un canal ;
  - un fichier est correctement chargé dans l’onglet **Fichiers** ;
  - une action est effectuée sur une invite pendant le chargement d’un fichier ;
  - un fichier sélectionné est correctement chargé.
- **uploadSelectFile** : un fichier a correctement été sélectionné ; appui sur **Charger un fichier**.
- **urgentMessageSelect** : un message urgent est sélectionné depuis le menu contextuel Priorité.
- **urgentMessageSend** : un message urgent est envoyé.
- **url** : URL.
- **urlPreview** : aperçu d’URL.
- **urlPreviewAdd** : aperçu d’URL ajouté.
- **urlPreviewOpen** : aperçu d’URL ouvert.
- **urlPreviewRemove** : aperçu d’URL retiré.
- **userConfiguration** : une demande de congé en attente est affichée.
- **userJoinedViaShareLink** : l’utilisateur rejoint la réunion par un lien.
- **userLongPress** : pression longue sur un participant.
- **userProfileOpened** : appui sur une icône **Utilisateur** pour ouvrir un profil utilisateur.
- userTimesheetOpened** : l’utilisateur appuie sur une feuille de temps depuis un profil utilisateur pour l’ouvrir.
- **useWifiForAudioDialog** : l’utilisateur appuie sur **OK** sur l’invite du système alors qu’un administrateur a bloqué les appels audio et vidéo sur mobiles.
- **useWifiForVideoDialog** se déclenche lorsque :
  - l’utilisateur appuie sur **OK** sur l’invite du système alors qu’un administrateur a bloqué les appels vidéo sur mobiles ;
  - l’utilisateur tente d’activer la vidéo dans une réunion alors qu’un administrateur l’a bloquée sur mobiles ;
  - l’utilisateur appuie sur **OK** sur l’invite du système alors qu’un administrateur a bloqué la vidéo dans les réunions sur mobiles.
- **videoUserDoubleTap** : double appui sur un participant vidéo.
- **viewChannelMembers** : Afficher la liste des membres d’un canal.
- **viewContactCard** : carte de visite sélectionnée depuis :
  - un élément de l’historique d’appels ;
  - un élément de messagerie vocale ;
  - une liste d’appels.
- **viewed** : l’utilisateur affiche une page.
- **viewFullAllDayMeetingList** : vue de l’agenda sur mobiles.
- **viewLobbyFromBanner** : nombre de fois que l’utilisateur appuie sur **Afficher la salle d'attente** depuis la bannière de notifications.
- **viewMeetingDetails** : appui sur le menu **…** sur la page Détails de la réunion. Concerne l’usage du menu **Plus** sur les calendriers sur mobiles.
- **viewMeetingOccurrence** : Ouvre les détails de la réunion d’une instance d’une réunion périodique. Données de télémétrie permettant de journaliser les données utilisateur dans l’ensemble de l’entonnoir de calendrier où les détails des réunions du calendrier jouent un rôle primordial ; aide à la validation des sélections pour les compositions, les réunions Teams, les RSVP, etc.
- **viewMeetingSeries** : rendu correct d’une série de réunions lorsque :
  - l’utilisateur passe d’une instance de réunion à la page Détails de la série de réunions ;
  - l’utilisateur appuie sur **Voir la série** depuis la page Détails de la réunion.
- **viewOrgChart** : données de télémétrie d’utilisation de base pour un organigramme.
- **viewRequests** : appui sur **Afficher les demandes**.
- **voiceDataCollectionOptOut** : l’utilisateur refuse l’enregistrement depuis le mobile en cliquant sur la bannière.
- **voicemail – aucun AS affecté** : un orateur appuie sur un élément de messagerie vocal.
- **whiteboardUsed** : l’utilisateur annote le tableau blanc (toute action sur le WebView).
- **wiki – aucun AS affecté** : données de télémétrie d’usage de Wiki.
- **poorNetworkBanner** : bannière réseau médiocre affichée.
- **badNetworkBanner** : bannière réseau de mauvaise qualité affichée.

### <a name="panelview"></a>PanelView

> [!NOTE]
> Pour des informations sur les propriétés des événements Panelview, consultez [Propriétés envoyées avec les événements panelview](#properties-sent-with-panelview-events).

- **appInstall**: déclenché lorsqu’un utilisateur ouvre l’application pour la première fois après l’installation.
- **fileDeleteFailed** - Déclenché en cas d’échec d’une opération de suppression de fichier.
- **fileDeleteSuccess** - Déclenché en cas de suppression d’un fichier.
- **filePreview** - Déclenché dans ces scénarios :
  - Lorsque l’option Partager est tapée dans l’écran d’aperçu.
  - Lorsque l’option Copier est tapée dans l’écran d’aperçu.
  - Lorsque l’option Télécharger est tapée dans l’écran d’aperçu.
  - Lorsqu’un aperçu du fichier est correctement chargé.
- **fichiers** - Déclenché dans ces scénarios :
  - Lorsqu’un fichier est prévisualiser dans l’application Teams.
  - Lorsque l’option Charger d’un fichier est tapée dans l’écran des fichiers OneDrive.
  - Lorsque l’option Copier un lien est tapée dans l’écran d’aperçu.
  - Lorsque l’écran de partage de fichiers est exclu.
  - Lorsque le menu d’options des fichiers est ouvert ou lorsque l’une des options de ce menu est tapée.
  - Lorsque l’écran « en cours d’appel » des fichiers est ouvert.
  - Lorsqu’un fichier est tapé pour s’ouvrir.
- **fichiersChannel** - Déclenché lorsque l’écran des fichiers de canal est ouvert.
- **fileSources** - Déclenché Lorsque le menu d’options des fichiers est ouvert ou lorsque l’une des options de ce menu est tapée.
- **fichierPersonal** - Déclenché lorsqu’un lot de fichiers est chargé dans OneDrive ou dans l’écran des fichiers récents.
- **fileUploadDeleteTrigreed** - Déclenché lorsqu’une pièce jointe est supprimée ou détachée’ de la zone de message.
- **fileUploadFailed** - Déclenché en cas d’échec d’une opération de chargement de fichier.
- **fileUploadLoadindividualNotification** Déclenché lorsque le contenu de la notification de chargement change ou lorsque la notification interagit avec. Les interactions peuvent inclure des mouvements tels que le mouvement de balayage pour faire disparaître la notification ou appuyer sur la notification, etc.
- **fileUploadSuccess** - Déclenché en cas de chargement d’un fichier.
- **fileUploadLoadSummaryNotification** Déclenché lorsque le résumé de la notification de chargement change ou lorsque la notification interagit avec. Les interactions peuvent inclure des mouvements tels que le mouvement de balayage pour faire disparaître la notification ou appuyer sur la notification, etc.
- **meetingFiles** - Déclenché lorsque l’écran des fichiers de réunion est ouvert.
- **meetNowActionSheet** : se déclenche lorsque l’utilisateur crée une réunion Meet Now.
- **navPersonalFiles** - Déclenché lorsque la navigation dans l’écran des fichiers est effectuée.
- **signInSSOPage**: déclenché lorsque l’utilisateur affiche une page d’authentification unique lors de la connexion.
-- **signInError**: déclenché lorsque l’utilisateur rencontre une erreur lors de la connexion. Cela est nécessaire pour identifier et résoudre de manière proactive les problèmes auxquels les utilisateurs sont confrontés lors de la connexion. 
-- **TfLSignInSuccessful** : déclenché lorsque l’utilisateur se connecte à un compte Microsoft personnel. Cela est nécessaire pour comprendre la fiabilité de la connexion et de l’inscription, et identifier et résoudre les problèmes de manière proactive.
-- **TfWFreemiumSignInSuccessful**: déclenché lorsque l’utilisateur se connecte avec succès à un compte freemium. Cela est nécessaire pour comprendre la fiabilité de la connexion et de l’inscription, et identifier et résoudre les problèmes de manière proactive.
-- **TfWSignInSuccessful**: déclenché lorsque l’utilisateur se connecte correctement à un compte professionnel ou scolaire. Cela est nécessaire pour comprendre la fiabilité de la connexion et de l’inscription, et identifier et résoudre les problèmes de manière proactive.
- **appDrawer** : déclenché lorsque le tiroir de l’application est ouvert avec succès.
- **appPolicyChange** : déclenché lorsqu’un utilisateur réinitialise et enregistre une nouvelle commande d’onglets localement.
- **app_stageview** : déclenché lorsqu’un affichage étendu est correctement rendu.

### <a name="scenario"></a>Scénario

> [!NOTE]
> Pour en savoir plus sur les propriétés des événements PanelAction, consulter la section [Propriétés envoyées avec les événements de scénarios](#properties-sent-with-scenario-events).
> 
- **acquire_resource_token_interactive**: appel de service requis qui est déclenché lorsqu’un jeton d’authentification est acquis par une connexion interactive. 
- **acquire_resource_token_silent**: appel de service requis qui est déclenché lorsqu’un jeton d’authentification est acquis par une connexion silencieuse.
- **add_buddy** : capture l’état d’ajout d’un contact.
- **app_crash2** : déclenché lorsque l’application est bloquée de manière inattendue. Fournit des informations sur la fréquence à laquelle l’application Teams se bloque. 
- **app_incremental_sync_launch** : confirme que le nombre de cachets est correctement mis à jour pour le lancement à froid.
- **app_incremental_sync_resume** : confirme que le nombre de cachets est correctement mis à jour pour le lancement à chaud.
- **app_start_cold**: pour surveiller le lancement de l’application à froid (Android uniquement).
- **app_start_hot** : pour surveiller le lancement de l’application à chaud (Android uniquement).
- **app_start_warm** : pour surveiller le lancement de l’application à chaud (Android uniquement).
- **auth_adal_tokens**: appel de service requis pour effectuer une authentification silencieuse. Déclenché lorsqu’un utilisateur démarre l’application ou que le jeton est actualisé à l’expiration.
- **chat_add_giphy** : confirme que l’action de rendu GIF Giphy a été effectuée.
- **chat_send_message_sfc**: déclenché lorsqu’un message de conversation est envoyé dans la conversation d’interopérabilité SfC.
- **cortanaError** : pour surveiller les erreurs Cortana.
- **cortanaView** : pour surveiller l’apparition de la zone de dessin Cortana.
- **cortanaRestart** : pour surveiller le redémarrage de Cortana.
- **cortanaSetNewConversation** : pour surveiller les nouvelles conversations de Cortana.
- **CortanaSpeechRecognization** : pour surveiller la latence de reconnaissance vocale de Cortana.
- **CortanaStart ne** : pour surveiller le démarrage du backend de Cortana.
- **CortanaStartListening** : pour surveiller la démarrage de l’écoute par Cortana.
- **cortanaStopListening** : pour surveiller l’arrêt de l’écoute par Cortana.
- **cortanaThinking** : pour surveiller l'état de Cortana, passez en mode réflexion (attente de la réponse du service).
- **CortanaTokenRefresh est** : pour surveiller l'actualisation du jeton Cortana en avant-plan.
- **cortanaOrtanaSmingUp** : pour surveiller le démarrage du réchauffement de Cortana (Cortana est ouvert mais le jeton est toujours en cours de récupération).
- **cortana_admin_policy_refresh** : pour surveiller l’actualisation des stratégies d’administration Cortana.
- **cortana_background_token_refresh** : pour surveiller l'actualisation du jeton Cortana.
- **cortana_initialization** : pour surveiller les étapes d’initialisation de Cortana.
- **cortana_sdk_events** : pour surveiller les événements liés à la rotation de Cortana.
- **cortana_skill_action_execution** : pour surveiller l'exécution des actions de Cortana.
- **cortana_skill_action_delay** : confirme le début de l’action de retard.
- **cortana_watchdog** : pour surveiller le processus de récupération de surveillance de Cortana.
- **create_default_plan_and_nav_to_view** : confirme la création réussie d’une liste de tâche partagée par défaut et indique le temps pris jusqu’à l’arrivée de l’utilisateur sur l’affichage résultant de son action.
- **create_new_chat_thread_sfc**: déclenché lorsqu’un nouveau thread de conversation est créé pour une conversation d’interopérabilité SfC.
- **create_personal_plan_and_nav_to_view** : confirme la création réussie d’une liste de tâche personnelle et indique le temps pris jusqu’à l’arrivée de l’utilisateur sur l’affichage résultant de son action.
- **create_personal_task** : confirme la création réussie d’un élément de tâche personnelle.
- **create_planner_plan_and_nav_to_view** : confirme la création réussie d’une liste de tâche partagée et indique le temps pris jusqu’à l’arrivée de l’utilisateur sur l’affichage résultant de son action.
- **create_planner_task** : confirme la création réussie d’un élément de tâche partagée.
- **forwardExistingAmsObject** confirme que l’action de transfert du multimédia a réussi ou échoué.
- **delete_personal_plan** : confirme la suppression réussie d’une liste de tâches personnelle.
- **delete_personal_task** : confirme la suppression réussie d’un élément de tâche personnelle.
- **delete_planner_plan** : confirme la suppression réussie d’une liste de tâches partagée.
- **delete_planner_task** : confirme la suppression réussie d’un élément de tâche partagée.
- **json_parse_failure**: fournit des informations sur la fréquence des problèmes d’analyse JSON.
- **fetch_me_profile** : état de création du profil utilisateur.
- **getProfilePicture**: appel de service nécessaire pour obtenir l’image du profil utilisateur. 
- **get_resource_token_async**: appel de service requis pour acquérir des jetons pour Azure Active Directory ressources de manière asynchrone.
- **get_resource_token_sync**: appel de service requis pour acquérir des jetons pour Azure Active Directory ressources de façon synchrone.
- **get_sender_sub_scenario** : obtenir le sous-scénario de l’expéditeur dans Activité.
- **interactiveAuthNopa2** : déclenché lorsqu’aucun utilisateur de mot de passe n’est interrompu pour effectuer une authentification interactive.
- **load_chat_plans_list** : confirme la récupération réussie des plans du Planificateur pour l’affichage du plan d’une conversation.
- **load_home_page** : confirme la récupération réussie des listes de tâches personnelles et partagées pour la vue d’accueil principale.
- **load_personal_task_list** : confirme récupération réussie des tâches d’une liste de tâches personnelle pour l’affichage de la liste de tâches.
- **load_shares_task_list** : confirme la récupération réussie des tâches d’une liste de tâches personnelle pour l’affichage de la liste de tâches.
- **load_smart_task_list** : confirme la récupération réussie des tâches d’une liste de tâches intelligente pour l’affichage de la liste de tâches.
- **meetingAttachmentRender** : confirme le rendu des pièces jointes de réunion.
- **MeetingInsightFe** : confirme la récupération du contenu lié à la réunion.
- **meetingInsightLocatorRender** : confirme le rendu de conseil de localisation de contenu associé à une réunion.
- **meetingInsightRender** : confirme le rendu du contenu associé à une réunion.
- **meetingInsightVisible** : confirme la visibilité du contenu associé à une réunion.
- **open_image** confirme que le rendu de l’image en plein écran a réussi ou échoué.
- **rename_personal_plan** : confirme le changement de nom réussi d’une liste de tâches personnelle.
- **rename_planner_plan** : confirme du changement de nom réussi d’une liste de tâches partagée.
- **save_image** confirme que l’action de sauvegarde de l’image a réussi ou échoué.
- **saveMeProfile**: appel de service requis qui est déclenché lorsque l’utilisateur enregistre le profil
- **share_image** : confirme que l’action de partage de l’image a réussi ou échoué.
- **smart_reply_enabled** : confirme que la réponse intelligente est activée pour l’utilisateur actuel.
- **smart_reply_received** : confirme qu’une suggestion de réponse intelligente a été reçue.
- **smart_reply_banned** : confirme que la réponse intelligente ne peut pas être affichée pour l’utilisateur actuel.
- **park_call_for_hold_v2** : confirme que la mise en attente de l’appel a réussi ou échoué à l’aide du parc d’appels.
- **unpark_call_for_hold_v2** : confirme que la reprise de l’appel a réussi ou échoué à l’aide de l’appel un-park. 
- **update_planner_task_and_nav_to_view** : confirme la mise à jour réussie d’un élément de tâche partagée et le temps pris jusqu’à l’arrivée de l’utilisateur sur l’affichage résultant de son action.
- **update_personalr_task_and_nav_to_view** : confirme la mise à jour d’un élément de tâche personnel et le temps pris par l’utilisateur pour accéder à l’affichage résultant après. 
- **updatePlannerTask** : confirme qu’un utilisateur a correctement mis à jour une tâche dans une liste de tâches partagées.
- **upload_image** confirme que l’action de chargement de l’image a réussi ou échoué.
- **upload_voice_messages** confirme que l’action de chargement de message vocal a réussi ou échoué.
- **voiceMessageUpload** confirme que l’action de chargement de message vocal a réussi ou échoué.
- **cancel_channel_meeting** confirme que l’annulation d’une réunion de canal a réussi ou échoué.
- **cancel_meeting** confirme que l’annulation d’une réunion a réussi ou échoué.
- **cancel_private_meeting** confirme que l’annulation d’une réunion privée a réussi ou échoué.
- **edit_channel_meeting** confirme que l’opération modification d’une réunion de canal a réussi ou échoué.
- **edit_meeting** confirme que l’opération de modification d’une réunion a réussi ou échoué.
- **server_fetch_agenda_view** confirme que la synchronisation des événements de calendrier à l’aide de l’API de niveau intermédiaire a réussi ou échoué.
- **server_fetch_date_picker_view** confirme que la synchronisation des événements de calendrier à l’aide de l’API REST d’Outlook a réussi ou échoué.
- **server_fetch_agenda_view_group** confirme que la synchronisation des événements de calendrier à l’aide de l’API de niveau intermédiaire pour le groupe TFL a réussi ou échoué.
- **server_fetch_date_picker_view_incremental** confirme que la synchronisation incrémentielle des événements du calendrier à l'aide de l'API REST d'Outlook a réussi ou échoué.
- **meeting_details** : confirme que la synchronisation des détails de la réunion a réussi ou échoué.
- **show_meeting_participants**: confirme que l’affichage de la liste des participants à la réunion a réussi ou échoué.
- **search**: confirme que l’ensemble de la session de recherche a réussi ou échoué.
- **time_based_retention_shared_channel** : capture les données de performances pour le nettoyage de la base de données.
- **toggle_searchability** : capture l’état de l’appel réseau pour l’horodatage/décommutation d’un alias.
- **sync_user_entitlements_and_app_definitions** : appel de service requis pour extraire aggregatedEntitlements.
- **bots_load_mediacards** : capture les instances lorsque les cartes de connecteur sont configurées dans la conversation et le canal.
- **bots_load_one_card** : capture si au moins une carte est présente et chargée lors de la conversation avec un bot.
- **load_assignments** : capture une gestion exceptionnelle du chargement de l’application d’affectation.
- **load_channel_tab** - Capture le chargement de l’onglet de canal. (Android uniquement)
- **load_messaging_extension_results** : capture le chargement du résultat de la recherche/requête d’extension de messagerie. (Android uniquement)
- **load_static_tab** - Capture le chargement de l’onglet de statique. (Android uniquement)
- **app_authenticated** : confirme que l’authentification est réussie et qu’un jeton est extrait. (Android uniquement)
- **blocked_by_conditional_access** - Lors de la réception de l’accès conditionnel, le code d’erreur bloqué lors de l’authentification. (nous essayons de forcer l’actualisation du jeton principal dans ce cas). (Android uniquement)
- **get_resource_token_sync** - Déclenché lorsque nous essayons d’extraire le jeton pour les ressources d’application de façon synchrone. (Android uniquement)
- **get_resource_token_sync** - Déclenché lorsque nous essayons d’extraire un jeton pour les ressources d’application de façon asynchrone. (Android uniquement)

## <a name="oneplayer-events"></a>Événements OnePlayer
> [!NOTE]
> Pour les événements OnePlayer, seules les propriétés répertoriées dans les [listes de propriétés pour les événements OnePlayer](#property-lists-for-oneplayer-events) s’appliquent.
### <a name="oneplayer-user-action-events"></a>Événements d’action utilisateur OnePlayer
- **PlayerPlay** - Confirme si l’utilisateur appuie sur le bouton de lecture dans l’affichage OnePlayer.
- **PlayerPause** - Confirme si l’utilisateur appuie sur le bouton suspendre dans la vue OnePlayer.
- **PlayerSeek** - Confirme si l’utilisateur recherche la vidéo à l’aide de la barre de recherche ou des boutons avant/arrière dans la vue OnePlayer (iOS uniquement).
- **VideoPlayerSeekForward** - Confirme si l’utilisateur recherche la vidéo à l’aide de la barre de recherche ou des boutons Avant dans la vue OnePlayer (Android uniquement).
- **VideoPlayerSeekBackward** - Confirme si l’utilisateur recherche la vidéo à l’aide de la barre de recherche ou des boutons Arrière dans la vue OnePlayer (Android uniquement).
- **ChangePlaybackSpeed** : confirme si l’utilisateur a sélectionné une nouvelle vitesse de lecture.
- **changePlaybackQuality** - Confirme si l’utilisateur a sélectionné une nouvelle qualité vidéo pour la lecture.
- **ShareVideo** - Confirme si l’utilisateur a appuyé sur l’icône de partage.
- **PlayerClose** - Confirme si l’utilisateur a appuyé sur l’icône fermer.
- **VideoCaptionsOn** - Confirme si l’utilisateur a basculé sur les sous-titres.
- **VideoCaptionsOff** - Confirme si l’utilisateur a désactivé les sous-titres.
- **ChangePlayerOrientation** : confirme si l’utilisateur a modifié l’orientation de l’appareil.
- **OpenPlayerSettingsMenu** - Confirme si l’utilisateur a ouvert le menu paramètres.
- **OpenPlaybackSpeedMenu** - Confirme si l’utilisateur a ouvert le menu vitesse de lecture.
- **PlayerAction** : action personnalisée fournie par l’application hôte.

### <a name="oneplayer-playback-events"></a>Événements de lecture OnePlayer
- **PlayerHeartbeat** : il s’agit d’un événement récurrent qui envoie l’état actuel du joueur et de la lecture à un journal.

## <a name="property-lists"></a>Listes des propriétés

### <a name="properties-sent-with-all-events"></a>Propriétés envoyées avec tous les événements

| Nom de la propriété                    | Description                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | Heure de création de l’événement                                                |
| EventInfo_Name                   | Nom de l’événement : utilisé pour différencier les types d’événements               |
| EventInfo_BaseType/name          | Type d’événement : utilisé pour différencier les types d’événements dans un événement   |
| EventInfo_Source                 | Source de création de l’événement                                       |
| AppInfo_Language                 | Langue de l’application                                                         |
| AppInfo_ETag                     | ID d’expérimentation attribuée à un utilisateur                                     |
| DeviceInfo_OsBuild               | Version de build du système d’exploitation                                              |
| UserInfo_Mri                     | Type d’ID utilisateur                                                       |
| Session_RunId                    | Type d’ID de session                                                 |
| DeviceInfo_DetailModel           | Modèle de l’appareil                                                  |
| UserInfo_TimeZone                | Fuseau horaire de l’utilisateur                                                |
| DeviceInfo_OsName                | Nom du système d’exploitation de l’appareil                                                       |
| DeviceInfo_NetworkProvider       | Fournisseur réseau de l’appareil                                              |
| DeviceInfo_Model                 | Modèle de l’appareil                                                         |
| DeviceInfo_NetworkType           | Type de réseau de l’appareil                                                  |
| UserInfo_Language                | Langue de l’utilisateur : identique à la langue de l’application                              |
| client_ring/UserInfo_Ring        | Cercle de l’utilisateur : permet de publier les fonctionnalités aux premiers acquéreurs           |
| UserInfo_Id                      | ID de l’utilisateur                                                              |
| UserInfo_TenantId                | ID du locataire                                                            |
| EventInfo_SdkVersion             | Version SDK utilisée pour générer l’événement                               |
| DeviceInfo_Id                    | ID de l’appareil fourni par le système d’exploitation de l’appareil                                      |
| eventpriority                    | Priorité d’un événement                                                 |
| DeviceInfo_Make                  | Fabricant de l’appareil                                                  |
| AppInfo_Version                  | Version de l’application                                                   |
| DeviceInfo_OsVersion             | Version du système d’exploitation de l’appareil                                                    |
| Session_Id/SessionId             | ID de session de la demande                                            |
| Session_Environment              | Environnement de la session                                                  |
| isNetworkIssue                   | Capture des informations en cas de problème de réseau lors du traitement de la demande |
| UserRole                         | Rôle d’utilisateur du locataire                                                |
| Tenant_Model                     | Capture si le compte est un compte freemium ou entreprise          |
| licenseType/UserInfo_LicenseType | Type de licence attribuée à l’utilisateur                                    |
| UserLocale                       | Paramètres régionaux avec lesquels l’accès à l’application est fait                                |
| Intune_sdkVersion                | Version du kit de développement de logiciel Intune                                            |
| Intune_sdkBundleVersion          | Version détaillée du kit de développement de logiciel Intune                                   |
| AppInfo_Environment              | Environnement dans lequel l’accès à l’application est fait                         |

### <a name="properties-sent-with-panelaction-events"></a>Propriétés envoyées avec les événements PanelAction

| Nom de la propriété         | Description                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | URI de la ressource accédée par l’action de l’utilisateur                  |
| Panel_Uri             | URI du panneau livré à l’utilisateur                             |
| Action_Gesture        | Type de mouvement effectué par l’utilisateur sur l’application                       |
| Action_ScenarioType   | Regroupement de fonctionnalités liées à la métrique commerciale pour la fonctionnalité       |
| Panel_Type            | Type de panneau auquel l’utilisateur accède                                    |
| Action_Outcome        | Résultat de l’action effectuée par l’utilisateur                            |
| Team_Id               | ID de l’équipe dans laquelle l’action a été effectuée par l’utilisateur           |
| Module_Type           | Type de module qui a hébergé l’action de l’utilisateur                        |
| Module_Name           | Nom du module qui a hébergé l’action de l’utilisateur                        |
| Module_Summary        | Résumé du module qui a hébergé l’action de l’utilisateur                      |
| Thread_Id             | ID du thread auquel l’utilisateur a accédé                         |
| Panel_PreviousUri     | URI du panneau précédent                                          |
| Panel_Region          | Zone dans laquelle le panneau était hébergé dans l’application                       |
| Panel_LaunchMethod    | méthode par laquelle le panneau été démarré                        |
| Panel_PreviousType    | Type du panneau précédent                                         |
| Thread_Type           | Type de thread auquel l’utilisateur a accédé                                    |
| Module_State          | État du module auquel l’utilisateur a accédé                               |
| Action_Scenario       | Fonctionnalité dans un groupe de fonctionnalités liées à la métrique commerciale |
| Panel_LaunchSource    | information de source du panneau démarré                  |
| Tab_Type              | Type de l’onglet auquel l’utilisateur a accédé                                   |
| Team_Type             | Type d’équipe à laquelle l’utilisateur a accédé                                      |

### <a name="properties-sent-with-panelview-events"></a>Propriétés envoyées avec les événements PanelView

| Panel_Uri          | URI du panneau livré à l’utilisateur                   |
|--------------------|----------------------------------------------------------|
| Panel_Type         | Type de panneau auquel l’utilisateur accède                          |
| Team_Id            | ID de l’équipe dans laquelle l’action a été effectuée par l’utilisateur |
| Thread_Id          | ID du thread auquel l’utilisateur a accédé               |
| Panel_PreviousUri  | URI du panneau précédent                                |
| Panel_Region       | Zone dans laquelle le panneau était hébergé dans l’application             |
| Panel_LaunchMethod | méthode par laquelle le panneau été démarré              |
| Panel_PreviousType | Type du panneau précédent                               |
| Thread_Type        | Type de thread auquel l’utilisateur a accédé                          |
| Panel_LaunchSource | information de source du panneau démarré        |
| Tab_Type           | Type de l’onglet auquel l’utilisateur a accédé                         |
| Team_Type          | Type d’équipe à laquelle l’utilisateur a accédé                            |

### <a name="properties-sent-with-scenario-events"></a>Propriétés envoyées avec les événements de scénario

| Nom de la propriété        | Description |
|----------------------|-------------|
| Scenario_Status      | État d’un scénario : Abandon/OK/ERREUR |
| Scenario_Step        | Lorsqu’un scénario contient plusieurs étapes avec des points d’échec différents, cette propriété capture les détails de l’étape |
| Scenario_StatusCode  | Code d’état des enregistrements de propriétés du scénario selon la réussite ou l’échec |

### <a name="properties-sent-with-trace-events"></a>Propriétés envoyées avec les événements de suivi

| Nom de la propriété | Description                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | Contient la chaîne d’erreur et des détails sur les raisons pour lesquelles une défaillance s’est produite |

## <a name="property-lists-for-oneplayer-events"></a>Listes de propriétés pour les événements OnePlayer

### <a name="1-properties-sent-with-all-oneplayer-events"></a>1. Propriétés envoyées avec tous les événements OnePlayer
##### <a name="11-standard-properties"></a>1.1 Propriétés standard
| Nom de la propriété | Description                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| eventType | Type d’événement (AppLogic, ErrorAlert, Performance, UserAction) |
| accountType   | Type de compte d’utilisateur (par exemple, entreprise) |
| composant     | OnePlayer |
| language      | Paramètres régionaux/langue de l’application |
| platform      | Plateforme de OnePlayer (iOS/Android) |
| tenantId      | ID du locataire|
| version       | Version de OnePlayer utilisée |
| aadUserId     | ID de l’utilisateur |                                

##### <a name="12-player-properties"></a>1.2 Propriétés du joueur
| Nom de la propriété | Description                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| engineName    | Nom du lecteur sous-jacent (AVFoundation pour iOS/ExoPlayer pour Android) |
| engineVersion | Version du système d’exploitation. |
| loadMode      | Mode de chargement du lecteur |
| playbackSessionId | ID de session pour la lecture |

##### <a name="13-host-properties"></a>1.3 Propriétés de l’hôte 
| Nom de la propriété | Description                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| hostIntegrationType | Type d’intégration de l’hôte (par exemple, Package, OneUp) |
| hostPlatform  | Plateforme pour l’application hôte |
| hostProperties| Propriétés de l’hôte, le cas échéant (iOS uniquement) |
| hostApp       | Nom de l’application hôte |
| hostVersion   | Version de l’application hôte |

##### <a name="14-experimentation-properties"></a>1.4 Propriétés d’expérimentation
| Nom de la propriété | Description                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| ring          | Ring auxquel appartient l’utilisateur. |
| hostSettings  | Attributs définis par l’application hôte (moreOptionsEnabled, shareFeatureEnabled, playbackQualityFeatureEnabled, playbackSpeedFeatureEnabled) |
| flightFilters | Description |
| flightsOverridden | Bool pour les vols remplacés ou non |

##### <a name="15-service-properties"></a>1.5 Propriétés du service
| Nom de la propriété | Description                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| contentType   | Type de contenu servi |
| source   | Nom d’un environnement  |
| mediaService  | Quel service multimédia est utilisé (SPO, ODB, ODC, IC3-AMS, Inconnu) |
| mediaType     | Type du média lu  |
| playbackTech  | Technologie de lecture du média  |
| correlationId | ID de corrélation pour le média, le cas échéant |

### <a name="2-properties-sent-with-all-oneplayer-user-action-events"></a>2. Propriétés envoyées avec les événements d’action utilisateur OnePlayer 
| Nom de la propriété | Description                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| actionType    | Type d’action en cours d’exécution, comme appuyer, faire glisser et faire glisser (iOS uniquement)|
| isIntentional | Valeur booléenne si l’action est intentionnelle ou non (iOS uniquement) |

#### <a name="21-properties-sent-with-changeplaybackquality-event"></a>2.1 Propriétés envoyées avec l’événement changePlaybackQuality
| Nom de la propriété | Description                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| currentPlaybackQuality | qualité de lecture actuelle |

#### <a name="22-properties-sent-with-changeplaybackspeed-event"></a>2.2 Propriétés envoyées avec l’événement ChangePlaybackSpeed
| Nom de la propriété | Description |
|---------------|------------------------------------------------------------------------------------------------|
| previousPlaybackRate  | Taux de lecture précédent de la vidéo (iOS uniquement) |
| currentPlaybackRate   | Taux de lecture actuel de la vidéo |

#### <a name="23-properties-sent-with-playerseek-event-ios-only"></a>2.3 Propriétés envoyées avec l’événement PlayerSeek (iOS uniquement)
| Nom de la propriété | Description |
|---------------|------------------------------------------------------------------------------------------------|
| seekSource    | Source de la recherche (seekbar, forwardButton, backwardButton) |
| seekValue     | Rechercher une position |

### <a name="3-properties-sent-with-oneplayer-heartbeat-event"></a>3. Propriétés envoyées avec l’événement de pulsation OnePlayer
| Nom de la propriété | Description |
|---------------|------------------------------------------------------------------------------------------------|
| mediaCurrentTime | Heure de lecture actuelle du média (iOS uniquement)|
| isLoaded | Est-ce que le média est chargé |
| loadTimeMs | Temps de chargement en millisecondes |
| numberOfStalls | Nombre de blocages pendant la lecture (iOS uniquement) |
| bufferingCount | Nombre de blocages pendant la lecture (Android uniquement) |
| observedBitrate | Taux de bits observé pendant la lecture (iOS uniquement) |
| avgBitrateBitsPerSecond | Taux de bits observé pendant la lecture (Android uniquement) |
| playedSeconds | Lecture en secondes jusqu’à l’événement |
| rebufferingSeconds | Rebuffer des secondes pendant la lecture |
| timeSinceSourceSetMs | Durée depuis laquelle la source a été définie (ms) |
| triggerType | Type de déclencheur (mise en mémoire tampon, erreur, errorLog, canPlayThrough, intervalBeat, jeu de sources, déchargement) |
| errorId | ID d’erreur de l’erreur, le cas échéant |
| errorCorrelationId | ID de corrélation d’erreur pour l’erreur, le cas échéant |
| errorLog | Journal des erreurs pour l’erreur, le cas échéant |
| errorType | Type d’erreur pour l’erreur, le cas échéant |
| errorMessage | Message d’erreur pour l’erreur, le cas échéant |
| errorStack | Informations d’erreur étendues pour l’erreur, le cas échéant |
| metaUrl | URL de méta pour le média |
| odspDocId | ID de document ODSP pour le média |
| siteId | ID de site pour le média |
| teamsCallId | ID d’appel Teams pour le média, le cas échéant |
