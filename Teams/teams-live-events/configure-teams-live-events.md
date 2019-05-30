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
ms.openlocfilehash: 277f5b326a2c8c4427ae4cea740630d4d1e6f0c7
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548644"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="57e00-103">Configurer les paramètres d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57e00-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="57e00-104">Utilisez les paramètres d’événements en direct teams pour configurer les paramètres des événements en direct contenus dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57e00-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="57e00-105">Vous pouvez configurer une URL du support technique et configurer un fournisseur de distribution vidéo tiers.</span><span class="sxs-lookup"><span data-stu-id="57e00-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="57e00-106">Ces paramètres s’appliquent à tous les événements en direct créés au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57e00-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="57e00-107">Vous pouvez facilement gérer ces paramètres dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="57e00-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="57e00-108">Dans le volet de navigation de gauche, accédez à la section **réunions** > en**direct des événements**.</span><span class="sxs-lookup"><span data-stu-id="57e00-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="57e00-109">![Capture d’écran des paramètres des événements en direct teams] (../media/teams-live-events-settings.png "Capture d’écran des paramètres d’événements en direct teams que vous pouvez configurer dans le centre d’administration Microsoft teams")</span><span class="sxs-lookup"><span data-stu-id="57e00-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="57e00-110">Configurer l’URL du support technique des événements</span><span class="sxs-lookup"><span data-stu-id="57e00-110">Set up event support URL</span></span>

<span data-ttu-id="57e00-111">Cette URL est présentée aux participants de l’événement en direct.</span><span class="sxs-lookup"><span data-stu-id="57e00-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="57e00-112">Ajoutez l’URL du support technique de votre organisation pour permettre aux participants de contacter le support technique pendant un événement en direct.</span><span class="sxs-lookup"><span data-stu-id="57e00-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](../media/teams-logo-30x30.png) <span data-ttu-id="57e00-114">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="57e00-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="57e00-115">Dans le volet de navigation de gauche, accédez à la section **réunions** > en**temps réel des événements**.</span><span class="sxs-lookup"><span data-stu-id="57e00-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="57e00-116">Sous **URL du support technique**, entrez l’URL du support technique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57e00-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="57e00-117">![Paramètre d’URL d’assistance pour les événements en direct dans le centre d’administration] (../media/teams-live-events-settings-supporturl.png "Capture d’écran du paramètre d’URL du support technique pour les événements en direct teams")</span><span class="sxs-lookup"><span data-stu-id="57e00-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="57e00-118">Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="57e00-118">Using Windows PowerShell</span></span>
<span data-ttu-id="57e00-119">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="57e00-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="57e00-120">Pour plus d’informations, consultez la rubrique [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="57e00-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="57e00-121">Configurer un fournisseur de distribution vidéo tiers</span><span class="sxs-lookup"><span data-stu-id="57e00-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="57e00-122">Si vous avez acheté et configuré une solution SDN (Software Defined Network) ou un réseau de distribution de contenu d’entreprise (eCDN) par le biais d’un fournisseur de services vidéo Microsoft, configurez le fournisseur pour les événements en direct dans Teams.</span><span class="sxs-lookup"><span data-stu-id="57e00-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](../media/teams-logo-30x30.png) <span data-ttu-id="57e00-124">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="57e00-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="57e00-125">Dans le volet de navigation de gauche, accédez à la section **réunions** > en**temps réel des événements**.</span><span class="sxs-lookup"><span data-stu-id="57e00-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="57e00-126">Sous **fournisseurs de distribution vidéo tiers**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="57e00-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="57e00-127">![Paramètres du fournisseur de distribution vidéo tiers dans le centre d’administration] (../media/teams-live-events-settings-distribution-provider.png "Capture d’écran des paramètres du fournisseur de distribution vidéo tiers pour les événements en direct")</span><span class="sxs-lookup"><span data-stu-id="57e00-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="57e00-128">**Utiliser un fournisseur de distribution tiers** Activez cette activation pour activer le fournisseur de distribution vidéo tiers.</span><span class="sxs-lookup"><span data-stu-id="57e00-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="57e00-129">**Nom du fournisseur de SDN** Choisissez le fournisseur que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="57e00-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="57e00-130">**Clé de licence du fournisseur** Entrez l’ID de licence obtenu par le contact du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="57e00-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="57e00-131">**URL du modèle d’API SDN** Entrez l’URL du modèle d’API obtenue auprès du contact du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="57e00-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="57e00-132">Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="57e00-132">Using Windows PowerShell</span></span>
<span data-ttu-id="57e00-133">Obtenez l’ID de licence ou le jeton d’API ainsi que le modèle d’API du contact du fournisseur, puis exécutez l’une des actions suivantes, selon le fournisseur que vous utilisez:</span><span class="sxs-lookup"><span data-stu-id="57e00-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="57e00-134">**Ruche**</span><span class="sxs-lookup"><span data-stu-id="57e00-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="57e00-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="57e00-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="57e00-136">Pour plus d’informations, consultez la rubrique [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="57e00-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="57e00-137">Si vous envisagez de créer des événements en direct qui utilisent des encodeurs externes, vous devez également [configurer votre fournisseur de services de eCDN avec Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="57e00-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="57e00-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57e00-138">Related topics</span></span>
- [<span data-ttu-id="57e00-139">Que sont les événements en direct Teams ?</span><span class="sxs-lookup"><span data-stu-id="57e00-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="57e00-140">Offre pour les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="57e00-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="57e00-141">Configurer les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="57e00-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)