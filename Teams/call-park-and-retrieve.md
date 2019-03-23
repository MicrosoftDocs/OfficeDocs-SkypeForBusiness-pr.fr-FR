---
title: Parcage et récupération d’appel dans Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 01/16/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Utilisez parcage d’appel et de récupération pour passer un appel en attente dans le service d’équipes dans le nuage.
ms.openlocfilehash: 416458b1f7c134fca3294107bd82bbd0f2300abc
ms.sourcegitcommit: 5ed00e911a151d3ab834528f121db8653c25dc12
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747653"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="8a28a-103">Parcage et récupération d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a28a-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="8a28a-104">Mise en garde d’appels et de récupération est une fonctionnalité qui permet à un utilisateur de passer un appel en attente dans le service d’équipes dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="8a28a-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="8a28a-105">Lors de la mise en garde un appel, le service génère un code unique pour la récupération de l’appel.</span><span class="sxs-lookup"><span data-stu-id="8a28a-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="8a28a-106">L’utilisateur qui a été mis en garde l’appel ou une autre personne peut ensuite utiliser ce code et une applications pris en charge ou périphérique pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="8a28a-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="8a28a-107">Les scénarios courants d’utilisation de parcage d’appel sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="8a28a-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="8a28a-108">Un réceptionniste parcs élevage un appel d’une personne travaillant dans une fabrique.</span><span class="sxs-lookup"><span data-stu-id="8a28a-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="8a28a-109">Le réceptionniste annonce puis l’appel et le numéro de code dans le système.</span><span class="sxs-lookup"><span data-stu-id="8a28a-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="8a28a-110">L’utilisateur pour l’appel peut sélectionner un téléphone équipes en usine, puis entrez le code pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="8a28a-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="8a28a-111">Un utilisateur parcs élevage un appel sur un appareil mobile, car la batterie de l’appareil manque d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="8a28a-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="8a28a-112">L’utilisateur peut entrer puis de code pour récupérer l’appel à partir d’un téléphone de bureau équipes.</span><span class="sxs-lookup"><span data-stu-id="8a28a-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="8a28a-113">Un parcs représentant prise en charge un client d’appel et envoie une annonce sur un canal d’équipes pour récupérer l’appel et aider le client à un expert.</span><span class="sxs-lookup"><span data-stu-id="8a28a-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="8a28a-114">Un expert entre le code dans les clients des équipes pour récupérer l’appel</span><span class="sxs-lookup"><span data-stu-id="8a28a-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a28a-115">Cette fonctionnalité est uniquement disponible en mode de déploiement équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="8a28a-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="8a28a-116">Pour plus d’informations sur les modes de déploiement d’équipes, voir [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="8a28a-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="8a28a-117">Licence requise</span><span class="sxs-lookup"><span data-stu-id="8a28a-117">License required</span></span>

<span data-ttu-id="8a28a-118">Pour mettre en garde et récupérer des appels, l’utilisateur doit être un utilisateur Enterprise Voice et un administrateur doit accorder à l’utilisateur une stratégie de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="8a28a-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="8a28a-119">Pour plus d’informations sur le modèle de licence, voir [Gestion des licences Office 365 pour les équipes Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8a28a-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="8a28a-120">Le parcage d’appel et de récupérer la disponibilité des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="8a28a-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="8a28a-121">Parcage d’appel et de récupérer est actuellement pris en charge par les périphériques clients suivants.</span><span class="sxs-lookup"><span data-stu-id="8a28a-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="8a28a-122">(Pris en charge en mode équipes uniquement, avec ou sans connectivité PSTN).</span><span class="sxs-lookup"><span data-stu-id="8a28a-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="8a28a-123">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="8a28a-123">Capability</span></span> | <span data-ttu-id="8a28a-124">Bureau des équipes</span><span class="sxs-lookup"><span data-stu-id="8a28a-124">Teams Desktop</span></span> | <span data-ttu-id="8a28a-125">Les équipes Mac application</span><span class="sxs-lookup"><span data-stu-id="8a28a-125">Teams Mac App</span></span> | <span data-ttu-id="8a28a-126">Les équipes Web App (périmètre)</span><span class="sxs-lookup"><span data-stu-id="8a28a-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="8a28a-127">Les équipes mobile iOS/Android application</span><span class="sxs-lookup"><span data-stu-id="8a28a-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="8a28a-128">Téléphone IP d’équipes</span><span class="sxs-lookup"><span data-stu-id="8a28a-128">Teams IP phone</span></span> | <span data-ttu-id="8a28a-129">Skype pour téléphone IP d’entreprise</span><span class="sxs-lookup"><span data-stu-id="8a28a-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="8a28a-130">Mise en garde d’un appel</span><span class="sxs-lookup"><span data-stu-id="8a28a-130">Park a call</span></span> | <span data-ttu-id="8a28a-131">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-131">Yes</span></span> | <span data-ttu-id="8a28a-132">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-132">Yes</span></span> | <span data-ttu-id="8a28a-133">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-133">Yes</span></span> | <span data-ttu-id="8a28a-134">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-134">Yes</span></span> | <span data-ttu-id="8a28a-135">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="8a28a-135">Coming soon</span></span>| <span data-ttu-id="8a28a-136">Non</span><span class="sxs-lookup"><span data-stu-id="8a28a-136">No</span></span> |
| <span data-ttu-id="8a28a-137">Récupérer un appel mis en garde</span><span class="sxs-lookup"><span data-stu-id="8a28a-137">Retrieve a parked call</span></span> | <span data-ttu-id="8a28a-138">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-138">Yes</span></span> | <span data-ttu-id="8a28a-139">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-139">Yes</span></span> | <span data-ttu-id="8a28a-140">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-140">Yes</span></span> | <span data-ttu-id="8a28a-141">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-141">Yes</span></span> | <span data-ttu-id="8a28a-142">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="8a28a-142">Coming soon</span></span>| <span data-ttu-id="8a28a-143">Non</span><span class="sxs-lookup"><span data-stu-id="8a28a-143">No</span></span> |
| <span data-ttu-id="8a28a-144">Sonnerie d’appel non récupérées précédent</span><span class="sxs-lookup"><span data-stu-id="8a28a-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="8a28a-145">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-145">Yes</span></span> | <span data-ttu-id="8a28a-146">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-146">Yes</span></span> | <span data-ttu-id="8a28a-147">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-147">Yes</span></span> | <span data-ttu-id="8a28a-148">Oui</span><span class="sxs-lookup"><span data-stu-id="8a28a-148">Yes</span></span> | <span data-ttu-id="8a28a-149">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="8a28a-149">Coming soon</span></span>| <span data-ttu-id="8a28a-150">Non</span><span class="sxs-lookup"><span data-stu-id="8a28a-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="8a28a-151">Configuration de mise en garde d’appels et de récupération</span><span class="sxs-lookup"><span data-stu-id="8a28a-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="8a28a-152">Vous devez être un administrateur de configurer la mise en garde d’appels et de récupération, et la fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="8a28a-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="8a28a-153">Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="8a28a-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="8a28a-154">Lorsque vous appliquez la même stratégie à un ensemble d’utilisateurs, ils seront en mesure de mettre en garde et récupérer des appels entre eux.</span><span class="sxs-lookup"><span data-stu-id="8a28a-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="8a28a-155">Pour configurer la mise en garde d’appels pour les utilisateurs et créer des groupes d’utilisateurs appel park, suivez la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8a28a-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="8a28a-156">Pour plus d’informations sur la façon d’utiliser la mise en garde d’appels et de récupérer la fonctionnalité, voir [mise en garde d’un appel en équipe](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="8a28a-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="8a28a-157">Affecter une stratégie de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="8a28a-157">Assign a call park policy</span></span>

<span data-ttu-id="8a28a-158">Suivez ces étapes pour affecter une stratégie de parcage d’appel à un ou plusieurs utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="8a28a-158">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="8a28a-159">Accédez au **Centre d’administration de Microsoft équipes** > **vocale** > **stratégies parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="8a28a-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="8a28a-160">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="8a28a-160">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="8a28a-161">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="8a28a-161">Select **Manage users**.</span></span>
4. <span data-ttu-id="8a28a-162">Dans le volet **Gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par un nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8a28a-162">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="8a28a-163">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="8a28a-163">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="8a28a-164">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8a28a-164">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="8a28a-165">Configurer la mise en garde d’appels et récupérer l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a28a-165">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="8a28a-166">Utilisez l’applet de commande PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) pour créer une stratégie de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="8a28a-166">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="8a28a-167">Utilisez l’applet de commande PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) pour accorder une stratégie de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="8a28a-167">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="8a28a-168">Vous pouvez modifier le paramètre par défaut à l’aide de [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) comme suit :</span><span class="sxs-lookup"><span data-stu-id="8a28a-168">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="8a28a-169">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="8a28a-169">Troubleshooting</span></span>

<span data-ttu-id="8a28a-170">Si les utilisateurs ne peuvent pas voir le parc ou récupérer le bouton :</span><span class="sxs-lookup"><span data-stu-id="8a28a-170">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="8a28a-171">Vérifiez que l’utilisateur dispose de la stratégie de parcage d’appel activée.</span><span class="sxs-lookup"><span data-stu-id="8a28a-171">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="8a28a-172">Si un utilisateur tente de récupérer un appel échoue, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="8a28a-172">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="8a28a-173">Vérifiez que l’utilisateur utilise le client équipes ou un téléphone/appareil prenant en charge les équipes</span><span class="sxs-lookup"><span data-stu-id="8a28a-173">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="8a28a-174">Regroupement – est l’utilisateur membre du groupe de parcage d’appel ?</span><span class="sxs-lookup"><span data-stu-id="8a28a-174">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="8a28a-175">Mode (îles) – mise en garde d’appels et de récupération n’est pas disponible en mode îlot d’équipes.</span><span class="sxs-lookup"><span data-stu-id="8a28a-175">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="8a28a-176">L’appel a déjà été récupéré ou interrompue.</span><span class="sxs-lookup"><span data-stu-id="8a28a-176">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="8a28a-177">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="8a28a-177">More information</span></span>

<span data-ttu-id="8a28a-178">[Mise en garde d’un appel en équipe](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="8a28a-178">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>