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
description: Découvrez comment gérer les paramètres pour les événements live équipes qui sont trouvent dans votre organisation.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3c1a3c4883705f5e9e5ded88cce94fc37da650b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204741"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurer les paramètres d’événements en direct dans Microsoft Teams

Utilisez les paramètres d’événements en direct équipes pour configurer les paramètres pour les événements live qui sont stockés dans votre organisation. Vous pouvez configurer une URL de prise en charge et configurer un fournisseur de distribution vidéo tiers. Ces paramètres s’appliquent à tous les événements live qui sont créés dans votre organisation. 

Vous pouvez facilement gérer ces paramètres dans le centre d’administration Microsoft Teams. Dans la navigation de gauche, accédez à des **réunions** > **paramètres d’événements en direct**. 

![settings.png-événement Live] (../media/teams-live-events-settings.png "Capture d’écran des équipes live paramètres des événements que vous pouvez configurer dans le centre d’administration Microsoft équipes") 

## <a name="set-up-event-support-url"></a>Configurer des URL de support d’événements

Cette URL est affichée en direct des participants de l’événement. Ajoutez l’URL de la prise en charge pour votre organisation pour donner à un moyen de contacter le support pendant un événement live participants.

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![les équipes-logo-30x30.png](../media/teams-logo-30x30.png) À l’aide du centre d’administration Microsoft Teams

1. Dans la navigation de gauche, accédez à des **réunions** > **paramètres événements Live**.
2. Sous **Prennent en charge les URL**, entrez les URL de support de votre organisation. 

    ![Paramètre d’URL de support pour les événements dans le centre d’administration Microsoft équipes en direct] (../media/teams-live-events-settings-supporturl.png "Capture d’écran de l’URL définition d’événements en direct pour les équipes de support")

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.
Exécutez la commande suivante :
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Pour plus d’informations, voir [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurer un fournisseur de distribution vidéo tiers 

Si vous avez acheté et configurez une solution logicielle défini de network (SDN) ou une solution réseau (eCDN) de distribution de contenu d’entreprise par un partenaire de remise vidéo Microsoft, configurez le fournisseur pour les événements live dans les équipes. 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![les équipes-logo-30x30.png](../media/teams-logo-30x30.png) À l’aide du centre d’administration Microsoft Teams

1. Dans la navigation de gauche, accédez à des **réunions** > **paramètres événements Live**.
2. Sous les **fournisseurs de distribution vidéo tiers**, procédez comme suit : 

    ![Paramètres du fournisseur tiers distribution vidéo dans le centre d’administration Microsoft équipes] (../media/teams-live-events-settings-distribution-provider.png "Capture d’écran de distribution vidéo tiers fournisseur décrivant les événements en direct")

    - **Utilisation d’un fournisseur tiers distribution** Désactivez cette option actif pour activer le fournisseur de distribution vidéo tiers.
    - **Nom du fournisseur SDN** Sélectionnez le fournisseur que vous utilisez.
    - **Clé de licence de fournisseur** Entrez l’ID de la licence que vous avez obtenu à partir de votre contact fournisseur.
    - **URL du modèle API SDN** Entrez l’URL de modèle API que vous avez obtenu à partir de votre contact fournisseur.

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.
Obtenir le jeton de licence d’ID ou d’API et modèle de l’API de contact de votre fournisseur, puis exécutez une des valeurs suivantes, selon le fournisseur que vous utilisez :

**Ruche** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Pour plus d’informations, voir [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Si vous envisagez de créer des événements en temps réel qui utilisent des encodeurs externes, vous devez également [configurer votre fournisseur eCDN avec flux de Microsoft](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Voir aussi
- [Que sont les événements en direct Teams ?](what-are-teams-live-events.md)
- [Offre pour les événements en direct Teams](plan-for-teams-live-events.md)
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)