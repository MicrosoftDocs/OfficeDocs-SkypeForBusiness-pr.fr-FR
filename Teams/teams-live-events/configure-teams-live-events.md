---
title: Configurer les paramètres d’événements en direct dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Découvrez comment gérer les paramètres des événements en direct teams tenus au sein de votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0e949b2773baa2cc819629133396020dee7d7d7
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203947"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurer les paramètres d’événements en direct dans Microsoft Teams

Utilisez les paramètres d’événements en direct teams pour configurer les paramètres des événements en direct contenus dans votre organisation. Vous pouvez configurer une URL du support technique et configurer un fournisseur de distribution vidéo tiers. Ces paramètres s’appliquent à tous les événements en direct créés au sein de votre organisation.

Vous pouvez facilement gérer ces paramètres dans le centre d’administration Microsoft Teams. Dans le volet de navigation de gauche, accédez à la section **réunions**en  >  **direct des événements**.

![Capture d’écran des paramètres des événements en direct teams](../media/teams-live-events-settings.png "Capture d’écran des paramètres d’événements en direct teams que vous pouvez configurer dans le centre d’administration Microsoft teams")

## <a name="set-up-event-support-url"></a>Configurer l’URL du support technique des événements

Cette URL est présentée aux participants de l’événement en direct. Ajoutez l’URL du support technique de votre organisation pour permettre aux participants de contacter le support technique pendant un événement en direct.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft Teams](../media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez à la section **réunions**en  >  **temps réel des événements**.
2. Sous **URL du support technique**, entrez l’URL du support technique de votre organisation.

    ![Paramètre d’URL d’assistance pour les événements en direct dans le centre d’administration](../media/teams-live-events-settings-supporturl.png "Capture d’écran du paramètre d’URL du support technique pour les événements en direct teams")

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.

Exécutez la commande suivante :

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Pour plus d’informations, consultez la rubrique [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurer un fournisseur de distribution vidéo tiers 

Si vous avez acheté et configuré une solution SDN (Software Defined Network) ou un réseau de distribution de contenu d’entreprise (eCDN) par le biais d’un fournisseur de services vidéo Microsoft, configurez le fournisseur pour les événements en direct dans Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft Teams](../media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez à la section **réunions**en  >  **temps réel des événements**.
2. Sous **fournisseurs de distribution vidéo tiers**, procédez comme suit : 

    ![Paramètres du fournisseur de distribution vidéo tiers dans le centre d’administration](../media/teams-live-events-settings-distribution-provider.png "Capture d’écran des paramètres du fournisseur de distribution vidéo tiers pour les événements en direct")

    - **Utiliser un fournisseur de distribution tiers** Activez cette activation pour activer le fournisseur de distribution vidéo tiers.
    - **Nom du fournisseur de SDN** Choisissez le fournisseur que vous utilisez.
    - **Clé de licence du fournisseur** Entrez l’ID de licence obtenu par le contact du fournisseur.
    - **URL du modèle d’API SDN** Entrez l’URL du modèle d’API obtenue auprès du contact du fournisseur.

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.
Obtenez l’ID de licence ou le jeton d’API ainsi que le modèle d’API du contact du fournisseur, puis exécutez l’une des actions suivantes, selon le fournisseur que vous utilisez :

**Ruche** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

Pour plus d’informations, consultez la rubrique [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Si vous envisagez de créer des événements dynamiques à l’aide d’une application ou d’un appareil externe, vous devez également [configurer votre fournisseur de services de eCDN avec Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

>[!Note]
> Les modifications apportées à l’aide de Microsoft Stream to [OneDrive entreprise et de SharePoint pour les enregistrements de réunion](../tmr-meeting-recording-change.md) seront une approche progressive. Au moment de l’exécution, vous serez en mesure de vous abonner à cette expérimentation en novembre, si vous voulez continuer à utiliser le flux de travail et que, à un 2021 moment donné, il est nécessaire que tous les clients utilisent OneDrive entreprise et SharePoint pour les nouveaux enregistrements de réunion.

### <a name="related-topics"></a>Sujets associés
- [Que sont les événements en direct Teams ?](what-are-teams-live-events.md)
- [Offre pour les événements en direct Teams](plan-for-teams-live-events.md)
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)