---
title: Configurer les paramètres d’événements en direct dans Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment gérer les paramètres des événements en direct teams tenus au sein de votre organisation.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83d7e43e75b71eefdb4a95f26c14c27956e763f9
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2019
ms.locfileid: "35013036"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurer les paramètres d’événements en direct dans Microsoft Teams

Utilisez les paramètres d’événements en direct teams pour configurer les paramètres des événements en direct contenus dans votre organisation. Vous pouvez configurer une URL du support technique et configurer un fournisseur de distribution vidéo tiers. Ces paramètres s’appliquent à tous les événements en direct créés au sein de votre organisation. 

Vous pouvez facilement gérer ces paramètres dans le centre d’administration Microsoft Teams. Dans le volet de navigation de gauche, accédez à la section **réunions** > en**direct des événements**. 

![Capture d’écran des paramètres des événements en direct teams] (../media/teams-live-events-settings.png "Capture d’écran des paramètres d’événements en direct teams que vous pouvez configurer dans le centre d’administration Microsoft teams") 

## <a name="set-up-event-support-url"></a>Configurer l’URL du support technique des événements

Cette URL est présentée aux participants de l’événement en direct. Ajoutez l’URL du support technique de votre organisation pour permettre aux participants de contacter le support technique pendant un événement en direct.

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](../media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft teams

1. Dans le volet de navigation de gauche, accédez à la section **réunions** > en**temps réel des événements**.
2. Sous **URL du support technique**, entrez l’URL du support technique de votre organisation. 

    ![Paramètre d’URL d’assistance pour les événements en direct dans le centre d’administration] (../media/teams-live-events-settings-supporturl.png "Capture d’écran du paramètre d’URL du support technique pour les événements en direct teams")

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.
Exécutez la commande suivante :
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Pour plus d’informations, consultez la rubrique [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurer un fournisseur de distribution vidéo tiers 

Si vous avez acheté et configuré une solution SDN (Software Defined Network) ou un réseau de distribution de contenu d’entreprise (eCDN) par le biais d’un fournisseur de services vidéo Microsoft, configurez le fournisseur pour les événements en direct dans Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](../media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft teams

1. Dans le volet de navigation de gauche, accédez à la section **réunions** > en**temps réel des événements**.
2. Sous **fournisseurs de distribution vidéo tiers**, procédez comme suit: 

    ![Paramètres du fournisseur de distribution vidéo tiers dans le centre d’administration] (../media/teams-live-events-settings-distribution-provider.png "Capture d’écran des paramètres du fournisseur de distribution vidéo tiers pour les événements en direct")

    - **Utiliser un fournisseur de distribution tiers** Activez cette activation pour activer le fournisseur de distribution vidéo tiers.
    - **Nom du fournisseur de SDN** Choisissez le fournisseur que vous utilisez.
    - **Clé de licence du fournisseur** Entrez l’ID de licence obtenu par le contact du fournisseur.
    - **URL du modèle d’API SDN** Entrez l’URL du modèle d’API obtenue auprès du contact du fournisseur.

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.
Obtenez l’ID de licence ou le jeton d’API ainsi que le modèle d’API du contact du fournisseur, puis exécutez l’une des actions suivantes, selon le fournisseur que vous utilisez:

**Ruche** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Pour plus d’informations, consultez la rubrique [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Si vous envisagez de créer des événements dynamiques à l’aide d’une application ou d’un appareil externe, vous devez également [configurer votre fournisseur de services de eCDN avec Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Voir aussi
- [Que sont les événements en direct Teams ?](what-are-teams-live-events.md)
- [Offre pour les événements en direct Teams](plan-for-teams-live-events.md)
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)