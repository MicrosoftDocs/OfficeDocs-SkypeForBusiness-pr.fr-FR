---
title: Gérer les stratégies de réunion
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Apprenez à gérer les paramètres de stratégie dans les équipes de réunion.
ms.openlocfilehash: 99458e71ae02eb6307b3f363dbf7e060e1b4ed5b
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036628"
---
# <a name="manage-meeting-policies-in-teams"></a>Gérer les stratégies de la réunion dans les équipes

::: zone target="docs"
Stratégies de réunion sont utilisés pour contrôler les fonctionnalités qui sont disponibles pour les participants à des réunions sont planifiées par les utilisateurs de votre organisation. Une fois que vous créez une stratégie et apportez vos modifications, vous pouvez ensuite affecter les utilisateurs à la stratégie. Gérer les stratégies de la réunion dans le centre d’administration Microsoft Teams ou à [l’aide de PowerShell](teams-powershell-overview.md).

Vous pouvez implémenter des stratégies de la façon suivante, qui affectent l’expérience des utilisateurs avant une réunion démarre, pendant une réunion ou une réunion. 

|Type d’implémentation  |Description  |
|---------|---------|
|Par organisateur    |Lorsque vous implémentez une stratégie par organisateur, tous les participants à la réunion héritent de la stratégie de l’organisateur. Par exemple, **accepter des personnes** est une stratégie par organisateur et les contrôles si les utilisateurs rejoignent la réunion directement ou attendent dans la salle d’attente pour les réunions planifiées par l’utilisateur qui est affecté à la stratégie.          |
|Par utilisateur    |Lorsque vous implémentez une stratégie utilisateur, seulement la stratégie par utilisateur s’applique pour limiter certaines fonctionnalités pour les participants à la bibliothèque multimédia et/ou de la réunion. Par exemple, **Autoriser Conférence maintenant** est une stratégie par utilisateur.     |
|Par organisateur et par utilisateur     |Lorsque vous implémentez une combinaison d’une stratégie par organisateur et par utilisateur, certaines fonctionnalités sont limitées pour participants en fonction de sa stratégie et la stratégie de l’organisateur de la réunion. Par exemple, **dans le nuage autoriser d’enregistrement** est une stratégie par organisateur et par utilisateur. Activez ce paramètre pour autoriser l’organisateur de la réunion et les participants pour démarrer et arrêter un enregistrement. 

Par défaut, une stratégie nommée Global (valeur par défaut à l’échelle de l’organisation) est créée. Tous les utilisateurs de votre organisation recevront cette stratégie de réunion par défaut. Apporter des modifications à cette stratégie ou créer un ou plusieurs des stratégies personnalisées et leur affecter des utilisateurs. Lorsque vous créez une stratégie personnalisée, vous pouvez autoriser ou empêcher certaines fonctionnalités disponibles pour vos utilisateurs et puis l’affecter à un ou plusieurs utilisateurs qui possèdent les paramètres qui leur sont appliquées. 

## <a name="change-or-create-a-meeting-policy"></a>Modifier ou créer une stratégie de réunion

Pour modifier ou créer une stratégie de réunion, accédez à la > de centre d’administration Microsoft Teams **réunions** > **stratégies de la réunion**. Sélectionnez une stratégie dans la liste ou sélectionnez **nouvelle stratégie**. Si vous créez une nouvelle stratégie, ajoutez un nom et une description. Le nom ne peut pas contenir des caractères spéciaux ou être plus de 64 caractères. Choisir les paramètres, puis cliquez sur **Enregistrer**.

Par exemple, vous disposez d’un ensemble d’utilisateurs et que vous souhaitez limiter la quantité de bande passante qui nécessite leur réunion. Vous créez une nouvelle stratégie personnalisée appelée « Bande passante limitée » et désactiver les paramètres suivants :

Sous **Audio & vidéo**:
- Désactiver le nuage d’enregistrement
- Désactiver la vidéo IP Autoriser

Sous **partage de contenu**:
- Désactiver le mode de partage d’écran
- Désactiver le tableau blanc
- Désactiver les notes partagées

Ensuite, attribuez la stratégie aux utilisateurs.

> [!NOTE] 
> Un utilisateur peut être affecté à une stratégie de réunion qu’un seul à la fois. 

## <a name="assign-a-meeting-policy-to-users"></a>Affecter une stratégie de réunion aux utilisateurs

Si vous appliquez la stratégie à un utilisateur, sélectionnez **les utilisateurs** dans le volet de navigation de gauche, puis cliquez sur le nom complet de l’utilisateur. Sur la page de l’utilisateur, en regard de **stratégies attribuées**, sélectionnez **Modifier**. Puis, dans le volet **Modifier les stratégies d’utilisateur** , sous **stratégie de réunion**, sélectionnez la stratégie de réunion à partir de la liste déroulante, puis cliquez sur **Enregistrer**. Vous pouvez également affecter des stratégies à partir de la liste des utilisateurs. Pour ce faire, sélectionnez l’utilisateur en cliquant à gauche du nom complet de l’utilisateur. Sélectionnez **Modifier les paramètres**. Puis, dans le volet **Modifier les paramètres** , sous **stratégie de réunion**, sélectionnez la stratégie dans la liste déroulante, puis cliquez sur **Enregistrer**. 
 
Si vous appliquez une stratégie à plusieurs utilisateurs, sélectionnez des **utilisateurs** dans le volet de navigation de gauche, puis sélectionnez chaque utilisateur en cliquant sur à gauche du nom d’utilisateur et puis cliquez sur **Modifier les paramètres**. Dans le volet **Modifier les paramètres** , sous **stratégie de réunion**, sélectionnez la stratégie dans la liste déroulante, puis cliquez sur **Enregistrer**.
 
Vous pouvez également assigner une stratégie de réunion comme suit pour un ou plusieurs utilisateurs :

1. Accédez au **Centre d’administration de Microsoft équipes** > **réunions** > **stratégies de la réunion**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par un nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.
 
> [!NOTE] 
> Impossible de supprimer une stratégie si les utilisateurs sont qui lui est affectés. Vous devez d’abord attribuer une stratégie différente à tous les utilisateurs concernés, et vous pouvez supprimer la stratégie d’origine.
 
## <a name="meeting-policy-settings"></a>Paramètres de stratégie de réunion

Lorsque vous sélectionnez une stratégie existante dans la page de **stratégies de réunion** ou sélectionnez **nouvelle stratégie** pour ajouter une nouvelle stratégie, vous pouvez configurer les paramètres suivants.

- [Général](#meeting-policy-settings---general)
- [Audio & vidéo](#meeting-policy-settings---audio--video)
- [Partage de contenu](#meeting-policy-settings---content-sharing)
- [Invités & des participants](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Paramètres de stratégie de réunion - général

- [Autoriser la conférence maintenant dans des canaux](#allow-meet-now-in-channels)
- [Autoriser privée Conférence maintenant (bientôt disponible)](#allow-private-meet-now-coming-soon)
- [Autoriser le complément Outlook](#allow-the-outlook-add-in)
- [Autoriser la planification de réunion de canal](#allow-channel-meeting-scheduling)
- [Autoriser la planification de réunions privées](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Autoriser la conférence maintenant dans des canaux

Il s’agit d’une stratégie par utilisateur et s’applique avant une réunion commence. Ce paramètre contrôle si un utilisateur peut démarrer une réunion ad-hoc dans un canal d’équipes. Si vous activez ce, lorsqu’un utilisateur publie un message dans un canal d’équipes, l’utilisateur peut cliquer sur **Conférence maintenant** sous la zone de message pour démarrer une réunion ad hoc dans le canal.

![réunion-stratégies-conférence-now.png](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a>Autoriser privée Conférence maintenant (bientôt disponible)

Il s’agit d’une stratégie par utilisateur et s’applique avant une réunion commence. Ce paramètre contrôle si un utilisateur peut démarrer une réunion ad hoc privée.  

### <a name="allow-the-outlook-add-in"></a>Autoriser le complément Outlook

Il s’agit d’une stratégie par utilisateur et s’applique avant une réunion commence. Ce paramètre contrôle si les réunions d’équipes peuvent être planifiées à partir d’Outlook (Windows, Mac, web et mobile).

![réunion-stratégies-outlook-ajouter-in.png](media/meeting-policies-outlook-add-in.png)

Si vous désactivez cette option, les utilisateurs ne peuvent pas planifier des réunions d’équipes lorsqu’ils créent une nouvelle réunion dans Outlook. Par exemple, dans Outlook sur Windows, l’option **Nouvelle réunion équipes** n’apparaît pas dans le ruban.

### <a name="allow-channel-meeting-scheduling"></a>Autoriser la planification de réunion de canal

Il s’agit d’une stratégie par utilisateur et s’applique avant une réunion commence. Ce paramètre contrôle si les utilisateurs peuvent planifier une réunion dans un canal d’équipes.  Si vous désactivez cette option, l’option de **planifier une réunion** ne sera disponible pour les utilisateurs lorsqu’ils lancer une réunion dans un canal d’équipes et l’option **Sélectionner un canal pour répondre aux** n’est pas disponible à l’utilisateur lorsqu’ils planifient une réunion à partir de réunions dans les équipes.

![réunion planification de stratégies a meeting.png](media/meeting-policies-schedule-a-meeting.png)

![Meeting-Policies-Select-a-Channel-to-Meet-in.png](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Autoriser la planification de réunions privées

Il s’agit d’une stratégie par utilisateur et s’applique avant une réunion commence. Ce paramètre contrôle si les utilisateurs peuvent planifier les réunions privées dans les équipes. Une réunion est privée lorsqu’il n’est pas publié à une chaîne dans une équipe.

Notez que si vous désactivez **Autoriser la planification de réunions privées** et **planifier des réunions autoriser canal**, l’option **Organiser une réunion** ne sera pas disponible et les utilisateurs ne pourront pas planifier des réunions dans les équipes.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Paramètres de stratégie de réunion - & Audio vidéo

- [Autoriser la transcription](#allow-transcription)
- [Autoriser le nuage d’enregistrement](#allow-cloud-recording)
- [Autoriser la vidéo IP](#allow-ip-video)
- [Vitesse de transmission multimédia (Kbits/s)](#media-bit-rate-kbs)
- [Activer les légendes live (bientôt disponible)](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a>Autoriser la transcription

Il s’agit d’une combinaison d’une stratégie par organisateur et par utilisateur. Ce paramètre contrôle si les légendes et les fonctionnalités de transcription sont disponibles lors de la lecture des enregistrements de réunions. Si vous désactivez cette option, les options de **recherche** et **CC** ne sont pas disponibles pendant la lecture d’un enregistrement de la réunion. La personne qui a initié l’enregistrement a besoin de ce paramètre est activé afin que l’enregistrement comprend également une transcription. 

Notez que la transcription pour les réunions enregistrées est actuellement uniquement pris en charge pour les utilisateurs disposant de la langue dans les équipes configurés pour l’anglais et lorsque l’anglais est lu de la réunion.

![réunion-stratégies-transcription.png](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Autoriser le nuage d’enregistrement

Il s’agit d’une combinaison d’une stratégie par organisateur et par utilisateur. Ce paramètre contrôle si les réunions de cet utilisateur peuvent être enregistrées. L’enregistrement peut être démarré par l’organisateur de la réunion ou par un autre participant à la réunion si le paramètre de stratégie est activé pour le participant et s’ils sont un utilisateur authentifié à partir de la même organisation.

Personnes extérieures à votre organisation, tels que les utilisateurs fédérés et anonymes, Impossible de démarrer l’enregistrement. Les utilisateurs invités ne peut pas démarrer ou arrêter l’enregistrement. 

![réunion-stratégies-recording.png](media/meeting-policies-recording.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser le nuage d’enregistrement |
|---------|---------|---------|
|Daniela | Globale   | False |
|Amanda | Location1MeetingPolicy | True|
|John (utilisateurs externes) | Non applicable | Non applicable|

Réunions organisées par Daniela ne peuvent pas être enregistrées et Amanda, qui a activé le paramètre de stratégie, ne peut pas enregistrer les réunions organisées par Daniela. Réunions organisées par Amanda peuvent être enregistrées, toutefois, Daniela, ce qui a désactivé le paramètre de stratégie et John qui est un utilisateur externe, ne peut pas enregistrer les réunions organisées par Amanda.

Pour en savoir plus sur l’enregistrement de la réunion dans le nuage, voir [équipes cloud d’enregistrement de la réunion](cloud-recording.md).

### <a name="allow-ip-video"></a>Autoriser la vidéo IP

Il s’agit d’une combinaison d’une stratégie par organisateur et par utilisateur. Vidéo est un composant essentiel de réunions. Dans certaines organisations, les administrateurs souhaiterez davantage de contrôle sur les réunions quels utilisateurs ont vidéo. Ce paramètre contrôle si la vidéo peut être activée dans les réunions hébergées par un utilisateur et 1:1 des appels et groupe lancé par un utilisateur. Réunions organisées par un utilisateur ayant cette stratégie est activée, autoriser le partage de vidéos de la réunion par les participants à la réunion, si les participants à la réunion ont également la stratégie activée. Participants à la réunion qui n’ont pas toutes les stratégies affectées (par exemple, les participants anonymes et fédérés) héritent de la stratégie de l’organisateur de la réunion.

![réunion-stratégies-audio-vidéo-settings.png](media/meeting-policies-audio-video-settings.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser la vidéo IP |
|---------|---------|---------|
|Daniela   | Globale   | True        |
|Amanda    | Location1MeetingPolicy        | False      |

Réunions hébergées par Daniela autorise la vidéos est activé. Daniela peut participer à la réunion et activer la vidéo. Amanda ne peut pas activer la vidéo dans Daniela réunion car la stratégie Amanda est définie à ne pas autoriser la vidéo. Amanda peut voir partagés par d’autres participants à la réunion.

Dans les réunions hébergées par Amanda, aucun participant ne peut activer vidéo, quelle que soit la stratégie vidéo affectée. Cela signifie que Daniela ne peut pas activer la vidéo dans les réunions Amanda.  

Si Daniela appelle Amanda avec vidéo sur, Amanda peut répondre à l’appel audio uniquement.  Lorsque l’appel est connecté, Amanda vidéo de Daniela, mais ne peuvent pas activer vidéo. Si Amanda appelle Daniela, Daniela peut répondre à l’appel avec audio et vidéo. Lorsque l’appel est connecté, Daniela peut activer ou désactiver son vidéo, selon vos besoins.

### <a name="media-bit-rate-kbs"></a>Vitesse de transmission multimédia (Kbits/s)

Il s’agit d’une stratégie par organisateur. Ce paramètre détermine la vitesse de transmission multimédia pour application audio, vidéo et vidéo, partage des transmissions dans des appels et des réunions pour l’utilisateur. Elle est appliquée à la liaison et la liaison descendante traversée du contenu multimédia pour les utilisateurs dans l’appel ou la réunion. Ce paramètre vous permet de contrôler la gestion de bande passante de votre organisation. Selon les scénarios de réunions requises par les utilisateurs, il est recommandé d’avoir suffisamment de bande passante en place pour une expérience de bonne qualité. La valeur minimale est de 30 Kbits/s et le scénario de réunion dépend de la valeur maximale. Pour en savoir plus sur la configuration minimale recommandée pour les réunions de bonne qualité, les appels et les événements en temps réel dans les équipes de bande passante, voir les [besoins en bande passante](prepare-network.md#bandwidth-requirements).

Si il n’est pas suffisamment de bande passante pour une réunion, les participants voient un message qui indique la mauvaise qualité réseau.

Pour les réunions nécessitant la plus haute qualité vidéo, tel que directeur général de la carte réunions et des événements en direct équipes, nous vous recommandons de définir la bande passante à 10 Mbits/s. Même lorsque l’expérience maximale est définie, la pile de médias équipes s’adapte aux conditions de faible bande passante lorsque certaines conditions de réseau sont détectées, en fonction du scénario. 

### <a name="enable-live-captions-coming-soon"></a>Activer les légendes live (bientôt disponible)

Ceci est une stratégie par utilisateur et s’applique pendant une réunion. Si ce paramètre est activé, l’utilisateur voit une option pour afficher les légendes pendant une réunion.

<a name="bkcontentsharing"> </a>

## <a name="meeting-policy-settings---content-sharing"></a>Paramètres de stratégie de réunion - partage de contenu

- [Mode de partage d’écran](#screen-sharing-mode)
- [Autoriser un participant à faire ou demander le contrôle](#allow-a-participant-to-give-or-request-control)
- [Autoriser un participant externe à faire ou demander le contrôle](#allow-an-external-participant-to-give-or-request-control)
- [Autoriser le partage de PowerPoint](#allow-powerpoint-sharing)
- [Autoriser le tableau blanc](#allow-whiteboard)
- [Autoriser les notes partagées](#allow-shared-notes)
- [Autoriser la conversation dans les réunions (bientôt disponible)](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a>Mode de partage d’écran

Il s’agit d’une combinaison d’une stratégie par organisateur et par utilisateur. Ce paramètre détermine si la bureau et/ou la fenêtre de partage est autorisé dans une réunion de l’utilisateur. Les participants qui n’ont pas toutes les stratégies affectées (par exemple, anonyme, invité, B2B et les participants fédérés) héritent de la stratégie de l’organisateur de la réunion.

|Valeur de paramètre |Comportement  |
|---------|---------|
|**Totalité de l’écran**    | Partage de bureau complet et le partage d’application est autorisé à la réunion |
|**Application unique**   | Partage d’application est autorisé à la réunion        |
|**Désactivé**     |Partage d’écran et le partage d’application désactivé dans la réunion.       |

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion |Mode de partage d’écran |
|---------|---------|---------|
|Daniela  | Globale   | Totalité de l’écran |
|Amanda   | Location1MeetingPolicy  | Désactivé |

Réunions hébergées par Daniela autoriser les participants à la réunion à partager leur écran entier ou une application spécifique. Si Amanda rejoint la réunion de Daniela, Amanda ne peuvent pas partager son écran ou une application spécifique comme son paramètre de stratégie est désactivé. Dans les réunions hébergées par Amanda, n’est autorisé à partager leur écran ou une application unique, quelle que soit la stratégie de mode affectée de partage d’écran. Cela signifie que Daniela ne peuvent pas partager son écran ou une seule application dans les réunions Amanda.  

Actuellement, les utilisateurs ne peuvent pas lire la vidéos ou partager leur écran à une réunion équipes s’il utilise Google Chrome.

### <a name="allow-a-participant-to-give-or-request-control"></a>Autoriser un participant à faire ou demander le contrôle

Il s’agit d’une stratégie par utilisateur. Ce paramètre contrôle si l’utilisateur peut donner le contrôle de la fenêtre ou un bureau partagé aux autres participants. Pour donner le contrôle, pointez sur la partie supérieure de l’écran. 

Si ce paramètre est activé pour l’utilisateur, l’option de **Donner le contrôle** s’affiche dans la barre supérieure dans une session de partage. 

![réunion-stratégies-donnent-control.png](media/meeting-policies-give-control.png)

Si les paramètres est désactivé pour l’utilisateur, l’option de **Donner le contrôle** n’est pas disponible.

![Meeting-Policies-GIVE-Control-not-available.png](media/meeting-policies-give-control-not-available.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser les participants à faire ou demander le contrôle |
|---------|---------|---------|
|Daniela   | Globale   | True       |
|Babek    | Location1MeetingPolicy        | False   |

Daniela peut donner le contrôle de la fenêtre ou un bureau partagé par les autres participants à une réunion organisée par Babek, tandis que Babek ne peut pas donner le contrôle à d’autres participants.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Autoriser un participant externe à faire ou demander le contrôle

Il s’agit d’une stratégie par utilisateur. Ce paramètre contrôle si les participants externes à une réunion peuvent donner le contrôle de leur bureau partagé ou la fenêtre aux autres participants à la réunion. Les participants externes dans les réunions des équipes peuvent être classées comme suit :  

   - Utilisateur anonyme
   - Utilisateurs invités  
   - Utilisateur B2B
   - Utilisateur fédéré  

Indique si les utilisateurs fédérés peuvent donner le contrôle à des utilisateurs externes lors du partage est contrôlé par le paramètre **Autoriser un participant externe à faire ou demander le contrôle** de leur organisation.

### <a name="allow-powerpoint-sharing"></a>Autoriser le partage de PowerPoint

Il s’agit d’une stratégie par utilisateur. Ce paramètre contrôle si les utilisateurs peuvent partager des diapositives PowerPoint dans une réunion. Les utilisateurs externes, y compris les utilisateurs anonymes et fédérés invités, héritent de la stratégie de l’organisateur de la réunion.

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser le partage de PowerPoint |
|---------|---------|---------|
|Daniela   | Globale   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda ne peuvent pas partager des diapositives PowerPoint dans les réunions même si elle est l’organisateur de la réunion. Daniela peuvent partager des diapositives PowerPoint même si la réunion est organisée par Amanda. Amanda peut afficher les diapositives PowerPoint partagées par d’autres personnes à la réunion, même si elle ne peuvent pas partager des diapositives PowerPoint.

### <a name="allow-whiteboard"></a>Autoriser le tableau blanc

Il s’agit d’une stratégie par utilisateur. Ce paramètre contrôle si un utilisateur peut partager le tableau blanc dans une réunion. Les utilisateurs externes, y compris anonyme, B2B et les utilisateurs fédérés, héritent de la stratégie de l’organisateur de la réunion. 

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser le tableau blanc|
|---------|---------|---------|
|Daniela   | Globale   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda ne peuvent pas partager le tableau blanc dans une réunion même si elle est l’organisateur de la réunion. Daniela peuvent partager le tableau blanc même si une réunion est organisée par Amanda.  

### <a name="allow-shared-notes"></a>Autoriser les notes partagées

Il s’agit d’une stratégie par utilisateur. Ce paramètre contrôle si un utilisateur peut créer et partager des notes dans une réunion. Les utilisateurs externes, y compris anonyme, B2B et les utilisateurs fédérés, héritent de la stratégie de l’organisateur de la réunion. L’onglet **Notes de réunion** est uniquement pris en charge dans réunions ayant moins de 20 participants. 

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser les notes partagées |
|---------|---------|---------|
|Daniela   | Globale   | True       |
|Amanda   | Location1MeetingPolicy | False |

Daniela peut prendre des notes dans les réunions Amanda et Amanda ne peut pas prendre des notes dans toutes les réunions.

### <a name="allow-chat-in-meetings-coming-soon"></a>Autoriser la conversation dans les réunions (bientôt disponible)

Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle si conversation de la réunion est autorisée dans une réunion de l’utilisateur. 

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---participants--guests"></a>Paramètres de stratégie de réunion - invités & de Participants

Ces paramètres déterminent qui attendent des participants à la réunion dans la salle d’attente avant qu’ils sont admis à la réunion et le niveau de participation, ils sont autorisés dans une réunion.

- [Accepter automatiquement des personnes](#automatically-admit-people)
- [Autoriser les utilisateurs anonymes démarrer une réunion](#allow-anonymous-people-to-start-a-meeting)
- [Autoriser les utilisateurs rendez-vous à la salle d’attente](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [Permettre aux organisateurs de remplacer les paramètres de la salle d’attente](#allow-organizers-to-override-lobby-settings-coming-soon)

### <a name="automatically-admit-people"></a>Accepter automatiquement des personnes

Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle si les personnes à participer à une réunion directement ou attendre dans la salle d’attente jusqu'à ce qu’ils sont admis par un utilisateur authentifié.

![réunion-stratégies-lobby.png](media/meeting-policies-lobby.png)

 Organisateurs de réunions peuvent cliquez sur **Options de la réunion** dans l’invitation à modifier ce paramètre pour chaque réunion qu’ils planifient. **(bientôt disponible)**
  
|Valeur de paramètre  |Rejoindre le comportement |
|---------|---------|
|**Tout le monde**   |Tous les participants rejoignent la réunion sans attendre dans la salle d’attente. Cela inclut les utilisateurs authentifiés, les utilisateurs fédérés, invités, les utilisateurs anonymes et les personnes qui se connectent par téléphone.       |
|**Tout le monde dans votre organisation et les organisations fédérées**     |Les utilisateurs authentifiés de l’organisation, y compris les utilisateurs invités et les utilisateurs d’une organisation fédérée, joindre la réunion sans attendre dans la salle d’attente.  Les utilisateurs anonymes et les utilisateurs qui se connectent par téléphone attendent dans la salle d’attente.   |
|**Tout le monde dans votre organisation**    |Les utilisateurs authentifiés à partir de l’organisation, y compris les utilisateurs invités, joindre la réunion sans attendre dans la salle d’attente.  Les utilisateurs fédérés, les utilisateurs anonymes et les utilisateurs qui se connectent par téléphone attendent dans la salle d’attente.           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a>Autoriser les utilisateurs anonymes démarrer une réunion

Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle si des utilisateurs anonymes, y compris B2B et les utilisateurs fédérés, peuvent rejoindre réunion de l’utilisateur sans qu’un utilisateur authentifié à partir de l’organisation des participants. 

![réunion-stratégies-anonyme-utilisateur-lobby.png](media/meeting-policies-anonymous-user-lobby.png)

Voici le comportement de participer à des utilisateurs anonymes lorsque les utilisateurs authentifiés sont présentes dans la réunion.

|Autoriser les utilisateurs anonymes démarrer une réunion  |Accepter automatiquement des personnes |Rejoindre le comportement des utilisateurs anonymes |
|---------|---------|---------|
|True    | Tout le monde      | Joindre directement         |
|   | Tout le monde dans votre organisation       | Patienter dans la salle d’attente        |
|   | Tout le monde dans votre organisation et les organisations fédérées       | Patienter dans la salle d’attente         |
|False    | Tout le monde        | Joindre directement        |
|   | Tout le monde dans votre organisation     | Patienter dans la salle d’attente        |
|   | Tout le monde dans votre organisation et les organisations fédérées      | Patienter dans la salle d’attente         |

Voici le comportement de participer à des utilisateurs anonymes lorsque les utilisateurs non authentifiés sont présentes dans la réunion.

|Autoriser les utilisateurs anonymes démarrer une réunion |Accepter automatiquement des personnes  |Rejoindre le comportement des utilisateurs anonymes |
|---------|---------|---------|
|True    | Tout le monde      | Joindre directement         |
|   | Tout le monde dans votre organisation       | Patienter dans la salle d’attente        |
|   | Tout le monde dans votre organisation et les organisations fédérées       | Patienter dans la salle d’attente         |
|False    | Tout le monde        | Patienter dans la salle d’attente. Les utilisateurs sont admis automatiquement lorsque le premier utilisateur authentifié rejoint la réunion.        |
|   | Tout le monde dans votre organisation     |Patienter dans la salle d’attente         |
|   | Tout le monde dans votre organisation et les organisations fédérées      | Patienter dans la salle d’attente         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a>Autoriser les utilisateurs rendez-vous à la salle d’attente (bientôt disponible)

Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle si les personnes qui se connectent par téléphone joindre la réunion directement ou attendent dans la salle d’attente, quel que soit le paramétrage **d’accepter des personnes** .

Voici le comportement de participer à des personnes qui se connectent par téléphone.

|Autoriser les utilisateurs rendez-vous à la salle d’attente  |Accepter automatiquement les utilisateurs  |Rejoindre le comportement des personnes qui se connectent |
|---------|---------|---------|
|True    | Tout le monde      | Joindre directement         |
|   | Tout le monde dans votre organisation       | Joindre directement        |
|   | Tout le monde dans votre organisation et les organisations fédérées       | Joindre directement         |
|False    | Tout le monde        | Joindre directement        |
|   | Tout le monde dans votre organisation     |Patienter dans la salle d’attente         |
|   | Tout le monde dans votre organisation et les organisations fédérées      | Patienter dans la salle d’attente         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a>Permettre aux organisateurs de remplacer les paramètres de salle d’attente (bientôt disponible)

Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle si l’organisateur de la réunion peut remplacer les paramètres de salle d’attente qu’un administrateur défini dans **accepter des personnes** et **permettre aux utilisateurs rendez-vous à la salle d’attente** lorsqu’ils planifient une nouvelle réunion. 

Organisateurs de réunions peuvent cliquez sur **Options de la réunion** dans l’invitation à modifier les paramètres de salle d’attente pour chaque réunion qu’ils planifient. 

Voici impact de ce paramètre si l’organisateur de la réunion peut modifier le paramètre **accepter des personnes** pour chaque les planifications de l’organisateur de la réunion.

|Permettre aux organisateurs de remplacer les paramètres de la salle d’attente  |Accepter automatiquement des personnes  |Comportement |
|---------|---------|---------|
|True    | Tout le monde      | Organisateur peut modifier le paramètre pour toute autre valeur. |
|   | Tout le monde dans votre organisation       | Organisateur peut modifier le paramètre pour toute autre valeur.|
|   | Tout le monde dans votre organisation et les organisations fédérées       | Organisateur de la possibilité de le modifier à une autre valeur.         |
|False    | Tout le monde        | Organisateur peut modifier le paramètre pour toute autre valeur.|
|   | Tout le monde dans votre organisation     |Organisateur peut modifier le paramètre pour **tout le monde dans votre organisation**. |
|   | Tout le monde dans votre organisation et les organisations fédérées      | Organisateur ne peut pas substituer le paramètre de la salle d’attente. |

Voici comment ce paramètre affecte si l’organisateur de la réunion peut modifier le paramètre **Autoriser rendez-vous aux utilisateurs de la salle d’attente** pour chaque les planifications de l’organisateur de la réunion.
    
|Permettre aux organisateurs de remplacer les paramètres de la salle d’attente  |Autoriser les utilisateurs rendez-vous à la salle d’attente  |Comportement |
|---------|---------|---------|
|True    |  True        | Organisateur peut modifier le paramètre sur False.       |
|True      | False         | Organisateur peut modifier le paramètre sur True.        |
|False     | True        |Organisateur peut modifier le paramètre sur False.         |
|False      |False          |Organisateur ne peut pas remplacer la valeur de la salle d’attente et ne peut pas demander rendez-vous à la salle d’attente de la réunion.        |

[Article complet](meeting-policies-in-teams.md)

## <a name="related-topics"></a>Voir aussi
[Stratégies de messagerie dans les équipes](messaging-policies-in-teams.md)
