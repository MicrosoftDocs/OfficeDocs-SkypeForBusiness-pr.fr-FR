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
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664891"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="883a2-103">Configurer les paramètres d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="883a2-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="883a2-104">Utilisez les paramètres d’événements en direct équipes pour configurer les paramètres pour les événements live qui sont stockés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="883a2-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="883a2-105">Vous pouvez configurer une URL de prise en charge et configurer un fournisseur de distribution vidéo tiers.</span><span class="sxs-lookup"><span data-stu-id="883a2-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="883a2-106">Ces paramètres s’appliquent à tous les événements live qui sont créés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="883a2-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="883a2-107">Vous pouvez facilement gérer ces paramètres dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="883a2-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="883a2-108">Dans la navigation de gauche, accédez à des **réunions** > **paramètres d’événements en direct**.</span><span class="sxs-lookup"><span data-stu-id="883a2-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="883a2-109">![settings.png-événement Live] (../media/teams-live-events-settings.png "Capture d’écran des équipes live paramètres des événements que vous pouvez configurer dans le centre d’administration Microsoft équipes")</span><span class="sxs-lookup"><span data-stu-id="883a2-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="883a2-110">Configurer des URL de support d’événements</span><span class="sxs-lookup"><span data-stu-id="883a2-110">Set up event support URL</span></span>

<span data-ttu-id="883a2-111">Cette URL est affichée en direct des participants de l’événement.</span><span class="sxs-lookup"><span data-stu-id="883a2-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="883a2-112">Ajoutez l’URL de la prise en charge pour votre organisation pour donner à un moyen de contacter le support pendant un événement live participants.</span><span class="sxs-lookup"><span data-stu-id="883a2-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![les équipes-logo-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="883a2-114">À l’aide du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="883a2-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="883a2-115">Dans la navigation de gauche, accédez à des **réunions** > **paramètres événements Live**.</span><span class="sxs-lookup"><span data-stu-id="883a2-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="883a2-116">Sous **Prennent en charge les URL**, entrez les URL de support de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="883a2-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="883a2-117">![Paramètre d’URL de support pour les événements dans le centre d’administration Microsoft équipes en direct] (../media/teams-live-events-settings-supporturl.png "Capture d’écran de l’URL définition d’événements en direct pour les équipes de support")</span><span class="sxs-lookup"><span data-stu-id="883a2-117">![Support URL setting for live events in the Microsoft Teams admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="883a2-118">Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="883a2-118">Using Windows PowerShell</span></span>
<span data-ttu-id="883a2-119">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="883a2-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="883a2-120">Pour plus d’informations, voir [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="883a2-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="883a2-121">Configurer un fournisseur de distribution vidéo tiers</span><span class="sxs-lookup"><span data-stu-id="883a2-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="883a2-122">Si vous avez acheté et configurez une solution logicielle défini de network (SDN) ou une solution réseau (eCDN) de distribution de contenu d’entreprise par un partenaire de remise vidéo Microsoft, configurez le fournisseur pour les événements live dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="883a2-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![les équipes-logo-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="883a2-124">À l’aide du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="883a2-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="883a2-125">Dans la navigation de gauche, accédez à des **réunions** > **paramètres événements Live**.</span><span class="sxs-lookup"><span data-stu-id="883a2-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="883a2-126">Sous les **fournisseurs de distribution vidéo tiers**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="883a2-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="883a2-127">![Paramètres du fournisseur tiers distribution vidéo dans le centre d’administration Microsoft équipes] (../media/teams-live-events-settings-distribution-provider.png "Capture d’écran de distribution vidéo tiers fournisseur décrivant les événements en direct")</span><span class="sxs-lookup"><span data-stu-id="883a2-127">![Third-party video distribution provider settings in the Microsoft Teams admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="883a2-128">**Utilisation d’un fournisseur tiers distribution** Désactivez cette option actif pour activer le fournisseur de distribution vidéo tiers.</span><span class="sxs-lookup"><span data-stu-id="883a2-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="883a2-129">**Nom du fournisseur SDN** Sélectionnez le fournisseur que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="883a2-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="883a2-130">**Clé de licence de fournisseur** Entrez l’ID de la licence que vous avez obtenu à partir de votre contact fournisseur.</span><span class="sxs-lookup"><span data-stu-id="883a2-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="883a2-131">**URL du modèle API SDN** Entrez l’URL de modèle API que vous avez obtenu à partir de votre contact fournisseur.</span><span class="sxs-lookup"><span data-stu-id="883a2-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="883a2-132">Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="883a2-132">Using Windows PowerShell</span></span>
<span data-ttu-id="883a2-133">Obtenir le jeton de licence d’ID ou d’API et modèle de l’API de contact de votre fournisseur, puis exécutez une des valeurs suivantes, selon le fournisseur que vous utilisez :</span><span class="sxs-lookup"><span data-stu-id="883a2-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="883a2-134">**Ruche**</span><span class="sxs-lookup"><span data-stu-id="883a2-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="883a2-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="883a2-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="883a2-136">Pour plus d’informations, voir [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="883a2-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="883a2-137">Si vous envisagez de créer des événements en temps réel qui utilisent des encodeurs externes, vous devez également [configurer votre fournisseur eCDN avec flux de Microsoft](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="883a2-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="883a2-138">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="883a2-138">Related topics</span></span>
- [<span data-ttu-id="883a2-139">Que sont les événements en direct Teams ?</span><span class="sxs-lookup"><span data-stu-id="883a2-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="883a2-140">Offre pour les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="883a2-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="883a2-141">Configurer les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="883a2-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)