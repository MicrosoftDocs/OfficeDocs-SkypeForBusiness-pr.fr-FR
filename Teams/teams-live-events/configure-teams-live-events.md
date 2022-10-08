---
title: Configurer les paramètres d’événements en direct dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: Découvrez comment gérer les paramètres des événements en direct Teams qui sont organisés dans votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: f526a3404d9077ecd97d877a914975218640028c
ms.sourcegitcommit: fcedb958bf555d870215ae84fb83752304944716
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68486564"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurer les paramètres d’événements en direct dans Microsoft Teams

Utilisez les paramètres d’événements en direct Teams pour configurer les paramètres des événements en direct qui se tiennent dans votre organisation. Vous pouvez configurer une URL de support et un fournisseur de distribution de vidéos tiers. Ces paramètres s’appliquent à tous les événements en direct créés dans votre organisation.

Vous pouvez facilement gérer ces paramètres dans le Centre d’administration Microsoft Teams. Dans le volet de navigation de gauche, accédez aux **paramètres des événements** > **en direct réunions**.

![Capture d’écran des paramètres des événements en direct Teams.](../media/teams-live-events-settings-new.png "Capture d’écran des paramètres d’événements en direct Teams que vous pouvez configurer dans le Centre d’administration Microsoft Teams")

## <a name="set-up-event-support-url"></a>Configurer l’URL de prise en charge des événements

Cette URL s’affiche pour les participants aux événements en direct. Ajoutez l’URL de support de votre organisation pour permettre aux participants de contacter le support lors d’un événement en direct.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez aux **paramètres d’événements** > **En direct des réunions**.
2. Sous **URL du support**, entrez l’URL de support de votre organisation.

    ![Paramètre d’URL de prise en charge pour les événements en direct dans le Centre d’administration.](../media/teams-live-events-settings-supporturl.png "Capture d’écran du paramètre d’URL de support pour les événements en direct Teams")

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.

Exécutez la commande suivante :

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Pour plus d’informations, consultez [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurer un fournisseur de distribution de vidéos tiers 

Si vous avez acheté et configuré une solution SDN (Software Defined Network) ou un réseau de distribution de contenu d’entreprise (eCDN) par le biais d’un partenaire de distribution de vidéos Microsoft, configurez le fournisseur pour les événements en direct dans Teams. 

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez aux **paramètres d’événements** > **En direct des réunions**.
2. Sous **fournisseurs de distribution de vidéos tiers**, procédez comme suit : 

    ![Paramètres du fournisseur de distribution de vidéos tiers dans le Centre d’administration.](../media/teams-live-events-settings-distribution-provider-new.png "Capture d’écran des paramètres du fournisseur de distribution de vidéos tiers pour les événements en direct")

    - **Fournisseur de distribution tiers** Activez cette option pour activer le fournisseur de distribution de vidéos tiers.
    - **Nom du fournisseur SDN** Choisissez le fournisseur que vous utilisez.
    - **Configuration du SDN** Entrez les détails de la configuration SDN.
        
### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.
Obtenez l’ID de licence ou le jeton d’API et le modèle d’API à partir du contact de votre fournisseur, puis exécutez l’une des opérations suivantes, en fonction du fournisseur que vous utilisez :

**Hive** 
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
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```
**Homologue 5**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName peer5 -SdnLicenseId {peer5CustomerId}
```

Pour plus d’informations, consultez [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).

> [!NOTE]
> Si vous envisagez de créer des événements en direct à l’aide d’une application ou d’un appareil externe, vous devez également [configurer votre fournisseur eCDN avec Microsoft Stream](/stream/network-caching). 

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.

>[!Note]
> Votre solution eCDN choisie est soumise aux conditions d’utilisation et à la politique de confidentialité du fournisseur tiers sélectionné, qui régiront votre utilisation de la solution du fournisseur eCDN. Votre utilisation de la solution du fournisseur eCDN ne sera pas soumise aux termes de licence en volume Microsoft ou aux conditions des services en ligne. Si vous n’acceptez pas les conditions du fournisseur tiers, n’activez pas la solution eCDN dans Microsoft Teams.

### <a name="related-topics"></a>Rubriques connexes
- [Que sont les événements en direct Teams ?](what-are-teams-live-events.md)
- [Offre pour les événements en direct Teams](plan-for-teams-live-events.md)
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)
