---
title: Configurer les paramètres d’événements en direct dans Microsoft Teams
author: cichur
ms.author: v-cichur
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
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: Découvrez comment gérer les paramètres des événements en direct Teams qui se tiennent dans votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9749484344d969671e8a0195de3386a57388d275
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637876"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="ceae2-103">Configurer les paramètres d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ceae2-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="ceae2-104">Utilisez les paramètres des événements en direct Teams pour configurer les paramètres des événements en direct qui se tiennent dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ceae2-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="ceae2-105">Vous pouvez configurer une URL de prise en charge et configurer un fournisseur de distribution de vidéos tiers.</span><span class="sxs-lookup"><span data-stu-id="ceae2-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="ceae2-106">Ces paramètres s’appliquent à tous les événements en direct créés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ceae2-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="ceae2-107">Vous pouvez facilement gérer ces paramètres dans le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ceae2-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ceae2-108">Dans le navigation de gauche, allez aux **paramètres d’événements**  >  **live Meetings.**</span><span class="sxs-lookup"><span data-stu-id="ceae2-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="ceae2-109">![Capture d’écran des paramètres des événements en direct Teams](../media/teams-live-events-settings.png "Capture d’écran des paramètres d’événements en direct Teams que vous pouvez configurer dans le Centre d’administration Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="ceae2-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="ceae2-110">Configurer l’URL de prise en charge des événements</span><span class="sxs-lookup"><span data-stu-id="ceae2-110">Set up event support URL</span></span>

<span data-ttu-id="ceae2-111">Cette URL est affichée aux participants à l’événement en direct.</span><span class="sxs-lookup"><span data-stu-id="ceae2-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="ceae2-112">Ajoutez l’URL de support pour votre organisation afin que les participants voient le support technique pendant un événement en direct.</span><span class="sxs-lookup"><span data-stu-id="ceae2-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="ceae2-114&quot;>Utilisation du centre d’administration Microsoft Teams</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ceae2-114&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;ceae2-115&quot;>Dans la barre de navigation de gauche, allez **aux paramètres de l’événement Meetings**  >  **Live event.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ceae2-115&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;ceae2-116&quot;>Sous **URL du support technique,** entrez l’URL du support technique de votre organisation.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ceae2-116&quot;>Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id=&quot;ceae2-117&quot;>![Paramètre de l’URL de prise en charge des événements en direct dans le Centre d’administration](../media/teams-live-events-settings-supporturl.png &quot;Capture d’écran du paramètre d’URL de support pour les événements en direct Teams")</span><span class="sxs-lookup"><span data-stu-id="ceae2-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="ceae2-118">Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="ceae2-118">Using Windows PowerShell</span></span>

<span data-ttu-id="ceae2-119">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ceae2-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="ceae2-120">Pour plus d’informations, [voir Set-CsTeamsMeetingBroadcastConfiguration.](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ceae2-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="ceae2-121">Configurer un fournisseur de distribution de vidéos tiers</span><span class="sxs-lookup"><span data-stu-id="ceae2-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="ceae2-122">Si vous avez acheté et configuré une solution de réseau (SDN) définie par le logiciel ou de réseau de distribution de contenu d’entreprise (eCDN) via un partenaire de distribution de vidéos Microsoft, configurez le fournisseur pour les événements en direct dans Teams.</span><span class="sxs-lookup"><span data-stu-id="ceae2-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="ceae2-124&quot;>Utilisation du centre d’administration Microsoft Teams</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ceae2-124&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;ceae2-125&quot;>Dans la barre de navigation de gauche, allez **aux paramètres de l’événement Meetings**  >  **Live event.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ceae2-125&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;ceae2-126&quot;>Sous **Fournisseurs de distribution de vidéos tiers,** remplissez les conditions suivantes :</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ceae2-126&quot;>Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id=&quot;ceae2-127&quot;>![Paramètres du fournisseur de distribution de vidéos tiers dans le Centre d’administration](../media/teams-live-events-settings-distribution-provider.png &quot;Capture d’écran des paramètres du fournisseur de distribution de vidéos tiers pour les événements en direct")</span><span class="sxs-lookup"><span data-stu-id="ceae2-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="ceae2-128">**Utiliser un fournisseur de distribution tiers** Activez cette fonction pour activer le fournisseur de distribution de vidéos tiers.</span><span class="sxs-lookup"><span data-stu-id="ceae2-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="ceae2-129">**Nom du fournisseur SDN** Choisissez le fournisseur que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="ceae2-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="ceae2-130">**Clé de licence fournisseur** Entrez l’ID de licence obtenu auprès du contact de votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="ceae2-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="ceae2-131">**URL du modèle d’API SDN** Entrez l’URL du modèle d’API que vous avez obtenu du contact de votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="ceae2-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="ceae2-132">Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="ceae2-132">Using Windows PowerShell</span></span>
<span data-ttu-id="ceae2-133">Obtenez l’ID de licence ou le modèle d’API et le modèle d’API auprès de votre fournisseur, puis exécutez l’une des solutions suivantes, selon le fournisseur que vous utilisez :</span><span class="sxs-lookup"><span data-stu-id="ceae2-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="ceae2-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="ceae2-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="ceae2-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="ceae2-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="ceae2-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="ceae2-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
<span data-ttu-id="ceae2-137">**Ramp**</span><span class="sxs-lookup"><span data-stu-id="ceae2-137">**Ramp**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

<span data-ttu-id="ceae2-138">Pour plus d’informations, [voir Set-CsTeamsMeetingBroadcastConfiguration.](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ceae2-138">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="ceae2-139">Si vous prévoyez de créer des événements en direct à l’aide d’une application ou d’un appareil externe, vous devrez également configurer votre fournisseur [eCDN avec Microsoft Stream.](/stream/network-caching)</span><span class="sxs-lookup"><span data-stu-id="ceae2-139">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="ceae2-p104">Le passage de Microsoft Stream à [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](../tmr-meeting-recording-change.md) est une approche à différentes étapes. Au lancement, vous aurez la possibilité de choisir cette expérience. En novembre vous devrez quitter cette option si vous souhaitez poursuivre avec Stream et, au début de 2021 nous exigerons de tous les clients l’utilisation de OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="ceae2-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

>[!Note]
> <span data-ttu-id="ceae2-142">Votre solution eCDN choisie est soumise aux conditions d’utilisation et à la politique de confidentialité du fournisseur tiers sélectionné, qui régissent votre utilisation de la solution du fournisseur eCDN.</span><span class="sxs-lookup"><span data-stu-id="ceae2-142">Your chosen eCDN solution is subject to the selected 3rd party provider’s terms of service and privacy policy, which will govern your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="ceae2-143">Votre utilisation de la solution du fournisseur eCDN ne sera pas soumise aux conditions de licence en volume ou aux conditions des services en ligne de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ceae2-143">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="ceae2-144">Si vous n’acceptez pas les conditions du fournisseur tiers, n’activez pas la solution eCDN dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ceae2-144">If you don't agree to the 3rd party provider’s terms, then don't enable the eCDN solution in Microsoft Teams.</span></span>

### <a name="related-topics"></a><span data-ttu-id="ceae2-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ceae2-145">Related topics</span></span>
- [<span data-ttu-id="ceae2-146">Que sont les événements en direct Teams ?</span><span class="sxs-lookup"><span data-stu-id="ceae2-146">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="ceae2-147">Offre pour les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="ceae2-147">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="ceae2-148">Configurer les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="ceae2-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
