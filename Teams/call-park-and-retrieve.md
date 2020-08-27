---
title: Parcage et récupération d’appel dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: En savoir plus sur l’utilisation du parc d’appels et la récupération pour mettre un appel en attente dans le service équipes du Cloud.
ms.openlocfilehash: 1fddc7acb6d670515fd5903731fab7cacd319f80
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255537"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="6caac-103">Parcage et récupération d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6caac-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="6caac-104">Le parc et la récupération des appels est une fonctionnalité qui permet à un utilisateur de mettre un appel en attente dans le service équipes du Cloud.</span><span class="sxs-lookup"><span data-stu-id="6caac-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="6caac-105">Lorsqu’un appel est parqué, le service génère un code unique pour la récupération des appels.</span><span class="sxs-lookup"><span data-stu-id="6caac-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="6caac-106">L’utilisateur qui a parqué l’appel ou quelqu’un d’autre peut alors utiliser ce code et une application ou un appareil pris en charge pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="6caac-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="6caac-107">Voici quelques-uns des scénarios les plus courants d’utilisation du parc d’appel :</span><span class="sxs-lookup"><span data-stu-id="6caac-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="6caac-108">Un réceptionniste est un appel pour une personne qui travaille dans une fabrique.</span><span class="sxs-lookup"><span data-stu-id="6caac-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="6caac-109">La réceptionniste annonce ensuite l’appel et le numéro de code sur le système d’adresses publiques.</span><span class="sxs-lookup"><span data-stu-id="6caac-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="6caac-110">L’utilisateur pour lequel l’appel est destiné peut alors décrocher un téléphone d’équipe sur le plancher et entrer le code permettant de récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="6caac-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="6caac-111">Un utilisateur a un appel sur un appareil mobile, car la batterie de l’appareil est épuisée.</span><span class="sxs-lookup"><span data-stu-id="6caac-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="6caac-112">L’utilisateur peut ensuite entrer le code permettant de récupérer l’appel à partir d’un téléphone de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="6caac-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="6caac-113">Un représentant du support technique Centre un appel client et envoie une annonce à un canal d’équipe pour permettre à un expert de récupérer l’appel et d’aider le client.</span><span class="sxs-lookup"><span data-stu-id="6caac-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="6caac-114">Un expert entre le code dans les clients teams pour récupérer l’appel</span><span class="sxs-lookup"><span data-stu-id="6caac-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6caac-115">Cette fonctionnalité n’est disponible que dans le mode déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="6caac-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="6caac-116">Pour plus d’informations sur les modes de déploiement d’équipes, voir comprendre les modes de déploiement de [Microsoft teams et de Skype entreprise et l’interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6caac-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="6caac-117">Licence requise</span><span class="sxs-lookup"><span data-stu-id="6caac-117">License required</span></span>

<span data-ttu-id="6caac-118">Pour parcer et récupérer des appels, l’utilisateur doit être un utilisateur d’entreprise voix et un administrateur doit lui accorder une stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="6caac-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="6caac-119">Pour plus d’informations sur le modèle de gestion des licences, voir [Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="6caac-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="6caac-120">Parc d’appels et récupération de la disponibilité des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="6caac-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="6caac-121">Le parc et la récupération des appels sont actuellement pris en charge par les clients et appareils suivants.</span><span class="sxs-lookup"><span data-stu-id="6caac-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="6caac-122">(Pris en charge en mode équipes uniquement, avec ou sans connectivité PSTN.)</span><span class="sxs-lookup"><span data-stu-id="6caac-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="6caac-123">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="6caac-123">Capability</span></span> | <span data-ttu-id="6caac-124">Bureau teams</span><span class="sxs-lookup"><span data-stu-id="6caac-124">Teams Desktop</span></span> | <span data-ttu-id="6caac-125">Application Mac teams</span><span class="sxs-lookup"><span data-stu-id="6caac-125">Teams Mac App</span></span> | <span data-ttu-id="6caac-126">Team Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="6caac-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="6caac-127">Application mobile iOS/Android teams</span><span class="sxs-lookup"><span data-stu-id="6caac-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="6caac-128">Téléphone IP teams</span><span class="sxs-lookup"><span data-stu-id="6caac-128">Teams IP phone</span></span> | <span data-ttu-id="6caac-129">Téléphone IP Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="6caac-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="6caac-130">Parc d’un appel</span><span class="sxs-lookup"><span data-stu-id="6caac-130">Park a call</span></span> | <span data-ttu-id="6caac-131">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-131">Yes</span></span> | <span data-ttu-id="6caac-132">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-132">Yes</span></span> | <span data-ttu-id="6caac-133">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-133">Yes</span></span> | <span data-ttu-id="6caac-134">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-134">Yes</span></span> | <span data-ttu-id="6caac-135">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-135">Yes</span></span> | <span data-ttu-id="6caac-136">Non</span><span class="sxs-lookup"><span data-stu-id="6caac-136">No</span></span> |
| <span data-ttu-id="6caac-137">Extraire un appel parqué</span><span class="sxs-lookup"><span data-stu-id="6caac-137">Retrieve a parked call</span></span> | <span data-ttu-id="6caac-138">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-138">Yes</span></span> | <span data-ttu-id="6caac-139">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-139">Yes</span></span> | <span data-ttu-id="6caac-140">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-140">Yes</span></span> | <span data-ttu-id="6caac-141">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-141">Yes</span></span> | <span data-ttu-id="6caac-142">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-142">Yes</span></span> | <span data-ttu-id="6caac-143">Non</span><span class="sxs-lookup"><span data-stu-id="6caac-143">No</span></span> |
| <span data-ttu-id="6caac-144">Retour de la sonnerie des appels annulé</span><span class="sxs-lookup"><span data-stu-id="6caac-144">Unretrieved call ring back</span></span> | <span data-ttu-id="6caac-145">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-145">Yes</span></span> | <span data-ttu-id="6caac-146">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-146">Yes</span></span> | <span data-ttu-id="6caac-147">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-147">Yes</span></span> | <span data-ttu-id="6caac-148">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-148">Yes</span></span> | <span data-ttu-id="6caac-149">Oui</span><span class="sxs-lookup"><span data-stu-id="6caac-149">Yes</span></span> | <span data-ttu-id="6caac-150">Non</span><span class="sxs-lookup"><span data-stu-id="6caac-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="6caac-151">Configurer le parc d’appels et la récupération</span><span class="sxs-lookup"><span data-stu-id="6caac-151">Configure call park and retrieve</span></span>

<span data-ttu-id="6caac-152">Vous devez être administrateur pour configurer le parc d’appels et la récupération, et la fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="6caac-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="6caac-153">Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="6caac-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="6caac-154">Lorsque vous appliquez la même politique à un ensemble d’utilisateurs, ces derniers peuvent se parcer et récupérer les appels entre eux.</span><span class="sxs-lookup"><span data-stu-id="6caac-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="6caac-155">Pour configurer le parc d’appels pour les utilisateurs et créer des groupes d’utilisateurs de parc d’appels, suivez la procédure [assigner une stratégie de parc d’appels](#assign-a-call-park-policy) ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6caac-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="6caac-156">Pour plus d’informations sur l’utilisation de la fonctionnalité de parc et de récupération d’appel, voir [Park a Call in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="6caac-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="6caac-157">Activer une stratégie de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="6caac-157">Enable a call park policy</span></span>

1. <span data-ttu-id="6caac-158">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies de parc d’appels**vocaux.</span><span class="sxs-lookup"><span data-stu-id="6caac-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="6caac-159">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6caac-159">Select **Add**.</span></span>
3. <span data-ttu-id="6caac-160">Attribuez un nom à la stratégie, puis basculez **autoriser le parc d’appels** sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="6caac-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="6caac-161">Sélectionnez **Save (enregistrer**).</span><span class="sxs-lookup"><span data-stu-id="6caac-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="6caac-162">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="6caac-162">Using PowerShell</span></span>

<span data-ttu-id="6caac-163">Voir [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6caac-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="6caac-164">Modifier une stratégie de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="6caac-164">Edit a call park policy</span></span>

1. <span data-ttu-id="6caac-165">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies de parc d’appels**vocaux.</span><span class="sxs-lookup"><span data-stu-id="6caac-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="6caac-166">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="6caac-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6caac-167">Activez ou **désactivez** l’option autoriser **le** **parc d’appels** .</span><span class="sxs-lookup"><span data-stu-id="6caac-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="6caac-168">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6caac-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="6caac-169">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="6caac-169">Using PowerShell</span></span>

<span data-ttu-id="6caac-170">Voir [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6caac-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="6caac-171">Par exemple, pour modifier le paramètre par défaut, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6caac-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="6caac-172">Assigner une stratégie de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="6caac-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="6caac-173">Voir aussi [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6caac-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6caac-174">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="6caac-174">Troubleshooting</span></span>

<span data-ttu-id="6caac-175">Si les utilisateurs ne peuvent pas voir le bouton parc ou récupérer :</span><span class="sxs-lookup"><span data-stu-id="6caac-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="6caac-176">Vérifiez que la stratégie de parc d’appels est activée pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6caac-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="6caac-177">Si un utilisateur tente de récupérer un appel et échoue, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="6caac-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="6caac-178">Vérifier que l’utilisateur utilise le client teams ou un appareil/téléphone compatible teams</span><span class="sxs-lookup"><span data-stu-id="6caac-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="6caac-179">Regroupement : il s’agit de l’utilisateur membre du groupe de parc d’appels, qui est basé sur le fait que la même stratégie de parc d’appels d’équipes est affectée.</span><span class="sxs-lookup"><span data-stu-id="6caac-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="6caac-180">Mode île : le parc d’appels et la récupération ne sont pas disponibles en mode îlot d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6caac-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="6caac-181">L’appel a déjà été récupéré ou arrêté.</span><span class="sxs-lookup"><span data-stu-id="6caac-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6caac-182">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6caac-182">Related topics</span></span>

[<span data-ttu-id="6caac-183">Park a Call en teams</span><span class="sxs-lookup"><span data-stu-id="6caac-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="6caac-184">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="6caac-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
