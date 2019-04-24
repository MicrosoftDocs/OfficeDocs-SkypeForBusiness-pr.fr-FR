---
title: Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Cet article explique comment planifier et configurer une interopérabilité vidéo Cloud pour les utilisateurs dans votre organisation.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b171b3fb5e73561ea5aea54e6e4f25bfabe6b0dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198859"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="6139b-103">Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6139b-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="6139b-104">Une fois que vous avez [choisi sur vos partenaires interopérabilité vidéo sur le nuage](cloud-video-interop.md), vous devrez planifier votre déploiement, get configurer avec des détails de mise en service et la clé client partenaire et consentement de l’utilisateur à l’application d’interopérabilité vidéo dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6139b-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="6139b-105">Le diagramme suivant présente le processus.</span><span class="sxs-lookup"><span data-stu-id="6139b-105">The following diagram outlines the process.</span></span> 

![Déploiement CVI dans votre organisation](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="6139b-107">Plan</span><span class="sxs-lookup"><span data-stu-id="6139b-107">Plan</span></span>

<span data-ttu-id="6139b-108">Pour plus d’informations sur l’identification d’un partenaire ou des partenaires à utiliser dans votre organisation, voir [Interopérabilité vidéo de Cloud pour les équipes Microsoft](cloud-video-interop.md) .</span><span class="sxs-lookup"><span data-stu-id="6139b-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="6139b-109">Planification de la prise en charge à l’échelle utilisateur/simultanés/site sur :</span><span class="sxs-lookup"><span data-stu-id="6139b-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="6139b-110">Choisir un modèle hébergé/modèle de déploiement pour l’utilisation</span><span class="sxs-lookup"><span data-stu-id="6139b-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="6139b-111">Sélectionnez le plan de licence idéale pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6139b-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="6139b-112">Planifier la capacité des ordinateurs virtuels est de que vous hébergez votre infrastructure vidéo.</span><span class="sxs-lookup"><span data-stu-id="6139b-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="6139b-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="6139b-113">Configure</span></span> 

<span data-ttu-id="6139b-114">Pour configurer une interopérabilité vidéo sur le nuage, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6139b-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="6139b-115">Obtenir des informations de configuration des partenaires/partenaires que vous avez choisi (clé client, AppID...).</span><span class="sxs-lookup"><span data-stu-id="6139b-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="6139b-116">Vous pouvez utiliser un ou plusieurs partenaires interopérabilités vidéo dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="6139b-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="6139b-117">Assurez-vous que votre réseau est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="6139b-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="6139b-118">Configurez votre pare-feu vidéo basée sur les normes de traversée du réseau de périmètre prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="6139b-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="6139b-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6139b-119">For example:</span></span> 
    - <span data-ttu-id="6139b-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="6139b-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="6139b-121">RPAD de Polycom</span><span class="sxs-lookup"><span data-stu-id="6139b-121">Polycom RPAD</span></span>

3. <span data-ttu-id="6139b-122">Configuration des salles intégrées avec exchange et OTD.</span><span class="sxs-lookup"><span data-stu-id="6139b-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="6139b-123">Dans la plupart des cas, relais supplémentaires devra être configurée et configurées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="6139b-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="6139b-124">Mise en service</span><span class="sxs-lookup"><span data-stu-id="6139b-124">Provision</span></span>
 
<span data-ttu-id="6139b-125">La clé client seront les appels sortants vers le service partenaire.</span><span class="sxs-lookup"><span data-stu-id="6139b-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="6139b-126">Dans l’exemple suivant, 813878896@t.plcm.vc est la clé de client.</span><span class="sxs-lookup"><span data-stu-id="6139b-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Exemple de clé de client](media/tenant-key-example.png) 

<span data-ttu-id="6139b-128">Vous devrez exécuter les applets de commande suivantes pour configurer la clé client et permettent également aux utilisateurs de sélectionner ou toute l’organisation créer des réunions avec des coordonnées interopérabilitées vidéo.</span><span class="sxs-lookup"><span data-stu-id="6139b-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="6139b-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft propose construit à partir des stratégies pour chacun des partenaires pris en charge qui vous permettent de désigner les partenaires qui à utiliser pour l’interopérabilité vidéo dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="6139b-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="6139b-130">Cette cmdlet vous permet d’identifier les construit à partir des stratégies que vous pouvez utiliser dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6139b-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="6139b-131">Vous pouvez assigner cette stratégie à un ou plusieurs de vos utilisateurs de tirer parti de l’applet de commande Grant-CsTeamsVideoInteropServicePolicy.</span><span class="sxs-lookup"><span data-stu-id="6139b-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="6139b-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* L’applet de commande Grant-CsTeamsVideoInteropServicePolicy permet d’affecter une stratégie construite préalable pour une utilisation dans votre organisation ou la stratégie à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6139b-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="6139b-133">\*\* [Nouveau CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Le nouveau-CsVideoInteropServiceProvider permet de spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.</span><span class="sxs-lookup"><span data-stu-id="6139b-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="6139b-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Utiliser la Set-CsVideoInteropServiceProvider pour mettre à jour des informations sur un partenaire CVI pris en charge que votre organisation utilise.</span><span class="sxs-lookup"><span data-stu-id="6139b-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="6139b-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Obtenir tous les fournisseurs qui ont été configurés pour une utilisation au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="6139b-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="6139b-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Remove-CsVideoInteropServiceProvider permet de supprimer toutes les informations fournisseur sur un fournisseur que votre organisation n’utilise plus.</span><span class="sxs-lookup"><span data-stu-id="6139b-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="6139b-137">Consentement de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="6139b-137">Consent</span></span>

<span data-ttu-id="6139b-138">Vous devrez fournir le consentement de l’autorisation pour les périphériques de téléconférence vidéo (VTCs) à participer à des réunions de votre organisation via le service partenaire.</span><span class="sxs-lookup"><span data-stu-id="6139b-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="6139b-139">Ce lien consentement est fourni par votre partenaire.</span><span class="sxs-lookup"><span data-stu-id="6139b-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="6139b-140">Une fois ces étapes terminées, les utilisateurs qui sont activés de façon individuelle par le biais de l’applet de commande Grant au-dessus ou tous les utilisateurs dans l’organisation si le client est activé, a VTC coordonnées dans toutes les réunions d’équipes qu’ils planifient.</span><span class="sxs-lookup"><span data-stu-id="6139b-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="6139b-141">N’importe quel VTC peut participer à ces réunions via ces coordonnées.</span><span class="sxs-lookup"><span data-stu-id="6139b-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="6139b-142">Nom</span><span class="sxs-lookup"><span data-stu-id="6139b-142">Name</span></span>|<span data-ttu-id="6139b-143">Courte Description d’autorisation d’application</span><span class="sxs-lookup"><span data-stu-id="6139b-143">Application Permission Short Description</span></span>| <span data-ttu-id="6139b-144">Description</span><span class="sxs-lookup"><span data-stu-id="6139b-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="6139b-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="6139b-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="6139b-146">Rejoindre des réunions et appels de groupe en tant qu’une application (preview)</span><span class="sxs-lookup"><span data-stu-id="6139b-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="6139b-147">Permet à l’application participer à des réunions planifiées et les appels de groupe dans votre organisation, sans qu’un utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="6139b-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="6139b-148">L’application s’être joint avec les privilèges d’un utilisateur de l’annuaire à des réunions dans votre client.</span><span class="sxs-lookup"><span data-stu-id="6139b-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="6139b-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="6139b-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="6139b-150">Participer à des réunions et appels de groupe en tant qu’invité (preview)</span><span class="sxs-lookup"><span data-stu-id="6139b-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="6139b-151">Permet à l’application à se joindre à des réunions planifiées et les appels de groupe dans votre organisation, sans qu’un utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="6139b-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="6139b-152">L’application sera joint en tant qu’invité à des réunions dans votre client.</span><span class="sxs-lookup"><span data-stu-id="6139b-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="6139b-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="6139b-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="6139b-154">Flux de données Access dans un appel en tant qu’une application (preview)</span><span class="sxs-lookup"><span data-stu-id="6139b-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="6139b-155">Permet à l’application d’accéder directement à des flux de données dans un appel, sans qu’un utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="6139b-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="6139b-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="6139b-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="6139b-157">Détails d’une réunion en ligne en lecture (preview)</span><span class="sxs-lookup"><span data-stu-id="6139b-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="6139b-158">Permet à l’application afficher les détails de réunion en ligne dans votre organisation, sans qu’un utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="6139b-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="6139b-159">Planification</span><span class="sxs-lookup"><span data-stu-id="6139b-159">Schedule</span></span>

<span data-ttu-id="6139b-160">Ensuite, planifier les équipes réunion avec vidéo coordonnées PIA.</span><span class="sxs-lookup"><span data-stu-id="6139b-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="6139b-161">L’utilisateur activé peut planifier des équipes réunions via :</span><span class="sxs-lookup"><span data-stu-id="6139b-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="6139b-162">Des équipes de complément de conférence pour Outlook</span><span class="sxs-lookup"><span data-stu-id="6139b-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="6139b-163">Client équipes mobile et de bureau</span><span class="sxs-lookup"><span data-stu-id="6139b-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="6139b-164">Rejoindre</span><span class="sxs-lookup"><span data-stu-id="6139b-164">Join</span></span>

<span data-ttu-id="6139b-165">Vous pouvez joindre des réunions d’équipes avec vos périphériques VTC comme suit :</span><span class="sxs-lookup"><span data-stu-id="6139b-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="6139b-166">IVR (réponse vocale Interactive)</span><span class="sxs-lookup"><span data-stu-id="6139b-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="6139b-167">Vous pouvez vous connecter à réponse vocale interactive du partenaire à l’aide de la tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="6139b-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="6139b-168">Une fois que vous êtes dans le partenaire de réponse vocale interactive, vous serez invité à entrer le conferenceId VTC, qui se connectera ensuite à la réunion équipes.</span><span class="sxs-lookup"><span data-stu-id="6139b-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="6139b-169">Appel direct</span><span class="sxs-lookup"><span data-stu-id="6139b-169">Direct dial</span></span>
    - <span data-ttu-id="6139b-170">Vous pouvez directement joindre la réunion équipes sans interaction avec interactive le partenaire à l’aide de la fonctionnalité de numérotation directe à l’aide de la chaîne complète de tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="6139b-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="6139b-171">Numérotation des touches de raccourci</span><span class="sxs-lookup"><span data-stu-id="6139b-171">One-touch dial</span></span>
    - <span data-ttu-id="6139b-172">Si vous disposez d’une salle équipes intégrée, vous pouvez utiliser une touche numérotation fonctionnalités offertes par votre partenaire (sans avoir à taper n’importe quelle chaîne de numérotation).</span><span class="sxs-lookup"><span data-stu-id="6139b-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="6139b-173">Enfin, vous collaborez avec les utilisateurs des équipes dans vos réunions en utilisant le partage audio, vidéo et de contenu.</span><span class="sxs-lookup"><span data-stu-id="6139b-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 