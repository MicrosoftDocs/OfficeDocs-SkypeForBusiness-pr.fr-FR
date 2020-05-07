---
title: Gérer les stratégies de réunion
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Apprenez à gérer les paramètres de stratégie de réunion dans teams et à les utiliser pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par les utilisateurs.
ms.openlocfilehash: 4a61d2563a63d2dc8d1b55bbf0bbc6c52230d900
ms.sourcegitcommit: c3f44fccdbd9178d30b52bb0db6f6d31a6dd174b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139208"
---
# <a name="manage-meeting-policies-in-teams"></a>Gérer les stratégies de réunion dans teams

::: zone target="docs"
Stratégies de réunion: elles sont utilisées pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par des utilisateurs au sein de votre organisation. Après avoir créé une stratégie et effectué vos modifications, vous pouvez affecter des utilisateurs à la stratégie. Vous gérez les stratégies de réunion dans le centre d’administration Microsoft teams ou en utilisant [PowerShell](teams-powershell-overview.md).

Vous pouvez mettre en œuvre des stratégies comme suit, ce qui a un impact sur l’interface de réunion pour les utilisateurs avant le début d’une réunion, pendant une réunion ou après une réunion.

|Type d’implémentation  |Description  |
|---------|---------|
|Par organisateur    |Lorsque vous implémentez une stratégie par organisateur, tous les participants à la réunion héritent de la stratégie de l’organisateur. Par exemple, l' **admission automatique de personnes** est une stratégie par organisateur et détermine si les utilisateurs rejoignent directement la réunion ou s’il attend dans la salle d’attente pour les réunions planifiées par l’utilisateur qui dispose de la stratégie.          |
|Par utilisateur    |Lorsque vous implémentez une stratégie par utilisateur, seule la stratégie par utilisateur s’applique pour limiter certaines fonctionnalités pour les participants de la réunion ou de l’organisateur. Par exemple, **l’autorisation de la fonction « Conférence maintenant » dans les canaux** est une stratégie par utilisateur.     |
|Par organisateur et par utilisateur     |Lorsque vous implémentez une combinaison d’une stratégie par utilisateur et par utilisateur, certaines fonctionnalités sont limitées pour les participants à la réunion en fonction de leur politique et de la stratégie de l’organisateur. Par exemple, **l’autorisation de l’enregistrement Cloud** est une stratégie par utilisateur et par utilisateur. Activez ce paramètre pour autoriser l’organisateur de la réunion et les participants à démarrer et arrêter un enregistrement.

Par défaut, la création d’une stratégie nommée global (au niveau de l’organisation par défaut) est créée. Par défaut, tous les utilisateurs de votre organisation reçoivent la stratégie de réunion globale. Vous pouvez y apporter des modifications ou créer une ou plusieurs stratégies personnalisées et leur affecter des utilisateurs. Les utilisateurs bénéficieront de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. Lorsque vous créez une stratégie personnalisée, vous pouvez autoriser ou empêcher l’accès à certaines fonctionnalités à vos utilisateurs, puis les affecter à un ou plusieurs utilisateurs qui disposeront de ces paramètres.

> [!NOTE]
> Le bouton Détails de la réunion sera disponible si un utilisateur a activé les licences de conférence audio ou si l’utilisateur est autorisé à utiliser la fonction de conférence audio si ce n’est pas le cas, les détails de la réunion ne seront pas disponibles.

## <a name="change-or-create-a-meeting-policy"></a>Modifier ou créer une stratégie de réunion

Pour modifier ou créer une stratégie de réunion, accédez au Centre d’administration Microsoft Teams > **Réunions** > **Stratégies de réunion**. Sélectionnez une stratégie dans la liste ou cliquez sur **Ajouter**. Si vous créez une stratégie, ajoutez un nom et une description. Le nom ne peut pas contenir de caractères spéciaux et ne doit pas dépasser 64 caractères. Choisissez vos paramètres, puis sélectionnez **Enregistrer**.

Par exemple, imaginons que vous avez un grand nombre d’utilisateurs et que vous voulez limiter la quantité de bande passante requise par la réunion. Vous devez créer une stratégie personnalisée nommée « bande passante limitée » et désactiver les paramètres suivants :

Sous ** Audio & vidéo** :
- Désactivez l’option Autoriser l’enregistrement Cloud.
- Désactivez Autoriser la vidéo IP.

Sous **Partage de contenu** :
- Désactiver le mode de partage d’écran.
- Désactivez  Autoriser le tableau blanc.
- Désactivez Autoriser les notes partagées.

Vous pouvez ensuite attribuer la stratégie aux utilisateurs.

> [!NOTE]
> Un utilisateur ne peut être associé qu’à une seule stratégie de réunion à la fois.

## <a name="assign-a-meeting-policy-to-users"></a>Affecter une stratégie de réunion aux utilisateurs

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Sous **Stratégie de réunion**, sélectionnez la stratégie que vous souhaitez attribuer, et puis cliquez sur **Appliquer**.

Pour attribuer une stratégie à plusieurs utilisateurs à la fois, consultez l’article [Modifier en masse les paramètres utilisateur Teams](edit-user-settings-in-bulk.md).

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies de réunion**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

> [!NOTE]
> Vous ne pouvez pas supprimer une stratégie s’il est affecté à des utilisateurs. Vous devez d’abord affecter une stratégie différente à tous les utilisateurs concernés, puis supprimer la stratégie d’origine.

## <a name="meeting-policy-settings"></a>Paramètres de la stratégie de réunion

Lorsque vous sélectionnez une stratégie existante dans la page stratégies de la **réunion** ou cliquez sur **Ajouter** pour ajouter une nouvelle stratégie, vous pouvez configurer les paramètres pour les éléments suivants.

- [Général](#meeting-policy-settings---general)
- [Audio & vidéo](#meeting-policy-settings---audio--video)
- [Partage de contenu](#meeting-policy-settings---content-sharing)
- [Participants & invités](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Paramètres de la stratégie de réunion-général

- [Autoriser la Conférence maintenant dans les canaux](#allow-meet-now-in-channels)
- [Autoriser le complément Outlook](#allow-the-outlook-add-in)
- [Autoriser la planification des réunions de canal](#allow-channel-meeting-scheduling)
- [Autoriser la planification de réunions privées](#allow-scheduling-private-meetings)
- [Autoriser la Conférence maintenant dans les réunions privées](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Autoriser la Conférence maintenant dans les canaux

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si un utilisateur peut démarrer une réunion ad hoc dans un canal d’équipe. Si vous activez cette case à costar, lorsque l’utilisateur publie un message dans un canal d’équipe, il peut cliquer sur **Conférence maintenant** sous la zone de rédaction pour commencer une réunion ad hoc du canal. La valeur par défaut est « True ».

![Capture d’écran montrant l’icône Conférence maintenant sous un message](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>Autoriser le complément Outlook

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les réunions d’équipes peuvent être planifiées dans Outlook (Windows, Mac, Web et mobile).

![Capture d’écran montrant la possibilité de planifier une nouvelle réunion](media/meeting-policies-outlook-add-in.png)

Si vous désactivez cette fonctionnalité, les utilisateurs ne sont pas en mesure de planifier des réunions d’équipes lors de la création d’une réunion dans Outlook. Par exemple, dans Outlook sur Windows, l’option **nouvelle réunion teams** ne s’affiche pas dans le ruban.

### <a name="allow-channel-meeting-scheduling"></a>Autoriser la planification des réunions de canal

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les utilisateurs peuvent planifier une réunion dans un canal d’équipe.  Si vous désactivez cette case à costar, l’option **planifier une réunion** ne sera pas disponible pour l’utilisateur lorsqu’il démarrera une réunion dans un canal d’équipe et l’option **Ajouter un canal** est désactivée pour les utilisateurs dans Teams. La valeur par défaut est « True ».

![Capture d’écran montrant l’option planifier une réunion dans teams](media/meeting-policies-schedule-a-meeting.png)

![Capture d’écran montrant l’option Sélectionner un canal pour la réunion](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Autoriser la planification de réunions privées

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les utilisateurs peuvent planifier des réunions privées dans Teams. Une réunion est privée lorsque celle-ci n’est pas publiée sur un canal d’une équipe.

Remarque : Si vous désactivez l’option **autoriser la planification de réunions privées** et **autoriser la planification**des réunions de canal, les options **Ajouter les participants nécessaires** et **Ajouter un canal** sont désactivées pour les utilisateurs de Microsoft Teams. La valeur par défaut est « True ».

### <a name="allow-meet-now-in-private-meetings"></a>Autoriser la Conférence maintenant dans les réunions privées

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si un utilisateur peut démarrer une réunion privée ad hoc.  La valeur par défaut est « True ».

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Paramètres de la stratégie de réunion-audio & Video

- [Autoriser la transcription](#allow-transcription)
- [Autoriser l’enregistrement Cloud](#allow-cloud-recording)
- [Autoriser la vidéo sur IP](#allow-ip-video)
- [Taux d’échantillonnage du support (Ko)](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>Autoriser la transcription

Il s’agit d’une combinaison d’une stratégie par l’organisateur et par utilisateur. Ce paramètre détermine si les légendes et les fonctionnalités de transcription sont disponibles lors de la lecture des enregistrements de réunion. Si vous désactivez cette fonctionnalité, les options **Rechercher** et **CC** ne seront pas disponibles lors de la lecture de l’enregistrement d’une réunion. Ce paramètre doit être activé pour la personne qui a créé l’enregistrement. 

Notez que la transcription pour les réunions enregistrées est uniquement prise en charge pour les utilisateurs qui disposent de la langue dans teams pour lesquelles l’anglais est lu lors de la réunion.

![Capture d’écran montrant les options de transcription dans une réunion](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Autoriser l’enregistrement Cloud

Il s’agit d’une combinaison d’une stratégie par l’organisateur et par utilisateur. Ce paramètre détermine si les réunions de cet utilisateur peuvent être enregistrées. L’enregistrement peut être démarré par l’organisateur de la réunion ou par un autre participant à la réunion si le paramètre de stratégie est activé pour le participant et s’il s’agit d’un utilisateur authentifié de la même organisation.

Les personnes externes à votre organisation, telles que les utilisateurs fédérés et anonymes, ne peuvent pas démarrer l’enregistrement. Les utilisateurs invités ne peuvent pas démarrer ou arrêter l’enregistrement. 

![Capture d’écran montrant les options d’enregistrement](media/meeting-policies-recording.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser l’enregistrement Cloud |
|---------|---------|---------|
|Daniela | Globale   | False |
|Amanda | Location1MeetingPolicy | Vrai|
|Jean (utilisateur externe) | Non applicable | Non applicable|

Les réunions organisées par Daniela ne peuvent pas être enregistrées et Amanda, qui dispose du paramètre de stratégie activé, ne peut pas enregistrer des réunions organisées par Daniela. Les réunions organisées par Amanda peuvent être enregistrées, mais, Daniela, qui a désactivé le paramètre de stratégie et John qui est un utilisateur externe, ne peuvent pas enregistrer des réunions organisées par Amanda.

Pour en savoir plus sur l’enregistrement d’une réunion dans le Cloud, voir [enregistrement de réunion Cloud teams](cloud-recording.md).

### <a name="allow-ip-video"></a>Autoriser la vidéo sur IP

Il s’agit d’une combinaison d’une stratégie par l’organisateur et par utilisateur. La vidéo est un composant clé pour les réunions. Dans certaines organisations, les administrateurs peuvent souhaiter davantage de contrôle sur les réunions des utilisateurs en vidéo. Ce paramètre détermine si la vidéo peut être activée dans les réunions hébergées par un utilisateur et dans les appels 1:1 et les appels de groupe démarrés par un utilisateur. Réunions organisées par un utilisateur pour lequel cette stratégie est activée, autorisez le partage vidéo pendant la réunion par les participants de la réunion, si la stratégie est également activée pour les participants à la réunion. Les participants à la réunion pour lesquels aucune stratégie n’est affectée (par exemple, des participants anonymes ou fédérés) héritent de la stratégie de l’organisateur de la réunion.

![Capture d’écran montrant une réunion avec les paramètres audio et vidéo](media/meeting-policies-audio-video-settings.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser la vidéo IP |
|---------|---------|---------|
|Daniela   | Globale   | Vrai        |
|Amanda    | Location1MeetingPolicy        | False      |

Les réunions hébergées par Daniela permettre l’activation de la vidéo. Daniela pouvez rejoindre la réunion et activer la vidéo. Amanda ne peut pas activer la vidéo pendant la réunion Daniela, car la politique d’Amanda est définie sur ne pas autoriser la vidéo. Amanda peut voir les vidéos partagées par d’autres participants à la réunion.

Dans les réunions hébergées par Amanda, personne ne peut activer la vidéo, quelle que soit la politique de vidéo qui lui est affectée. Cela signifie que Daniela ne peut pas activer la vidéo dans les réunions Amanda.  

Si Daniela appelle Amanda avec la vidéo, Amanda peut répondre à l’appel avec l’audio uniquement.  Lorsque l’appel est connecté, Amanda peut voir la vidéo de Daniela, mais ne peut pas activer la vidéo. Si Amanda appelle Daniela, Daniela peut répondre à l’appel avec de la vidéo et de l’audio. Lorsque l’appel est connecté, Daniela peut activer ou désactiver sa vidéo, selon les besoins.

### <a name="media-bit-rate-kbs"></a>Taux d’échantillonnage du support (Ko)

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine le taux de bits média pour les transmissions du partage d’application audio, vidéo et vidéo dans les appels et les réunions de l’utilisateur. Il est appliqué à la traversée de l’appel ou de la réunion, en liaison descendante et en liaison descendante multimédia. Ce paramètre vous permet de contrôler plus précisément la bande passante de votre organisation. En fonction des scénarios de réunions requis par les utilisateurs, nous recommandons une bande passante suffisante pour une qualité optimale. La valeur minimale est 30 kbps et la valeur maximale dépend du scénario de la réunion. Pour en savoir plus sur la bande passante minimum recommandée pour des réunions, des appels et des événements en direct de bonne qualité dans Teams, voir [besoins en bande passante](prepare-network.md#bandwidth-requirements).

S’il n’y a pas assez de bande passante pour une réunion, un message s’affiche indiquant une mauvaise qualité du réseau.

Pour les réunions qui ont besoin d’une vidéo de qualité optimale, telle que les réunions du tableau PDG et les événements en direct, nous vous conseillons de définir une bande passante de 10 Mbps. Même si l’expérience maximale est définie, la pile multimédia de teams s’adapte à des conditions de bande passante insuffisantes lorsque certaines conditions réseau sont détectées, en fonction du scénario. 

## <a name="meeting-policy-settings---content-sharing"></a>Paramètres de la stratégie de réunion-partage de contenu

- [Mode de partage d’écran](#screen-sharing-mode)
- [Autoriser un participant à céder ou demander le contrôle](#allow-a-participant-to-give-or-request-control)
- [Autoriser un participant externe à céder ou demander le contrôle](#allow-an-external-participant-to-give-or-request-control)
- [Autoriser le partage PowerPoint](#allow-powerpoint-sharing)
- [Autoriser le tableau blanc](#allow-whiteboard)
- [Autoriser les notes partagées](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>Mode de partage d’écran

Il s’agit d’une combinaison d’une stratégie par l’organisateur et par utilisateur. Ce paramètre détermine si le partage de bureau et/ou de fenêtre est autorisé lors de la réunion de l’utilisateur. Les participants à la réunion pour lesquels aucune stratégie n’est affectée (par exemple, les participants anonymes, invités, B2B et fédéré) héritent de la stratégie de l’organisateur de la réunion.

|Définition de la valeur |Comportement  |
|---------|---------|
|**Tout l’écran**    | Le partage de bureau complet et le partage d’application sont autorisés dans la réunion |
|**Application unique**   | Le partage d’application est autorisé dans la réunion        |
|**Désactivé**     |Le partage d’écran et le partage d’application ont été désactivés dans la réunion.       |

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion |Mode de partage d’écran |
|---------|---------|---------|
|Daniela  | Globale   | Tout l’écran |
|Amanda   | Location1MeetingPolicy  | Désactivé |

Réunions hébergées par Daniela permettre aux participants d’une réunion de partager leur écran entier ou une application spécifique. Si Amanda rejoint la réunion Daniela, Amanda ne peut pas partager son écran ou une application spécifique, car son paramètre de stratégie est désactivé. Dans les réunions hébergées par Amanda, personne ne peut partager son écran ou une application unique, quelle que soit la stratégie du mode de partage d’écran qui leur est affectée. Cela signifie qu’Daniela ne peut pas partager son écran ou une application unique dans les réunions Amanda.  

Pour le moment, les utilisateurs ne peuvent pas lire de vidéo ou partager leur écran dans une réunion teams s’ils utilisent Google Chrome.

### <a name="allow-a-participant-to-give-or-request-control"></a>Autoriser un participant à céder ou demander le contrôle

Il s’agit d’une stratégie par utilisateur. Ce paramètre indique si l’utilisateur peut donner le contrôle du bureau ou de la fenêtre partagés aux autres participants à la réunion. Pour donner le contrôle, pointez sur la partie supérieure de l’écran. 

Si ce paramètre est activé pour l’utilisateur, l’option **donner le contrôle** s’affiche dans la barre supérieure d’une session de partage. 

![Capture d’écran montrant l’option donner le contrôle](media/meeting-policies-give-control.png)

Si les paramètres sont désactivés pour l’utilisateur, l’option **donner le contrôle** n’est pas disponible.

![Capture d’écran montrant que l’option donner le contrôle n’est pas disponible](media/meeting-policies-give-control-not-available.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser les participants à céder ou demander le contrôle |
|---------|---------|---------|
|Daniela   | Globale   | Vrai       |
|Babek    | Location1MeetingPolicy        | False   |

Daniela pouvez donner le contrôle de l’ordinateur ou de la fenêtre partagée à d’autres participants à une réunion organisée par Babek que Babek ne peut pas céder le contrôle à d’autres participants.

Pour utiliser PowerShell afin de contrôler les personnes qui peuvent donner le contrôle ou accepter des demandes de contrôle, utilisez l’applet de commande AllowParticipantGiveRequestControl.

> [!NOTE]
> Pour donner et prendre le contrôle du contenu partagé lors du partage, les deux parties doivent utiliser le client de bureau Teams. Le contrôle n’est pas pris en charge lorsqu'une des parties exécute Teams dans un navigateur. Il s'agit d'une limitation technique que nous nous efforçons de résoudre. 

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Autoriser un participant externe à céder ou demander le contrôle

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si les participants externes d’une réunion peuvent donner le contrôle de leur bureau ou fenêtre partagée aux autres participants à la réunion. Les participants externes aux réunions teams peuvent être classés comme suit :  

- Utilisateur anonyme
- Utilisateurs invités  
- Utilisateur B2B
- Utilisateur fédéré  

Si les utilisateurs fédérés peuvent donner le contrôle à des utilisateurs externes lorsque le partage est contrôlé, le paramètre **autoriser un participant externe à attribuer ou demander un contrôle** au sein de leur organisation.

Pour utiliser PowerShell pour contrôler si les participants externes peuvent donner le contrôle ou accepter des demandes de contrôle, utilisez l’applet de commande AllowExternalParticipantGiveRequestControl.

### <a name="allow-powerpoint-sharing"></a>Autoriser le partage PowerPoint

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si l’utilisateur peut partager des diapositives PowerPoint dans une réunion. Les utilisateurs externes, y compris les utilisateurs anonymes, invités et fédérés, héritent de la stratégie de l’organisateur de la réunion.

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser le partage PowerPoint |
|---------|---------|---------|
|Daniela   | Globale   | Vrai       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda ne peut pas partager des diapositives PowerPoint dans les réunions, même si elle est l’organisateur de la réunion. Daniela peut partager des diapositives PowerPoint, même si la réunion est organisée par Amanda. Amanda peut afficher les diapositives PowerPoint partagées par d’autres participants à la réunion, même si elles ne peuvent pas partager des diapositives PowerPoint.

### <a name="allow-whiteboard"></a>Autoriser le tableau blanc

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si un utilisateur peut partager le tableau blanc dans une réunion. Les utilisateurs externes, y compris les utilisateurs anonymes, B2B et fédérés, héritent de la stratégie de l’organisateur de la réunion. 

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser le tableau blanc|
|---------|---------|---------|
|Daniela   | Globale   | Vrai       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda ne peut pas partager le tableau blanc dans une réunion, même s’il s’agit de l’organisateur de la réunion. Daniela peut partager le tableau blanc même si une réunion est organisée par Amanda.  

### <a name="allow-shared-notes"></a>Autoriser les notes partagées

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si un utilisateur peut créer et partager des notes pendant une réunion. Les utilisateurs externes, y compris les utilisateurs anonymes, B2B et fédérés, héritent de la stratégie de l’organisateur de la réunion. Pour l’instant, l’onglet **notes de réunion** est uniquement pris en charge dans les réunions dont la taille est inférieure à 20 participants.

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser les notes partagées |
|---------|---------|---------|
|Daniela   | Globale   | Vrai       |
|Amanda   | Location1MeetingPolicy | False |

Daniela peut prendre des notes dans les réunions d’Amanda et qu’Amanda ne peut prendre des notes pendant une réunion.

## <a name="meeting-policy-settings---participants--guests"></a>Paramètres de la stratégie de réunion-participants & invités

Ces paramètres contrôlent les participants à la réunion qui attendent dans la salle d’attente avant d’être admis à la réunion et le niveau de participation qui leur est accordé lors d’une réunion.

- [Permettre aux utilisateurs anonymes de démarrer une réunion](#let-anonymous-people-start-a-meeting)
- [Admettre automatiquement des personnes](#automatically-admit-people)
- [Autoriser les utilisateurs rendez-vous à ignorer la salle d’attente](#allow-dial-in-users-to-bypass-the-lobby)
- [Activer les légendes dynamiques](#enable-live-captions)
- [Autoriser la discussion dans les réunions](#allow-chat-in-meetings)

> [!NOTE]
>Les options de participation à une réunion varient en fonction des paramètres de chaque groupe équipes et de la méthode de connexion. Si votre groupe comporte une audioconférence et qu’elle est utilisée pour se connecter, voir [audioconférence dans Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Si ce n’est pas le cas, reportez-vous à la rubrique [participer à une réunion dans teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="let-anonymous-people-start-a-meeting"></a>Permettre aux utilisateurs anonymes de démarrer une réunion

Il s’agit d’une stratégie par organisateur. Ce paramètre détermine si les personnes anonymes, y compris les utilisateurs interentreprises, et les utilisateurs fédérés, peuvent rejoindre la réunion de l’utilisateur sans qu’un utilisateur authentifié de l’organisation n’ait accès à celle-ci. 

![Capture d’écran montrant un message à un utilisateur en attente](media/meeting-policies-anonymous-user-lobby.png)

Vous trouverez ci-dessous le comportement de jointure des personnes anonymes lorsque les utilisateurs authentifiés sont présents dans la réunion.

|Permettre aux utilisateurs anonymes de démarrer une réunion  |Admettre automatiquement des personnes |Comportement de jointure des personnes anonymes |
|---------|---------|---------|
|Vrai    | Tout le monde      | Rejoindre directement         |
|   | Tout le monde dans votre organisation       | Patienter dans la salle d’attente        |
|   | Tout le monde au sein de votre organisation et organisations fédérées       | Patienter dans la salle d’attente         |
|False    | Tout le monde        | Rejoindre directement        |
|   | Tout le monde dans votre organisation     | Patienter dans la salle d’attente        |
|   | Tout le monde au sein de votre organisation et organisations fédérées      | Patienter dans la salle d’attente         |

Vous trouverez ci-dessous le comportement de jointure des personnes anonymes lorsqu’aucun utilisateur authentifié n’est présent à la réunion.

|Permettre aux utilisateurs anonymes de démarrer une réunion |Admettre automatiquement des personnes  |Comportement de jointure des personnes anonymes |
|---------|---------|---------|
|Vrai    | Tout le monde      | Rejoindre directement         |
|   | Tout le monde dans votre organisation       | Patienter dans la salle d’attente        |
|   | Tout le monde au sein de votre organisation et organisations fédérées       | Patienter dans la salle d’attente         |
|False    | Tout le monde        | Patienter dans la salle d’attente. Les utilisateurs sont automatiquement admis lorsque le premier utilisateur authentifié rejoint la réunion.        |
|   | Tout le monde dans votre organisation     |Patienter dans la salle d’attente         |
|   | Tout le monde au sein de votre organisation et organisations fédérées      | Patienter dans la salle d’attente         |

### <a name="automatically-admit-people"></a>Admettre automatiquement des personnes

Il s’agit d’une stratégie par organisateur. Ce paramètre détermine si les personnes rejoignent directement une réunion ou patientent dans la salle d’attente jusqu’à ce qu’elles soient admises par un utilisateur authentifié.

![Capture d’écran montrant une réunion avec un utilisateur dans la salle d’attente](media/meeting-policies-lobby.png)

 Les organisateurs de la réunion peuvent cliquer sur options de la **réunion** dans l’invitation à la réunion pour modifier ce paramètre pour chaque réunion qu’ils planifient.
  
|Définition de la valeur  |Comportement de jointure |
|---------|---------|
|**Tout le monde**   |Tous les participants à la réunion rejoignent directement la réunion sans attendre dans la salle d’attente. Cela inclut les utilisateurs authentifiés, les utilisateurs fédérés, les invités, les utilisateurs anonymes, ainsi que les personnes qui se connectent par téléphone.       |
|**Tout le monde au sein de votre organisation et organisations fédérées**     |Utilisateurs authentifiés au sein de l’organisation, y compris utilisateurs invités et utilisateurs d’organisations fédérées, joignez directement la réunion sans attendre dans la salle d’attente.  Utilisateurs anonymes et utilisateurs qui se connectent par téléphone dans la salle d’attente.   |
|**Tout le monde dans votre organisation**    |Utilisateurs authentifiés au sein de l’organisation, y compris les utilisateurs invités, qui rejoignent directement la réunion sans attendre dans la salle d’attente.  Utilisateurs fédérés, utilisateurs anonymes et utilisateurs qui composent le numéro de téléphone dans la salle d’attente.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Autoriser les utilisateurs rendez-vous à ignorer la salle d’attente

Il s’agit d’une stratégie par organisateur. Ce paramètre détermine si les personnes qui se connectent par téléphone rejoignent directement la réunion ou qu’elles patientent dans la salle d’attente, indépendamment du paramètre d' **admission automatique des personnes** .

Voici le comportement de participation des personnes qui se connectent par téléphone.

|Autoriser les utilisateurs rendez-vous à ignorer la salle d’attente  |Admettre automatiquement des personnes  |Comportement de connexion des personnes qui se connectent |
|---------|---------|---------|
|Vrai    | Tout le monde      | Rejoindre directement         |
|   | Tout le monde dans votre organisation       | Rejoindre directement        |
|   | Tout le monde au sein de votre organisation et organisations fédérées       | Rejoindre directement         |
|False    | Tout le monde        | Rejoindre directement        |
|   | Tout le monde dans votre organisation     |Patienter dans la salle d’attente         |
|   | Tout le monde au sein de votre organisation et organisations fédérées      | Patienter dans la salle d’attente         |


### <a name="enable-live-captions"></a>Activer les légendes dynamiques

Il s’agit d’une stratégie par utilisateur qui s’applique au cours d’une réunion. Ce paramètre détermine si l’option **activer les légendes dynamiques** est disponible pour permettre à l’utilisateur d’activer et de désactiver les légendes dynamiques lors des réunions que l’utilisateur attend.  

![Capture d’écran montrant l’option Activer les légendes dynamiques](media/meeting-policies-live-captions.png)

|Définition de la valeur |Comportement  |
|---------|---------|
|**Désactivé mais l’organisateur peut remplacer**     | Les légendes dynamiques ne sont pas activées automatiquement pour l’utilisateur pendant une réunion. L’utilisateur voit l’option **activer les légendes dynamiques** dans le menu débordement (**...**) pour l’activer. Il s’agit du paramètre par défaut. |
|**Désactivé**     | Les légendes dynamiques sont désactivées pour l’utilisateur pendant une réunion. L’utilisateur ne dispose pas de l’option pour l’activer.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>Autoriser la discussion dans les réunions

Il s’agit d’une stratégie par organisateur. Ce paramètre indique si la conversation de réunion est autorisée lors de la réunion de l’utilisateur.

<a name="bkparticipantsandguests"> </a>

## <a name="related-topics"></a>Sujets associés

[Stratégies de messagerie dans teams](messaging-policies-in-teams.md)
