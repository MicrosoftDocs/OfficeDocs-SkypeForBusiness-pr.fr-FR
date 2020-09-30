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
ms.openlocfilehash: c6942a86a8bf63254fb30e59c4a5400f9fa58304
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308416"
---
# <a name="manage-meeting-policies-in-teams"></a>Gérer les stratégies de réunion dans teams

::: zone target="docs"
Stratégies de réunion: elles sont utilisées pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par des utilisateurs au sein de votre organisation. Vous pouvez utiliser la stratégie globale par défaut de l’organisation qui crée ou crée automatiquement des stratégies personnalisées. Vous gérez les stratégies de réunion dans le centre d’administration Microsoft teams ou en utilisant [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Pour plus d’informations sur l’utilisation de rôles pour gérer les autorisations des présentateurs de la réunion et des participants, voir [rôles d’une réunion teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Vous pouvez mettre en œuvre des stratégies comme suit, ce qui a un impact sur l’interface de réunion pour les utilisateurs avant le début d’une réunion, pendant une réunion ou après une réunion.

|Type d’implémentation  |Description  |
|---------|---------|
|Par organisateur    |Lorsque vous implémentez une stratégie par organisateur, tous les participants à la réunion héritent de la stratégie de l’organisateur. Par exemple, l' **admission automatique de personnes** est une stratégie par organisateur et détermine si les utilisateurs rejoignent directement la réunion ou s’il attend dans la salle d’attente pour les réunions planifiées par l’utilisateur qui dispose de la stratégie.          |
|Par utilisateur    |Lorsque vous implémentez une stratégie par utilisateur, seule la stratégie par utilisateur s’applique pour limiter certaines fonctionnalités pour les participants de la réunion ou de l’organisateur. Par exemple, **l’autorisation de la fonction « Conférence maintenant » dans les canaux** est une stratégie par utilisateur.     |
|Par organisateur et par utilisateur     |Lorsque vous implémentez une combinaison d’une stratégie par utilisateur et par utilisateur, certaines fonctionnalités sont limitées pour les participants à la réunion en fonction de leur politique et de la stratégie de l’organisateur. Par exemple, **l’autorisation de l’enregistrement Cloud** est une stratégie par utilisateur et par utilisateur. Activez ce paramètre pour autoriser l’organisateur de la réunion et les participants à démarrer et arrêter un enregistrement.

Vous pouvez modifier les paramètres de la stratégie globale ou créer et affecter une ou plusieurs stratégies personnalisées. Les utilisateurs bénéficieront de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.

> [!NOTE]
> Le bouton Détails de la réunion sera disponible si un utilisateur a activé les licences de conférence audio ou si l’utilisateur est autorisé à utiliser la fonction de conférence audio si ce n’est pas le cas, les détails de la réunion ne seront pas disponibles.

## <a name="create-a-custom-meeting-policy"></a>Créer une stratégie de réunion personnalisée

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de réunion**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description. Le nom ne peut pas contenir de caractères spéciaux et ne doit pas dépasser 64 caractères.
4. Choisissez les paramètres souhaités.
5. Cliquez sur **Enregistrer**.

Par exemple, imaginons que vous avez un grand nombre d’utilisateurs et que vous voulez limiter la quantité de bande passante requise par la réunion. Vous devez créer une stratégie personnalisée nommée « bande passante limitée » et désactiver les paramètres suivants :

Sous ** Audio & vidéo** :

- Désactivez l’option Autoriser l’enregistrement Cloud.
- Désactivez Autoriser la vidéo IP.

Sous **Partage de contenu** :

- Désactiver le mode de partage d’écran.
- Désactivez  Autoriser le tableau blanc.
- Désactivez Autoriser les notes partagées.

Vous pouvez ensuite attribuer la stratégie aux utilisateurs.

## <a name="edit-a-meeting-policy"></a>Modifier une stratégie de réunion

Vous pouvez modifier la stratégie globale et les stratégies personnalisées que vous créez.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de réunion**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. À partir de cet emplacement, apportez les modifications souhaitées.
4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Un utilisateur ne peut être associé qu’à une seule stratégie de réunion à la fois.

## <a name="assign-a-meeting-policy-to-users"></a>Affecter une stratégie de réunion aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

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

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si un utilisateur peut démarrer une réunion ad hoc dans un canal d’équipe. Si vous activez cette option, les utilisateurs peuvent cliquer sur le bouton **rencontrer** pour démarrer une réunion ad hoc ou planifier une réunion dans le canal. La valeur par défaut est « True ».

[![Capture d’écran montrant l’icône Conférence maintenant sous un message ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

### <a name="allow-the-outlook-add-in"></a>Autoriser le complément Outlook

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les réunions d’équipes peuvent être planifiées dans Outlook (Windows, Mac, Web et mobile).

![Capture d’écran montrant la possibilité de planifier une nouvelle réunion](media/meeting-policies-outlook-add-in.png)

Si vous désactivez cette fonctionnalité, les utilisateurs ne sont pas en mesure de planifier des réunions d’équipes lors de la création d’une réunion dans Outlook. Par exemple, dans Outlook sur Windows, l’option **nouvelle réunion teams** ne s’affiche pas dans le ruban.

### <a name="allow-channel-meeting-scheduling"></a>Autoriser la planification des réunions de canal

Utilisez la stratégie AllowChannelMeetingScheduling existante pour contrôler les types d’événements qui peuvent être créés dans les calendriers d’équipe. Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les utilisateurs peuvent planifier une réunion dans un canal d’équipe. Par défaut, ce paramètre est activé. 

Si cette stratégie est désactivée, les utilisateurs ne seront pas en mesure de créer des réunions de canal. Néanmoins, il est possible de modifier les réunions existantes du canal par l’organisateur de l’événement.

La planification d’une réunion est désactivée.

![Capture d’écran montrant l’option planifier une réunion dans teams](media/schedule-meeting-option.png)

La sélection du canal est désactivée.

[![Capture d’écran montrant l’option calendrier permettant de sélectionner le canal dans lequel vous souhaitez planifier une réunion. ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Dans la page billets de canal, les éléments suivants seront désactivés :

- Bouton **planifier une réunion** dans la zone de rédaction de la réponse au canal.
  ![Capture d’écran montrant l’option calendrier permettant de sélectionner le canal dans lequel vous souhaitez planifier une réunion.](media/schedule-meeting-disabled-in-chat2.png)
  
- Bouton **planifier une réunion** dans l’en-tête de canal.
  ![Capture d’écran montrant l’option calendrier permettant de sélectionner le canal dans lequel vous souhaitez planifier une réunion.](media/schedule-now-in-header.png)

Dans le calendrier de canal :

- Le bouton **Ajouter un nouvel événement** dans l’en-tête du calendrier du canal sera désactivé.
  ![Capture d’écran montrant l’option calendrier permettant de sélectionner le canal dans lequel vous souhaitez planifier une réunion.](media/add-new-event-disabled.png)

- Les utilisateurs ne seront pas en mesure de faire glisser et sélectionner un bloc d’heure sur le calendrier du canal pour créer une réunion à partir du canal.

- Les utilisateurs ne peuvent pas utiliser les raccourcis clavier pour créer une réunion dans le calendrier de canal.

Dans le centre d’administration :

L’application Calendrier de canal s’affiche dans la section **applications Microsoft** du volet d’administration pour les stratégies d’autorisation.

![Capture d’écran montrant la stratégie applications Microsoft dans la console d’administration des équipes.](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a>Autoriser la planification de réunions privées

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les utilisateurs peuvent planifier des réunions privées dans Teams. Une réunion est privée lorsque celle-ci n’est pas publiée sur un canal d’une équipe.

Remarque : Si vous désactivez l’option **autoriser la planification de réunions privées** et **autoriser la planification**des réunions de canal, les options **Ajouter les participants nécessaires** et **Ajouter un canal** sont désactivées pour les utilisateurs de Microsoft Teams. Par défaut, ce paramètre est activé.

### <a name="allow-meet-now-in-private-meetings"></a>Autoriser la Conférence maintenant dans les réunions privées

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si un utilisateur peut démarrer une réunion privée ad hoc.  Par défaut, ce paramètre est activé.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Paramètres de la stratégie de réunion-audio & Video

- [Autoriser la transcription](#allow-transcription)
- [Autoriser l’enregistrement Cloud](#allow-cloud-recording)
- [Mode pour le son IP](#mode-for-ip-audio) 
- [Mode pour la vidéo IP](#mode-for-ip-video) 
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
|Daniela | Globale   | Désactivé |
|Amanda | Location1MeetingPolicy | Activé|
|Jean (utilisateur externe) | Non applicable | Non applicable|

Les réunions organisées par Daniela ne peuvent pas être enregistrées et Amanda, qui dispose du paramètre de stratégie activé, ne peut pas enregistrer des réunions organisées par Daniela. Les réunions organisées par Amanda peuvent être enregistrées, mais, Daniela, qui a désactivé le paramètre de stratégie et John qui est un utilisateur externe, ne peuvent pas enregistrer des réunions organisées par Amanda.

Pour en savoir plus sur l’enregistrement d’une réunion dans le Cloud, voir [enregistrement de réunion Cloud teams](cloud-recording.md).

### <a name="mode-for-ip-audio"></a>Mode pour le son IP

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si l’audio peut être activé dans les réunions et les appels de groupe. Voici les valeurs de ce paramètre.

|Définition de la valeur |Comportement  |
|---------|---------|
|**Audio entrant et sortant activé**    |Le son entrant et sortant est autorisé dans la réunion. Il s’agit du paramètre par défaut. |
|**Désactivé**     |Le son entrant et sortant est désactivé dans la réunion.     |

S’il est défini sur **Disabled** pour un utilisateur, celui-ci peut toujours planifier et organiser des réunions, mais il ne peut pas utiliser le son. Pour participer à une réunion, ils doivent se connecter par le biais du réseau téléphonique public commuté (RTC) ou avoir l’appel de la réunion et les joindre par téléphone. Les participants à la réunion pour lesquels aucune stratégie n’est affectée (par exemple, des participants anonymes) disposent de l’option **audio entrant et sortant activée** par défaut. Sur les clients mobiles Teams, si ce paramètre est désactivé, l’utilisateur doit se connecter à la réunion via PSTN.

Ce paramètre ne s’applique pas aux appels 1:1. Pour limiter les appels 1:1, configurez une [stratégie d’appel](teams-calling-policy.md) d’équipes et désactivez le paramètre **effectuer des appels privés** . Ce paramètre ne s’applique également pas aux appareils de salle de conférence tels que surface Hub et les appareils Microsoft Teams.

Pour en savoir plus, voir [gérer les appels audio et vidéo des participants](#manage-audiovideo-for-meeting-participants)à la réunion.

### <a name="mode-for-ip-video"></a>Mode pour la vidéo IP

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si la vidéo peut être activée dans les réunions et les appels de groupe. Voici les valeurs de ce paramètre.

|Définition de la valeur |Comportement  |
|---------|---------|
|**Vidéo sortante et entrante activée**    | La vidéo sortante et entrante est autorisée dans la réunion. Il s’agit du paramètre par défaut. |
|**Désactivé**     | La vidéo sortante et entrante est désactivée dans la réunion. Sur les clients mobiles Teams, les utilisateurs ne peuvent pas partager des vidéos ou des photos pendant la réunion. <br><br>Notez que si le **mode pour le son IP** est désactivé, le **mode de lecture de la vidéo IP** reste également désactivé.  |

S’il est défini sur **Disabled** pour un utilisateur, celui-ci ne peut pas activer la vidéo ou afficher les vidéos partagées par les autres participants à la réunion. Les participants à la réunion pour lesquels aucune stratégie n’est affectée (par exemple, des participants anonymes) ont configuré ce paramètre sur **sortant et la vidéo entrante est activée** par défaut.

Ce paramètre ne s’applique pas aux appareils de salle de conférence comme les appareils surface Hub et Microsoft Teams.

> [!NOTE]
> Gardez à l’esprit que ce paramètre contrôle la vidéo sortante et entrante, alors que le paramètre **autoriser la vidéo IP** contrôle la vidéo sortante. Pour en savoir plus, voir [le paramètre de stratégie de vidéo IP prioritaire](#which-ip-video-policy-setting-takes-precedence) et gérer les paramètres [audio et vidéo des participants à la réunion](#manage-audiovideo-for-meeting-participants).

### <a name="allow-ip-video"></a>Autoriser la vidéo sur IP

Il s’agit d’une combinaison d’une stratégie par l’organisateur et par utilisateur. La vidéo est un composant clé pour les réunions. Dans certaines organisations, les administrateurs peuvent souhaiter davantage de contrôle sur les réunions des utilisateurs en vidéo. Ce paramètre détermine si la vidéo peut être activée dans les réunions hébergées par un utilisateur et dans 1:1 et les appels de groupe démarrés par un utilisateur. Sur les clients mobiles Teams, ce paramètre détermine si les utilisateurs peuvent partager des photos et des vidéos pendant une réunion. 

Réunions organisées par un utilisateur pour lequel ce paramètre de stratégie est activé, autorisez le partage vidéo pendant la réunion aux participants à la réunion, si le paramètre de stratégie est également activé pour les participants. Les participants à la réunion pour lesquels aucune stratégie n’est affectée (par exemple, des participants anonymes ou fédérés) héritent de la stratégie de l’organisateur de la réunion.

> [!NOTE]
> Gardez à l’esprit que ce paramètre contrôle la vidéo sortante, tandis que le paramètre **vidéo IP** contrôle la vidéo sortante et entrante. Pour en savoir plus, voir [le paramètre de stratégie de vidéo IP prioritaire](#which-ip-video-policy-setting-takes-precedence) et gérer les paramètres [audio et vidéo des participants à la réunion](#manage-audiovideo-for-meeting-participants).

| Bureau et client Web teams |Client mobile teams  |
|:-------:|:-------:|
|![Capture d’écran montrant la participation à une réunion avec les paramètres audio et vidéo sur le Bureau](media/meeting-policies-audio-video-settings.png)    |![Capture d’écran illustrant la participation à une réunion Sreen avec les paramètres audio et vidéo sur un appareil mobile](media/meeting-policies-mobile-join.png)          |


Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser la vidéo sur IP |
|---------|---------|---------|
|Daniela   | Globale   | Activé       |
|Amanda    | Location1MeetingPolicy        | Désactivé      |

Les réunions hébergées par Daniela permettre l’activation de la vidéo. Daniela pouvez rejoindre la réunion et activer la vidéo. Amanda ne peut pas activer la vidéo pendant la réunion Daniela, car la politique d’Amanda est définie sur ne pas autoriser la vidéo. Amanda peut voir les vidéos partagées par d’autres participants à la réunion.

Dans les réunions hébergées par Amanda, personne ne peut activer la vidéo, quelle que soit la politique de vidéo qui lui est affectée. Cela signifie que Daniela ne peut pas activer la vidéo dans les réunions Amanda.  

Si Daniela appelle Amanda avec la vidéo, Amanda peut répondre à l’appel avec l’audio uniquement.  Lorsque l’appel est connecté, Amanda peut voir la vidéo de Daniela, mais ne peut pas activer la vidéo. Si Amanda appelle Daniela, Daniela peut répondre à l’appel avec de la vidéo et de l’audio. Lorsque l’appel est connecté, Daniela peut activer ou désactiver sa vidéo, selon les besoins.

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>Quel est le paramètre de stratégie de vidéo IP prioritaire ?

Pour un utilisateur, le paramètre de stratégie le plus restrictif pour la vidéo est prioritaire. Voici quelques exemples.

|Autoriser la vidéo sur IP|Mode pour la vidéo IP|Découverte des réunions|
|---------|---------|---------|
|Organisateur : **activé**<br><br>Participant : **activé** |Participant : **désactivé**        |Ce **paramètre** est prioritaire. Le participant affecté à cette stratégie ne peut pas activer ou afficher les vidéos partagées par d’autres personnes.|
|Organisateur : **activé**<br><br>Participant : **activé** |Participant : **vidéo sortante et entrante activée**          |Le participant affecté à cette stratégie peut activer ou afficher les vidéos partagées par d’autres personnes.         |
|Organisateur : **activé**<br><br>Participant : **désactivé** |Participant : **vidéo sortante et entrante activée**         |Le paramètre **allow IP Video** est prioritaire. Les participants peuvent uniquement voir la vidéo entrante et ne peut pas envoyer de vidéo sortante.         |
|Organisateur : **activé**<br><br>Participant : **désactivé** |Participant : **désactivé**         |Ce **paramètre** est prioritaire. Le participant ne peut pas voir la vidéo entrante ou sortante.|
|Organisateur : **désactivé**    |       |Le paramètre **allow IP Video** est prioritaire, car il est désactivé pour l’organisateur. Personne ne peut activer la vidéo dans les réunions organisées par l’utilisateur affecté de cette stratégie.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Gérer les éléments audio/vidéo des participants à la réunion

|Si vous souhaitez...  |Définissez les paramètres de stratégie suivants  |
|---------|---------|
|Désactiver l’audio et la vidéo pour les participants aux réunions  |Mode de l’audio IP : **désactivé**<br> Mode pour la vidéo IP : **désactivé**<br>Autoriser la vidéo IP : N/A       |
|Activez uniquement les éléments vidéo et audio entrants pour les participants aux réunions.  |Mode audio IP : **audio sortant et entrant activé**<br> Mode pour la vidéo IP : **vidéo sortante et entrante activée**<br>Autoriser la vidéo IP : **désactivé**       |
|Désactiver la vidéo pour les participants à une réunion (les participants ont uniquement le son)|  Mode de l’audio IP : **activez le son entrant et sortant** .<br> Mode pour la vidéo IP : **désactivé**<br>Autoriser la vidéo IP : N/A        
|Activer l’audio et la vidéo pour les participants aux réunions    |Mode audio IP : **audio entrant et sortant activé** (par défaut)<br> Mode pour la vidéo IP : **vidéo sortante et entrante activée** (par défaut)<br>Autoriser la vidéo IP : **activée** (par défaut)    |

La stratégie la plus restrictive entre la stratégie de l’organisateur de la réunion et la stratégie de l’utilisateur s’applique. Par exemple, si un organisateur dispose d’une stratégie qui limite la vidéo et la stratégie d’un utilisateur ne limite pas la vidéo, les participants à la réunion héritent de la stratégie de l’organisateur de la réunion et n’ont pas accès à la vidéo dans les réunions. Cela signifie qu’ils peuvent rejoindre la réunion à l’aide du son uniquement.

> [!NOTE]
> Lorsqu’un utilisateur entame un appel de groupe pour participer par téléphone, l’écran **utiliser le téléphone pour l’audio** ne s’affiche pas. Il s’agit d’un problème connu que nous nous efforçons de résoudre. Pour contourner ce problème, sélectionnez **audio du téléphone** sous **autres options de jointure**.  

#### <a name="teams-mobile-clients"></a>Clients mobiles teams

Pour les utilisateurs de clients mobiles Teams, la possibilité de partager des photos et des vidéos pendant une réunion est également déterminée par le paramètre **autoriser** le mode vidéo IP ou **IP** . En fonction du paramètre de stratégie prioritaire, la possibilité de partager des vidéos et des photos ne sera pas disponible. Cela n’affecte pas le partage d’écran, que vous configurez à l’aide d’un paramètre différent du [mode de partage d’écran](#screen-sharing-mode) . Par ailleurs, vous pouvez définir une [stratégie de mobilité d’équipes](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) pour empêcher les utilisateurs mobiles d’utiliser la vidéo IP sur une connexion de données cellulaires, ce qui signifie qu’ils doivent utiliser une connexion WiFi.

### <a name="media-bit-rate-kbs"></a>Taux d’échantillonnage du support (Ko)

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine le taux de bits média pour les transmissions du partage d’application audio, vidéo et vidéo dans les appels et les réunions de l’utilisateur. Il est appliqué à la traversée de l’appel ou de la réunion, en liaison descendante et en liaison descendante multimédia. Ce paramètre vous permet de contrôler plus précisément la bande passante de votre organisation. En fonction des scénarios de réunions requis par les utilisateurs, nous recommandons une bande passante suffisante pour une qualité optimale. La valeur minimale est 30 kbps et la valeur maximale dépend du scénario de la réunion. Pour en savoir plus sur la bande passante minimum recommandée pour des réunions, des appels et des événements en direct de bonne qualité dans Teams, voir [besoins en bande passante](prepare-network.md#bandwidth-requirements).

S’il n’y a pas assez de bande passante pour une réunion, un message s’affiche indiquant une mauvaise qualité du réseau.

Pour les réunions qui ont besoin d’une vidéo de qualité supérieure, telle que des réunions de tableau PDG et des événements en direct, nous vous conseillons de définir une bande passante de 10 Mbps. Même si l’expérience maximale est définie, la pile multimédia teams s’adapte à des conditions de bande passante insuffisantes lorsque certaines conditions réseau sont détectées, en fonction du scénario.

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
|Daniela   | Globale   | Activé       |
|Babek    | Location1MeetingPolicy        | Désactivé   |

Daniela pouvez donner le contrôle de l’ordinateur ou de la fenêtre partagée à d’autres participants à une réunion organisée par Babek que Babek ne peut pas céder le contrôle à d’autres participants.

Pour utiliser PowerShell afin de contrôler les personnes qui peuvent donner le contrôle ou accepter des demandes de contrôle, utilisez l’applet de commande AllowParticipantGiveRequestControl.

> [!NOTE]
> Pour donner et prendre le contrôle du contenu partagé lors du partage, les deux parties doivent utiliser le client de bureau Teams. Le contrôle n’est pas pris en charge lorsqu'une des parties exécute Teams dans un navigateur. Il s'agit d'une limitation technique que nous nous efforçons de résoudre.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Autoriser un participant externe à céder ou demander le contrôle

Il s’agit d’une stratégie par utilisateur. La présence d’une organisation pour un utilisateur ne contrôle pas ce qu’il est possible de faire, quels que soient les participants externes qu’il a définis. Ce paramètre détermine si les participants externes peuvent recevoir le contrôle ou demander le contrôle de l’écran du partage, en fonction de ce que le partage a défini dans les stratégies de la réunion de leur organisation. Les participants externes aux réunions teams peuvent être classés comme suit :  

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
|Daniela   | Globale   | Activé       |
|Amanda   | Location1MeetingPolicy        | Désactivé   |

Amanda ne peut pas partager des diapositives PowerPoint dans les réunions, même si elle est l’organisateur de la réunion. Daniela peut partager des diapositives PowerPoint, même si la réunion est organisée par Amanda. Amanda peut afficher les diapositives PowerPoint partagées par d’autres participants à la réunion, même si elles ne peuvent pas partager des diapositives PowerPoint.

### <a name="allow-whiteboard"></a>Autoriser le tableau blanc

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si un utilisateur peut partager le tableau blanc dans une réunion. Les utilisateurs externes, y compris les utilisateurs anonymes, B2B et fédérés, héritent de la stratégie de l’organisateur de la réunion.

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser le tableau blanc|
|---------|---------|---------|
|Daniela   | Globale   | Activé       |
|Amanda   | Location1MeetingPolicy        | Désactivé   |

Amanda ne peut pas partager le tableau blanc dans une réunion, même s’il s’agit de l’organisateur de la réunion. Daniela peut partager le tableau blanc même si une réunion est organisée par Amanda.  

### <a name="allow-shared-notes"></a>Autoriser les notes partagées

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si un utilisateur peut créer et partager des notes pendant une réunion. Les utilisateurs externes, y compris les utilisateurs anonymes, B2B et fédérés, héritent de la stratégie de l’organisateur de la réunion. Pour l’instant, l’onglet **notes de réunion** est uniquement pris en charge dans les réunions ayant moins de 20 participants.

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser les notes partagées |
|---------|---------|---------|
|Daniela   | Globale   | Activé       |
|Amanda   | Location1MeetingPolicy | Désactivé |

Daniela peut prendre des notes dans les réunions d’Amanda et qu’Amanda ne peut prendre des notes pendant une réunion.

## <a name="meeting-policy-settings---participants--guests"></a>Paramètres de la stratégie de réunion-participants & invités

Ces paramètres contrôlent les participants à la réunion qui attendent dans la salle d’attente avant d’être admis à la réunion et le niveau de participation qui leur est accordé lors d’une réunion.

- [Permettre aux utilisateurs anonymes de démarrer une réunion](#let-anonymous-people-start-a-meeting)
- [Admettre automatiquement des personnes](#automatically-admit-people)
- [Autoriser les utilisateurs rendez-vous à ignorer la salle d’attente](#allow-dial-in-users-to-bypass-the-lobby)
- [Activer les légendes dynamiques](#enable-live-captions)
- [Autoriser la discussion dans les réunions](#allow-chat-in-meetings)

> [!NOTE]
>Les options de participation à une réunion varient en fonction des paramètres de chaque groupe équipes et de la méthode de connexion. S’il s’agit d’une audioconférence et de l’utiliser pour se connecter, voir [audioconférence](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Si ce n’est pas le cas, reportez-vous à la rubrique [participer à une réunion dans teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="let-anonymous-people-start-a-meeting"></a>Permettre aux utilisateurs anonymes de démarrer une réunion

Il s’agit d’une stratégie basée sur la Conférence rendez-vous pour les utilisateurs de conférences rendez-vous. Ce paramètre détermine si les utilisateurs d’appels entrants peuvent participer à la réunion sans un utilisateur authentifié de l’organisation. Par défaut, ce paramètre est désactivé, ce qui signifie que les utilisateurs d’appels entrants attendent dans la salle d’attente jusqu’à ce qu’un utilisateur authentifié de l’organisation rejoigne la réunion.

> [!NOTE]
> Si ce paramètre est désactivé et qu’un utilisateur rendez-vous rejoint la réunion tout d’abord et qu’il est placé dans la salle d’attente, l’utilisateur de l’organisation doit participer à la réunion à l’aide d’un client d’équipes pour admettre l’utilisateur dans la salle d’attente. Aucun contrôle de salle d’attente n’est disponible pour les utilisateurs distants.

### <a name="automatically-admit-people"></a>Admettre automatiquement des personnes

Il s’agit d’une stratégie par organisateur. Ce paramètre détermine si les personnes rejoignent directement une réunion ou patientent dans la salle d’attente jusqu’à ce qu’elles soient admises par un utilisateur authentifié. Ce paramètre ne s’applique pas aux utilisateurs d’appels entrants.

![Capture d’écran montrant une réunion avec un utilisateur dans la salle d’attente](media/meeting-policies-lobby.png)

 Les organisateurs de la réunion peuvent cliquer sur options de la **réunion** dans l’invitation à la réunion pour modifier ce paramètre pour chaque réunion qu’ils planifient.

> [!NOTE]
> Dans les options de la réunion, le paramètre est intitulé « qui peut éviter la salle d’attente ». Si vous modifiez le paramètre par défaut d’un utilisateur, celui-ci est appliqué à toutes les nouvelles réunions organisées par cet utilisateur et à toute réunion antérieure dans laquelle l’utilisateur n’a pas modifié les options de la réunion.
  
|Définition de la valeur  |Comportement de jointure |
|---------|---------|
|**Tout le monde**   |Tous les participants à la réunion rejoignent directement la réunion sans attendre dans la salle d’attente. Cela inclut les utilisateurs authentifiés, les utilisateurs externes d’organisations de confiance, les invités et les utilisateurs anonymes.     |
|**Tout le monde au sein de votre organisation et organisations fédérées**     |Utilisateurs authentifiés au sein de l’organisation, y compris utilisateurs invités et utilisateurs d’organisations approuvées, joignez directement la réunion sans attendre dans la salle d’attente.  Les utilisateurs anonymes attendent dans la salle d’attente.   |
|**Tout le monde dans votre organisation**    |Utilisateurs authentifiés au sein de l’organisation, y compris les utilisateurs invités, qui rejoignent directement la réunion sans attendre dans la salle d’attente.  Les utilisateurs d’organisations approuvées et d’utilisateurs anonymes attendent dans la salle d’attente. Il s’agit du paramètre par défaut.           |
|**Organisateur uniquement**    |Seuls les organisateurs de la réunion peuvent rejoindre la réunion directement sans attendre dans la salle d’attente. Tout le monde, y compris les utilisateurs authentifiés au sein de l’organisation, les utilisateurs invités, les utilisateurs d’organisations approuvées et d’utilisateurs anonymes doivent patienter dans la salle d’attente.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Autoriser les utilisateurs rendez-vous à ignorer la salle d’attente

Il s’agit d’une stratégie par organisateur. Ce paramètre détermine si les personnes qui se connectent par téléphone rejoignent directement la réunion ou qu’elles patientent dans la salle d’attente, indépendamment du paramètre d' **admission automatique des personnes** . Par défaut, ce paramètre est désactivé. Lorsque cette option est désactivée, les utilisateurs rendez-vous attendent dans la salle d’attente jusqu’à ce qu’un utilisateur de l’organisation rejoigne la réunion avec un client teams et les autorise. Lorsque ce paramètre est activé, les utilisateurs rendez-vous se connectent automatiquement à la réunion lorsqu’un utilisateur de l’organisation rejoint la réunion.

> [!NOTE]
> Si un utilisateur d’un rendez-vous rejoint une réunion avant qu’un utilisateur de l’organisation ne rejoint la réunion, il est placé dans la salle d’attente jusqu’à ce qu’un utilisateur de l’organisation rejoigne la réunion par le biais d’un client d’équipe et les admet. Si vous modifiez le paramètre par défaut d’un utilisateur, celui-ci est appliqué à toutes les nouvelles réunions organisées par cet utilisateur et à toute réunion antérieure dans laquelle l’utilisateur n’a pas modifié les options de la réunion.

### <a name="enable-live-captions"></a>Activer les légendes dynamiques

Il s’agit d’une stratégie par utilisateur qui s’applique au cours d’une réunion. Ce paramètre détermine si l’option **activer les légendes dynamiques** est disponible pour permettre à l’utilisateur d’activer et de désactiver les légendes dynamiques lors des réunions que l’utilisateur attend.  

![Capture d’écran montrant l’option Activer les légendes dynamiques](media/meeting-policies-live-captions.png)

|Définition de la valeur |Comportement  |
|---------|---------|
|**Désactivé, mais l’utilisateur peut remplacer**     | Les légendes dynamiques ne sont pas activées automatiquement pour l’utilisateur pendant une réunion. L’utilisateur voit l’option **activer les légendes dynamiques** dans le menu débordement (**...**) pour l’activer. Il s’agit du paramètre par défaut. |
|**Désactivé**     | Les légendes dynamiques sont désactivées pour l’utilisateur pendant une réunion. L’utilisateur ne dispose pas de l’option pour l’activer.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>Autoriser la discussion dans les réunions

Il s’agit d’un paramètre par participant. Ce paramètre indique si la conversation de réunion est autorisée lors de la réunion de l’utilisateur.

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>Paramètres de stratégie de réunion-mode de rôle de présentateur désigné

Il s’agit d’une stratégie par utilisateur. Ce paramètre vous permet de changer la valeur par défaut du paramètre **qui peut présenter ?** dans les **options de réunion** du client Teams. Ce paramètre de stratégie affecte toutes les réunions, y compris les réunions Conférence maintenant.

Le paramètre **qui peut présenter ?** permet aux organisateurs de la réunion de choisir qui peut être présentateur dans une réunion. Pour en savoir plus, voir [modifier les paramètres des participants d’une réunion](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) et de rôles d’équipes [dans une réunion teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Pour l’instant, vous pouvez uniquement utiliser PowerShell pour configurer ce paramètre de stratégie. Vous pouvez modifier une stratégie de réunion teams existante à l’aide de l’applet de passe [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez créer une stratégie de réunion teams à l’aide de l’applet [de nouvelle cmdlet New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour spécifier la valeur par défaut du paramètre **qui peut présenter ?** dans Teams, définissez le paramètre **DesignatedPresenterRoleMode** sur l’une des options suivantes :

- **EveryoneUserOverride**: tous les participants à la réunion peuvent être présentateurs. Il s’agit de la valeur par défaut. Ce paramètre correspond au paramètre **tout le monde** dans Teams.
- **EveryoneInCompanyUserOverride**: les utilisateurs authentifiés au sein de l’organisation, y compris les utilisateurs invités, peuvent être présentateurs. Ce paramètre correspond au paramètre **personnes du mon organisation** dans Teams.
- **OrganizerOnlyUserOverride**: seul l’organisateur de la réunion peut être présentateur, et tous les participants à la réunion sont désignés comme participants. Ce paramètre correspond au paramètre **moi uniquement** dans Teams.

Gardez à l’esprit qu’une fois que vous avez défini la valeur par défaut, les organisateurs de la réunion peuvent toujours modifier ce paramètre dans teams et choisir qui peut effectuer une présentation aux réunions planifiées.

## <a name="meeting-policy-settings---meeting-attendance-report"></a>Paramètres de la stratégie de réunion-rapport de participation à une réunion

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si les organisateurs de la réunion peuvent télécharger le [rapport de présence](teams-analytics-and-reports/meeting-attendance-report.md)de la réunion.

Pour l’instant, vous pouvez uniquement utiliser PowerShell pour configurer ce paramètre de stratégie. Vous pouvez modifier une stratégie de réunion teams existante à l’aide de l’applet de passe [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez créer une stratégie de réunion teams à l’aide de l’applet [de nouvelle cmdlet New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour permettre à un organisateur de la réunion de télécharger le rapport de présence de la réunion, définissez le paramètre **AllowEngagementReport** sur **Enabled**. Lorsque l’option est activée, l’option permettant de télécharger le rapport s’affiche dans le volet **participants** .

Pour empêcher un organisateur de la réunion de télécharger le rapport, attribuez au paramètre la valeur **Disabled**. Par défaut, ce paramètre est désactivé et l’option permettant de télécharger le rapport n’est pas disponible.

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>Paramètres de la stratégie de réunion-fournisseur de réunion pour le mode îles

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine quel complément de réunion Outlook est utilisé pour *les utilisateurs en mode îlot*. Vous pouvez spécifier si les utilisateurs peuvent uniquement utiliser le complément de réunion teams ou les compléments de réunion équipes et de réunions Skype entreprise pour planifier des réunions dans Outlook.

Vous pouvez uniquement appliquer cette politique aux utilisateurs qui sont en mode îlot et dont le paramètre **AllowOutlookAddIn** est défini sur **true** dans la stratégie de réunion Teams.

Pour l’instant, vous pouvez uniquement utiliser PowerShell pour définir cette stratégie. Vous pouvez modifier une stratégie de réunion teams existante à l’aide de l’applet de passe [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez créer une stratégie de réunion teams à l’aide de l’applet [de nouvelle cmdlet New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour spécifier le complément de réunion que vous voulez mettre à la disposition des utilisateurs, définissez le paramètre **PreferredMeetingProviderForIslandsMode** comme suit :

- Définissez le paramètre sur **TeamsAndSfB** pour activer le complément réunion teams et le complément Skype entreprise dans Outlook. Il s’agit de la valeur par défaut.
- Définissez le paramètre sur **équipes** pour activer uniquement le complément réunion équipes dans Outlook. Ce paramètre de stratégie permet de s’assurer que toutes les réunions futures disposent d’un lien vers une réunion Teams. Elle ne permet pas de migrer des liens vers les équipes. Ce paramètre de stratégie n’a aucun impact sur la présence, les discussions, les appels RTC ou toute autre fonctionnalité de Skype entreprise, ce qui signifie que les utilisateurs continuent à utiliser Skype entreprise pour ces fonctionnalités.

  Si vous définissez le paramètre sur **teams**, puis que vous revenez à **TeamsAndSfB**, les compléments de réunion sont activés. Toutefois, Notez que les liens de participation à une réunion teams existants ne seront pas déplacés vers Skype entreprise. Seules les réunions Skype entreprise programmées après le changement comportent un lien vers une réunion Skype entreprise.

## <a name="meeting-policy-settings---video-filters-mode"></a>Paramètres de la stratégie de réunion-mode de filtres vidéo

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si les utilisateurs peuvent personnaliser leur arrière-plan vidéo dans une réunion.

Pour l’instant, vous pouvez uniquement utiliser PowerShell pour définir cette stratégie. Vous pouvez modifier une stratégie de réunion teams existante à l’aide de l’applet de passe [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez créer une stratégie de réunion teams à l’aide de l’applet [de nouvelle applet de nouveau-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) , puis affecter la stratégie aux utilisateurs.

Pour indiquer si les utilisateurs peuvent personnaliser leur arrière-plan vidéo dans une réunion, définissez le paramètre **VideoFiltersMode** comme suit :

|Définition d’une valeur dans PowerShell |Comportement  |
|---------|---------|
|**Nofiltre**     |L’utilisateur ne peut pas personnaliser son arrière-plan vidéo.|
|**BlurOnly**     |L’utilisateur a la possibilité de brouiller son arrière-plan vidéo. |
|**BlurandDefaultBackgrounds**     |L’utilisateur a la possibilité de brouiller son arrière-plan vidéo ou de choisir parmi les images par défaut à utiliser comme arrière-plan. |
|**AllFilters**     |Utiliser a la possibilité de brouiller l’arrière-plan de la vidéo, de choisir parmi les images par défaut ou de télécharger des images personnalisées à utiliser en tant qu’arrière-plan. |

> [!NOTE]
> Les images téléchargées par les utilisateurs ne sont pas affichées par Teams. Lorsque vous utilisez le paramètre **AllFilters** , vous devez disposer de stratégies d’organisation internes pour empêcher les utilisateurs de télécharger des images inappropriées ou inappropriées ou des images qui ne sont pas autorisées par votre organisation sur les arrière-plans des réunions Teams.

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
- [Suppression de la stratégie de réunion RestrictedAnonymousAccess teams des utilisateurs](meeting-policies-restricted-anonymous-access.md)
