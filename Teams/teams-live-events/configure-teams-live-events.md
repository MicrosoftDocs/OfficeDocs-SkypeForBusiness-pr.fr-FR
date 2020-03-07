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
ms.openlocfilehash: 222e7e51fcf87e0e76c3ab18f33357f7489a1ce1
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558594"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="c71dd-103">Configurer les paramètres d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c71dd-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="c71dd-104">Utilisez les paramètres d’événements en direct teams pour configurer les paramètres des événements en direct contenus dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c71dd-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="c71dd-105">Vous pouvez configurer une URL du support technique et configurer un fournisseur de distribution vidéo tiers.</span><span class="sxs-lookup"><span data-stu-id="c71dd-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="c71dd-106">Ces paramètres s’appliquent à tous les événements en direct créés au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c71dd-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="c71dd-107">Vous pouvez facilement gérer ces paramètres dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c71dd-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c71dd-108">Dans le volet de navigation de gauche, accédez à la section **réunions** > en**direct des événements**.</span><span class="sxs-lookup"><span data-stu-id="c71dd-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="c71dd-109">![Capture d’écran des paramètres des événements en direct teams](../media/teams-live-events-settings.png "Capture d’écran des paramètres d’événements en direct teams que vous pouvez configurer dans le centre d’administration Microsoft teams")</span><span class="sxs-lookup"><span data-stu-id="c71dd-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="c71dd-110">Configurer l’URL du support technique des événements</span><span class="sxs-lookup"><span data-stu-id="c71dd-110">Set up event support URL</span></span>

<span data-ttu-id="c71dd-111">Cette URL est présentée aux participants de l’événement en direct.</span><span class="sxs-lookup"><span data-stu-id="c71dd-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="c71dd-112">Ajoutez l’URL du support technique de votre organisation pour permettre aux participants de contacter le support technique pendant un événement en direct.</span><span class="sxs-lookup"><span data-stu-id="c71dd-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](../media/teams-logo-30x30.png) <span data-ttu-id="c71dd-114">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="c71dd-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c71dd-115">Dans le volet de navigation de gauche, accédez à la section **réunions** > en**temps réel des événements**.</span><span class="sxs-lookup"><span data-stu-id="c71dd-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="c71dd-116">Sous **URL du support technique**, entrez l’URL du support technique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c71dd-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="c71dd-117">![Paramètre d’URL d’assistance pour les événements en direct dans le centre d’administration](../media/teams-live-events-settings-supporturl.png "Capture d’écran du paramètre d’URL du support technique pour les événements en direct teams")</span><span class="sxs-lookup"><span data-stu-id="c71dd-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="c71dd-118">Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="c71dd-118">Using Windows PowerShell</span></span>
<span data-ttu-id="c71dd-119">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c71dd-119">Run the following:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="c71dd-120">Pour plus d’informations, consultez la rubrique [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c71dd-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="c71dd-121">Configurer un fournisseur de distribution vidéo tiers</span><span class="sxs-lookup"><span data-stu-id="c71dd-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="c71dd-122">Si vous avez acheté et configuré une solution SDN (Software Defined Network) ou un réseau de distribution de contenu d’entreprise (eCDN) par le biais d’un fournisseur de services vidéo Microsoft, configurez le fournisseur pour les événements en direct dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c71dd-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](../media/teams-logo-30x30.png) <span data-ttu-id="c71dd-124">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="c71dd-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c71dd-125">Dans le volet de navigation de gauche, accédez à la section **réunions** > en**temps réel des événements**.</span><span class="sxs-lookup"><span data-stu-id="c71dd-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="c71dd-126">Sous **fournisseurs de distribution vidéo tiers**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c71dd-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="c71dd-127">![Paramètres du fournisseur de distribution vidéo tiers dans le centre d’administration](../media/teams-live-events-settings-distribution-provider.png "Capture d’écran des paramètres du fournisseur de distribution vidéo tiers pour les événements en direct")</span><span class="sxs-lookup"><span data-stu-id="c71dd-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="c71dd-128">**Utiliser un fournisseur de distribution tiers** Activez cette activation pour activer le fournisseur de distribution vidéo tiers.</span><span class="sxs-lookup"><span data-stu-id="c71dd-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="c71dd-129">**Nom du fournisseur de SDN** Choisissez le fournisseur que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="c71dd-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="c71dd-130">**Clé de licence du fournisseur** Entrez l’ID de licence obtenu par le contact du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c71dd-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="c71dd-131">**URL du modèle d’API SDN** Entrez l’URL du modèle d’API obtenue auprès du contact du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c71dd-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="c71dd-132">Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="c71dd-132">Using Windows PowerShell</span></span>
<span data-ttu-id="c71dd-133">Obtenez l’ID de licence ou le jeton d’API ainsi que le modèle d’API du contact du fournisseur, puis exécutez l’une des actions suivantes, selon le fournisseur que vous utilisez :</span><span class="sxs-lookup"><span data-stu-id="c71dd-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="c71dd-134">**Ruche**</span><span class="sxs-lookup"><span data-stu-id="c71dd-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="c71dd-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="c71dd-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="c71dd-136">Pour plus d’informations, consultez la rubrique [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c71dd-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="c71dd-137">Si vous envisagez de créer des événements dynamiques à l’aide d’une application ou d’un appareil externe, vous devez également [configurer votre fournisseur de services de eCDN avec Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="c71dd-137">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="c71dd-138">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="c71dd-138">Related topics</span></span>
- [<span data-ttu-id="c71dd-139">Que sont les événements en direct Teams ?</span><span class="sxs-lookup"><span data-stu-id="c71dd-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="c71dd-140">Offre pour les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="c71dd-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="c71dd-141">Configurer les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="c71dd-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)