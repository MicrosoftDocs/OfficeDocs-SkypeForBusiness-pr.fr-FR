---
title: Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Cet article explique comment planifier et configurer Cloud Video Interop pour les utilisateurs de votre organisation.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102600"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="0ee96-103">Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ee96-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="0ee96-104">Une fois que vous avez choisi votre ou vos partenaires [Cloud Video Interop,](cloud-video-interop.md)vous devez planifier votre déploiement, configurer avec les détails de mise en service et la clé de client partenaire, et donner votre consentement à l’application d’interop vidéo dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0ee96-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="0ee96-105">Le diagramme suivant décrit le processus.</span><span class="sxs-lookup"><span data-stu-id="0ee96-105">The following diagram outlines the process.</span></span> 

![Déploiement de CVI dans votre organisation](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="0ee96-107">Plan</span><span class="sxs-lookup"><span data-stu-id="0ee96-107">Plan</span></span>

<span data-ttu-id="0ee96-108">Pour [plus d’informations sur l’Microsoft Teams](cloud-video-interop.md) d’identification d’un partenaire ou partenaire à utiliser dans votre organisation, voir Cloud Video Interop.</span><span class="sxs-lookup"><span data-stu-id="0ee96-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="0ee96-109">Pour planifier l’enablement à l’échelle de l’utilisateur, des concurrents/des sites :</span><span class="sxs-lookup"><span data-stu-id="0ee96-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="0ee96-110">Sélectionner un modèle de déploiement/hébergé pour votre utilisation</span><span class="sxs-lookup"><span data-stu-id="0ee96-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="0ee96-111">Sélectionnez le plan de licences idéal pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0ee96-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="0ee96-112">La capacité des VMs est que vous hébergez votre infrastructure vidéo.</span><span class="sxs-lookup"><span data-stu-id="0ee96-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="0ee96-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="0ee96-113">Configure</span></span> 

<span data-ttu-id="0ee96-114">Pour configurer Cloud Video Interop, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="0ee96-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="0ee96-115">Obtenez des informations de configuration auprès du partenaire/partenaire que vous avez choisi (clé client, appIds, etc.).</span><span class="sxs-lookup"><span data-stu-id="0ee96-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="0ee96-116">Vous pouvez utiliser un ou plusieurs partenaires d’interop vidéo dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="0ee96-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="0ee96-117">Assurez-vous que votre réseau est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="0ee96-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="0ee96-118">Configurez votre pare-feu vidéo basé sur les normes pour le travers de réseau de périmètre à prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="0ee96-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="0ee96-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0ee96-119">For example:</span></span> 
    - <span data-ttu-id="0ee96-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="0ee96-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="0ee96-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="0ee96-121">Polycom RPAD</span></span>

3. <span data-ttu-id="0ee96-122">Configurez des salles intégrées avec Exchange et OTD.</span><span class="sxs-lookup"><span data-stu-id="0ee96-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="0ee96-123">Dans la plupart des cas, un relais supplémentaire doit être configuré dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="0ee96-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="0ee96-124">Approvisionnement</span><span class="sxs-lookup"><span data-stu-id="0ee96-124">Provision</span></span>
 
<span data-ttu-id="0ee96-125">La clé client sera l’appel sortant vers le service partenaire.</span><span class="sxs-lookup"><span data-stu-id="0ee96-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="0ee96-126">Dans l’exemple suivant, 813878896@t.plcm.vc est la clé client.</span><span class="sxs-lookup"><span data-stu-id="0ee96-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Exemple de clé de client](media/tenant-key-example.png) 

<span data-ttu-id="0ee96-128">Vous devrez exécuter les cmdlets suivantes pour mettre en service la clé client et permettre également à certains utilisateurs ou à l’ensemble de votre organisation de créer des réunions avec des coordonnées d’interop vidéo.</span><span class="sxs-lookup"><span data-stu-id="0ee96-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="0ee96-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft fournit des stratégies prédécoupées pour chacun de nos partenaires pris en charge qui vous permettent de désigner le ou les partenaires à utiliser pour interop vidéo cloud.</span><span class="sxs-lookup"><span data-stu-id="0ee96-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="0ee96-130">Cette cmdlet vous permet d’identifier les stratégies pré-construite que vous pouvez utiliser dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0ee96-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="0ee96-131">Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l'Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0ee96-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="0ee96-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** LGrant-CsTeamsVideoInteropServicePolicy cmdlet vous permet d’affecter une stratégie précont enfantin à utiliser dans votre organisation ou d’affecter la stratégie à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0ee96-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="0ee96-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Utilisez le New-CsVideoInteropServiceProvider pour spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.</span><span class="sxs-lookup"><span data-stu-id="0ee96-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="0ee96-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Utilisez le Set-CsVideoInteropServiceProvider pour mettre à jour les informations sur un partenaire CVI pris en charge par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0ee96-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="0ee96-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenez tous les fournisseurs configurés pour une utilisation au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="0ee96-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="0ee96-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Utilisez Remove-CsVideoInteropServiceProvider pour supprimer toutes les informations de fournisseur concernant un fournisseur que votre organisation n’utilise plus.</span><span class="sxs-lookup"><span data-stu-id="0ee96-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="0ee96-137">Consentement</span><span class="sxs-lookup"><span data-stu-id="0ee96-137">Consent</span></span>

<span data-ttu-id="0ee96-138">Vous devrez fournir l’autorisation d’autoriser les périphériques de téléconférence vidéo (VCS) à rejoindre les réunions de votre organisation via le service partenaire.</span><span class="sxs-lookup"><span data-stu-id="0ee96-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="0ee96-139">Ce lien d’accord sera également fourni par votre partenaire.</span><span class="sxs-lookup"><span data-stu-id="0ee96-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="0ee96-140">Une fois ces étapes terminées, les utilisateurs activés individuellement via l’cmdlet Grant ci-dessus, ou tous les utilisateurs de l’organisation si le client est activé, auront des coordonnées VTC dans toutes les réunions Teams qu’ils ont prévues.</span><span class="sxs-lookup"><span data-stu-id="0ee96-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="0ee96-141">N’importe quel VTC peut participer à ces réunions via ces coordonnées.</span><span class="sxs-lookup"><span data-stu-id="0ee96-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="0ee96-142">Nom</span><span class="sxs-lookup"><span data-stu-id="0ee96-142">Name</span></span>|<span data-ttu-id="0ee96-143">Courte description des autorisations d’application</span><span class="sxs-lookup"><span data-stu-id="0ee96-143">Application Permission Short Description</span></span>| <span data-ttu-id="0ee96-144">Description</span><span class="sxs-lookup"><span data-stu-id="0ee96-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="0ee96-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="0ee96-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="0ee96-146">Rejoindre des appels de groupe et des réunions en tant qu’application (aperçu)</span><span class="sxs-lookup"><span data-stu-id="0ee96-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="0ee96-147">Permet à l’application de participer à des appels de groupe et à des réunions programmées dans votre organisation, sans qu’un utilisateur ne soit inscrit.</span><span class="sxs-lookup"><span data-stu-id="0ee96-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="0ee96-148">L’application sera jointe avec les privilèges d’un utilisateur de l’annuaire pour les réunions dans votre client.</span><span class="sxs-lookup"><span data-stu-id="0ee96-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="0ee96-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="0ee96-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="0ee96-150">Rejoindre des appels de groupe et des réunions en tant qu’utilisateur invité (prévisualisation)</span><span class="sxs-lookup"><span data-stu-id="0ee96-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="0ee96-151">Permet à l’application de participer de manière anonyme à des appels de groupe et à des réunions programmées dans votre organisation, sans qu’un utilisateur ne soit inscrit.</span><span class="sxs-lookup"><span data-stu-id="0ee96-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="0ee96-152">L’application sera jointe en tant qu’invité aux réunions dans votre client.</span><span class="sxs-lookup"><span data-stu-id="0ee96-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="0ee96-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="0ee96-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="0ee96-154">Accéder aux flux multimédias dans un appel en tant qu’application (aperçu)</span><span class="sxs-lookup"><span data-stu-id="0ee96-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="0ee96-155">Permet à l’application d’accéder directement aux flux multimédias dans un appel, sans utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="0ee96-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="0ee96-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="0ee96-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="0ee96-157">Lire les détails de la réunion en ligne (aperçu)</span><span class="sxs-lookup"><span data-stu-id="0ee96-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="0ee96-158">Permet à l’application de lire les détails de la réunion en ligne dans votre organisation, sans utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="0ee96-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="0ee96-159">Planifier</span><span class="sxs-lookup"><span data-stu-id="0ee96-159">Schedule</span></span>

<span data-ttu-id="0ee96-160">Ensuite, planifier Teams réunion avec les coordonnées d’interopation vidéo.</span><span class="sxs-lookup"><span data-stu-id="0ee96-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="0ee96-161">L’utilisateur activé peut planifier des réunions d’équipe via :</span><span class="sxs-lookup"><span data-stu-id="0ee96-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="0ee96-162">Teams Le add-in de réunion pour Outlook</span><span class="sxs-lookup"><span data-stu-id="0ee96-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="0ee96-163">Teams bureau et mobile client</span><span class="sxs-lookup"><span data-stu-id="0ee96-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="0ee96-164">Rejoindre</span><span class="sxs-lookup"><span data-stu-id="0ee96-164">Join</span></span>

<span data-ttu-id="0ee96-165">Vous pouvez participer Teams réunions avec vos appareils VTC des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="0ee96-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="0ee96-166">IVR (Réponse vocale interactive)</span><span class="sxs-lookup"><span data-stu-id="0ee96-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="0ee96-167">Vous pouvez appeler les IVR du partenaire à l’aide de la tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="0ee96-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="0ee96-168">Une fois que vous êtes dans l’IVR partenaire, vous êtes invité à entrer le VTC conferenceId, qui vous connecte ensuite à la Teams partenaire.</span><span class="sxs-lookup"><span data-stu-id="0ee96-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="0ee96-169">Numérotation directe</span><span class="sxs-lookup"><span data-stu-id="0ee96-169">Direct dial</span></span>
    - <span data-ttu-id="0ee96-170">Vous pouvez appeler directement la réunion Teams sans interagir avec les IVR du partenaire à l’aide de la fonctionnalité de numérotation directe utilisant la chaîne complète de clés client. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="0ee96-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="0ee96-171">Numérotation à une pression</span><span class="sxs-lookup"><span data-stu-id="0ee96-171">One-touch dial</span></span>
    - <span data-ttu-id="0ee96-172">Si vous avez une salle de numérotation Teams intégrée, vous pouvez utiliser les fonctionnalités de numérotation à une pression offertes par votre partenaire (sans avoir à taper de chaîne de numérotation).</span><span class="sxs-lookup"><span data-stu-id="0ee96-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="0ee96-173">Enfin, engagez-vous Teams vos réunions en utilisant l’audio, la vidéo et le partage de contenu.</span><span class="sxs-lookup"><span data-stu-id="0ee96-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span>