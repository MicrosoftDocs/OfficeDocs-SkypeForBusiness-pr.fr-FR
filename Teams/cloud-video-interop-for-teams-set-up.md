---
title: Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: Cet article décrit la planification et la configuration de l’interopérabilité Cloud Video pour les utilisateurs de votre organisation.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e91b0e25a7844634577083b26d74a48c788bc45b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237051"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="81d35-103">Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81d35-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="81d35-104">Une fois que vous avez [choisi sur votre ou vos partenaires d’interopérabilité Cloud Video](cloud-video-interop.md), vous devez planifier votre déploiement, se préparer à l’aide des détails de mise en service et de la clé de client partenaire et consent à l’application d’interopérabilité vidéo de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81d35-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="81d35-105">Le schéma suivant décrit le processus.</span><span class="sxs-lookup"><span data-stu-id="81d35-105">The following diagram outlines the process.</span></span> 

![Déploiement d’CVI au sein de votre organisation](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="81d35-107">Plan</span><span class="sxs-lookup"><span data-stu-id="81d35-107">Plan</span></span>

<span data-ttu-id="81d35-108">Pour plus d’informations sur l’identification d’un partenaire ou partenaire à utiliser au sein de votre organisation, voir [interopérabilité Cloud pour Microsoft teams](cloud-video-interop.md) .</span><span class="sxs-lookup"><span data-stu-id="81d35-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="81d35-109">Pour planifier l’activation basée sur le niveau d’utilisation/le site, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="81d35-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="81d35-110">Sélectionner un modèle de déploiement/un modèle hébergé pour votre utilisation</span><span class="sxs-lookup"><span data-stu-id="81d35-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="81d35-111">Sélectionnez le plan de licence idéal pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81d35-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="81d35-112">Vous pouvez planifier la capacité des VM pour votre infrastructure vidéo.</span><span class="sxs-lookup"><span data-stu-id="81d35-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="81d35-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="81d35-113">Configure</span></span> 

<span data-ttu-id="81d35-114">Pour configurer le Cloud Video Interop, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="81d35-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="81d35-115">Obtenez les informations de configuration des partenaires/partenaires que vous avez choisis (clé de client, AppID...).</span><span class="sxs-lookup"><span data-stu-id="81d35-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="81d35-116">Vous pouvez utiliser un ou plusieurs partenaires d’interopérabilité vidéo au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81d35-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="81d35-117">Assurez-vous que votre réseau est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="81d35-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="81d35-118">Configurez votre pare-feu vidéo standard pour la prise en charge du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="81d35-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="81d35-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="81d35-119">For example:</span></span> 
    - <span data-ttu-id="81d35-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="81d35-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="81d35-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="81d35-121">Polycom RPAD</span></span>

3. <span data-ttu-id="81d35-122">Configurez les salles intégrées avec Exchange et OTD.</span><span class="sxs-lookup"><span data-stu-id="81d35-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="81d35-123">Dans la plupart des cas, il est nécessaire de configurer et de configurer un relais supplémentaire dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="81d35-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="81d35-124">Octroi</span><span class="sxs-lookup"><span data-stu-id="81d35-124">Provision</span></span>
 
<span data-ttu-id="81d35-125">La clé de locataire sera le numéro de connexion au service partenaire.</span><span class="sxs-lookup"><span data-stu-id="81d35-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="81d35-126">Dans l’exemple suivant, 813878896@t.plcm.vc est la clé de client.</span><span class="sxs-lookup"><span data-stu-id="81d35-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Exemple de clé de client](media/tenant-key-example.png) 

<span data-ttu-id="81d35-128">Vous devez exécuter les applets de commande suivantes pour mettre en service la clé de client et permettre à certains utilisateurs ou à votre organisation de créer des réunions avec des coordonnées d’interopérabilité vidéo.</span><span class="sxs-lookup"><span data-stu-id="81d35-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="81d35-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft fournit des stratégies préconçues pour chacun de nos partenaires pris en charge, qui vous permettent de désigner le ou les partenaires à utiliser pour l’interopérabilité de la vidéo Cloud.</span><span class="sxs-lookup"><span data-stu-id="81d35-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="81d35-130">Cette applet de connexion vous permet d’identifier les politiques prédéfinies que vous pouvez utiliser au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81d35-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="81d35-131">Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l’applet de passe Grant-CsTeamsVideoInteropServicePolicy.</span><span class="sxs-lookup"><span data-stu-id="81d35-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="81d35-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* L’applet de connexion Grant-CsTeamsVideoInteropServicePolicy vous permet d’affecter une stratégie prédéfinie à utiliser au sein de votre organisation ou de l’affecter à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="81d35-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="81d35-133">\*\* [Nouveau-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Utilisez le nouveau-CsVideoInteropServiceProvider pour spécifier les informations relatives à un partenaire CVI pris en charge que votre organisation souhaite utiliser.</span><span class="sxs-lookup"><span data-stu-id="81d35-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="81d35-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Utilisez la CsVideoInteropServiceProvider pour mettre à jour les informations relatives à un partenaire CVI pris en charge que votre organisation utilise.</span><span class="sxs-lookup"><span data-stu-id="81d35-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="81d35-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Obtenir tous les fournisseurs configurés pour une utilisation au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="81d35-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="81d35-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Utilisez Remove-CsVideoInteropServiceProvider pour supprimer toutes les informations de fournisseur relatives à un fournisseur que votre organisation n’utilise plus.</span><span class="sxs-lookup"><span data-stu-id="81d35-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="81d35-137">Consentement</span><span class="sxs-lookup"><span data-stu-id="81d35-137">Consent</span></span>

<span data-ttu-id="81d35-138">Vous devez fournir le consentement d’autorisation pour les appareils de visioconférence vidéo (VTCs) pour rejoindre les réunions de votre organisation via le service partenaire.</span><span class="sxs-lookup"><span data-stu-id="81d35-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="81d35-139">Ce lien de consentement sera également fourni par votre partenaire.</span><span class="sxs-lookup"><span data-stu-id="81d35-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="81d35-140">Une fois ces étapes terminées, les utilisateurs qui sont activés individuellement par le biais de l’applet de contrôle Grant ci-dessus, ou tous les utilisateurs de l’organisation si le client est activé, auront des coordonnées VTC dans toutes les réunions teams qu’ils emploient.</span><span class="sxs-lookup"><span data-stu-id="81d35-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="81d35-141">Tout VTC peut rejoindre ces réunions par le biais de ces coordonnées.</span><span class="sxs-lookup"><span data-stu-id="81d35-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="81d35-142">Nom</span><span class="sxs-lookup"><span data-stu-id="81d35-142">Name</span></span>|<span data-ttu-id="81d35-143">Brève description de l’autorisation d’application</span><span class="sxs-lookup"><span data-stu-id="81d35-143">Application Permission Short Description</span></span>| <span data-ttu-id="81d35-144">Description</span><span class="sxs-lookup"><span data-stu-id="81d35-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="81d35-145">Appels. JoinGroupCall. All</span><span class="sxs-lookup"><span data-stu-id="81d35-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="81d35-146">Joindre des appels de groupe et des réunions en tant qu’application (Preview)</span><span class="sxs-lookup"><span data-stu-id="81d35-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="81d35-147">Autorise l’application à rejoindre les appels de groupe et les réunions planifiées au sein de votre organisation, sans utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="81d35-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="81d35-148">L’application sera associée aux privilèges d’un utilisateur d’annuaire pour les réunions de votre client.</span><span class="sxs-lookup"><span data-stu-id="81d35-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="81d35-149">Appels. JoinGroupCallasGuest. All</span><span class="sxs-lookup"><span data-stu-id="81d35-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="81d35-150">Joindre des appels de groupe et des réunions en tant qu’utilisateur invité (Preview)</span><span class="sxs-lookup"><span data-stu-id="81d35-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="81d35-151">Permet à l’application de joindre anonymement des appels de groupe et des réunions planifiées au sein de votre organisation, sans utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="81d35-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="81d35-152">L’application sera associée en tant qu’invité à des réunions de votre client.</span><span class="sxs-lookup"><span data-stu-id="81d35-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="81d35-153">Appels. AccessMedia. All</span><span class="sxs-lookup"><span data-stu-id="81d35-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="81d35-154">Accéder aux flux multimédias dans un appel en tant qu’application (Preview)</span><span class="sxs-lookup"><span data-stu-id="81d35-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="81d35-155">Autorise l’application à accéder directement aux flux multimédias pendant un appel, sans utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="81d35-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="81d35-156">OnlineMeetings. Read. All</span><span class="sxs-lookup"><span data-stu-id="81d35-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="81d35-157">Lire les détails d’une réunion en ligne (Preview)</span><span class="sxs-lookup"><span data-stu-id="81d35-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="81d35-158">Permet à l’application de lire les détails d’une réunion en ligne au sein de votre organisation, sans utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="81d35-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="81d35-159">Horaire</span><span class="sxs-lookup"><span data-stu-id="81d35-159">Schedule</span></span>

<span data-ttu-id="81d35-160">Ensuite, planifiez une réunion en équipe avec des coordonnées d’interopérabilité vidéo.</span><span class="sxs-lookup"><span data-stu-id="81d35-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="81d35-161">L’utilisateur activé peut planifier des réunions d’équipes par le biais de:</span><span class="sxs-lookup"><span data-stu-id="81d35-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="81d35-162">Complément réunion teams pour Outlook</span><span class="sxs-lookup"><span data-stu-id="81d35-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="81d35-163">Bureau et appareil mobile teams</span><span class="sxs-lookup"><span data-stu-id="81d35-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="81d35-164">Rejoindre</span><span class="sxs-lookup"><span data-stu-id="81d35-164">Join</span></span>

<span data-ttu-id="81d35-165">Vous pouvez participer à des réunions d’équipes à l’aide de vos appareils VTC comme suit:</span><span class="sxs-lookup"><span data-stu-id="81d35-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="81d35-166">IVR (réponse vocale interactive)</span><span class="sxs-lookup"><span data-stu-id="81d35-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="81d35-167">Vous pouvez vous connecter à l’IVR du partenaire à l’aide du tenantkey @ Domain.</span><span class="sxs-lookup"><span data-stu-id="81d35-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="81d35-168">Une fois que vous avez été dans le partenaire IVR, vous êtes invité à entrer le conferenceId VTC, qui vous connecte ensuite à la réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="81d35-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="81d35-169">Numérotation directe</span><span class="sxs-lookup"><span data-stu-id="81d35-169">Direct dial</span></span>
    - <span data-ttu-id="81d35-170">Vous pouvez accéder directement à la réunion teams sans interagir avec le son de votre partenaire à l’aide de la fonction de numérotation directe qui utilise la chaîne complète de tenantkey. VTC ConferenceId @ Domain.</span><span class="sxs-lookup"><span data-stu-id="81d35-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="81d35-171">Numérotation en un clic</span><span class="sxs-lookup"><span data-stu-id="81d35-171">One-touch dial</span></span>
    - <span data-ttu-id="81d35-172">Si vous avez une salle d’équipe intégrée, vous pouvez utiliser les fonctionnalités de numérotation à l’aide de votre partenaire (sans avoir à taper une chaîne de numérotation).</span><span class="sxs-lookup"><span data-stu-id="81d35-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="81d35-173">Enfin, vous collaborez avec les utilisateurs de teams dans vos réunions à l’aide du son, de la vidéo et du partage de contenu.</span><span class="sxs-lookup"><span data-stu-id="81d35-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 