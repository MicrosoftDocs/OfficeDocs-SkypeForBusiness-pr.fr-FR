---
title: Parcage et récupération d’appel dans Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
description: Utiliser le parc d’appels et la récupération pour mettre un appel en attente dans le service équipes du Cloud.
ms.openlocfilehash: b4b5200f139f5610ff1109b97742607d3b633ff6
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824592"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="e9f4c-103">Parcage et récupération d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9f4c-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="e9f4c-104">Le parc et la récupération des appels est une fonctionnalité qui permet à un utilisateur de mettre un appel en attente dans le service équipes du Cloud.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="e9f4c-105">Lorsqu’un appel est parqué, le service génère un code unique pour la récupération des appels.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="e9f4c-106">L’utilisateur qui a parqué l’appel ou quelqu’un d’autre peut alors utiliser ce code et une application ou un appareil pris en charge pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="e9f4c-107">Voici quelques-uns des scénarios les plus courants d’utilisation du parc d’appel :</span><span class="sxs-lookup"><span data-stu-id="e9f4c-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="e9f4c-108">Un réceptionniste est un appel pour une personne qui travaille dans une fabrique.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="e9f4c-109">La réceptionniste annonce ensuite l’appel et le numéro de code sur le système d’adresses publiques.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="e9f4c-110">L’utilisateur pour lequel l’appel est destiné peut alors décrocher un téléphone d’équipe sur le plancher et entrer le code permettant de récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="e9f4c-111">Un utilisateur a un appel sur un appareil mobile, car la batterie de l’appareil est épuisée.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="e9f4c-112">L’utilisateur peut ensuite entrer le code permettant de récupérer l’appel à partir d’un téléphone de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="e9f4c-113">Un représentant du support technique Centre un appel client et envoie une annonce à un canal d’équipe pour permettre à un expert de récupérer l’appel et d’aider le client.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="e9f4c-114">Un expert entre le code dans les clients teams pour récupérer l’appel</span><span class="sxs-lookup"><span data-stu-id="e9f4c-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9f4c-115">Cette fonctionnalité n’est disponible que dans le mode déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="e9f4c-116">Pour plus d’informations sur les modes de déploiement d’équipes, voir comprendre les modes de déploiement de [Microsoft teams et de Skype entreprise et l’interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="e9f4c-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="e9f4c-117">Licence requise</span><span class="sxs-lookup"><span data-stu-id="e9f4c-117">License required</span></span>

<span data-ttu-id="e9f4c-118">Pour parcer et récupérer des appels, l’utilisateur doit être un utilisateur d’entreprise voix et un administrateur doit lui accorder une stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="e9f4c-119">Pour plus d’informations sur le modèle de gestion des licences, voir gestion [des licences Office 365 pour Microsoft teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e9f4c-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="e9f4c-120">Parc d’appels et récupération de la disponibilité des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="e9f4c-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="e9f4c-121">Le parc et la récupération des appels sont actuellement pris en charge par les clients et appareils suivants.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="e9f4c-122">(Pris en charge en mode équipes uniquement, avec ou sans connectivité PSTN.)</span><span class="sxs-lookup"><span data-stu-id="e9f4c-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="e9f4c-123">Faculté</span><span class="sxs-lookup"><span data-stu-id="e9f4c-123">Capability</span></span> | <span data-ttu-id="e9f4c-124">Bureau teams</span><span class="sxs-lookup"><span data-stu-id="e9f4c-124">Teams Desktop</span></span> | <span data-ttu-id="e9f4c-125">Application Mac teams</span><span class="sxs-lookup"><span data-stu-id="e9f4c-125">Teams Mac App</span></span> | <span data-ttu-id="e9f4c-126">Team Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="e9f4c-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="e9f4c-127">Application mobile iOS/Android teams</span><span class="sxs-lookup"><span data-stu-id="e9f4c-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="e9f4c-128">Téléphone IP teams</span><span class="sxs-lookup"><span data-stu-id="e9f4c-128">Teams IP phone</span></span> | <span data-ttu-id="e9f4c-129">Téléphone IP Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="e9f4c-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="e9f4c-130">Parc d’un appel</span><span class="sxs-lookup"><span data-stu-id="e9f4c-130">Park a call</span></span> | <span data-ttu-id="e9f4c-131">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-131">Yes</span></span> | <span data-ttu-id="e9f4c-132">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-132">Yes</span></span> | <span data-ttu-id="e9f4c-133">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-133">Yes</span></span> | <span data-ttu-id="e9f4c-134">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-134">Yes</span></span> | <span data-ttu-id="e9f4c-135">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="e9f4c-135">Coming soon</span></span>| <span data-ttu-id="e9f4c-136">Non</span><span class="sxs-lookup"><span data-stu-id="e9f4c-136">No</span></span> |
| <span data-ttu-id="e9f4c-137">Extraire un appel parqué</span><span class="sxs-lookup"><span data-stu-id="e9f4c-137">Retrieve a parked call</span></span> | <span data-ttu-id="e9f4c-138">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-138">Yes</span></span> | <span data-ttu-id="e9f4c-139">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-139">Yes</span></span> | <span data-ttu-id="e9f4c-140">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-140">Yes</span></span> | <span data-ttu-id="e9f4c-141">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-141">Yes</span></span> | <span data-ttu-id="e9f4c-142">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="e9f4c-142">Coming soon</span></span>| <span data-ttu-id="e9f4c-143">Non</span><span class="sxs-lookup"><span data-stu-id="e9f4c-143">No</span></span> |
| <span data-ttu-id="e9f4c-144">Retour de la sonnerie des appels annulé</span><span class="sxs-lookup"><span data-stu-id="e9f4c-144">Unretrieved call ring back</span></span> | <span data-ttu-id="e9f4c-145">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-145">Yes</span></span> | <span data-ttu-id="e9f4c-146">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-146">Yes</span></span> | <span data-ttu-id="e9f4c-147">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-147">Yes</span></span> | <span data-ttu-id="e9f4c-148">Oui</span><span class="sxs-lookup"><span data-stu-id="e9f4c-148">Yes</span></span> | <span data-ttu-id="e9f4c-149">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="e9f4c-149">Coming soon</span></span>| <span data-ttu-id="e9f4c-150">Non</span><span class="sxs-lookup"><span data-stu-id="e9f4c-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="e9f4c-151">Configuration du parc et de la récupération des appels</span><span class="sxs-lookup"><span data-stu-id="e9f4c-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="e9f4c-152">Vous devez être administrateur pour configurer le parc d’appels et la récupération, et la fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="e9f4c-153">Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="e9f4c-154">Lorsque vous appliquez la même politique à un ensemble d’utilisateurs, ces derniers peuvent se parcer et récupérer les appels entre eux.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="e9f4c-155">Pour configurer le parc d’appels pour les utilisateurs et créer des groupes d’utilisateurs de parc d’appels, suivez la procédure [assigner une stratégie de parc d’appels](#assign-a-call-park-policy) ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="e9f4c-156">Pour plus d’informations sur l’utilisation de la fonctionnalité de parc et de récupération d’appel, voir [Park a Call in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="e9f4c-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="e9f4c-157">Activer une stratégie de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="e9f4c-157">Enable a call park policy</span></span>

<span data-ttu-id="e9f4c-158">Pour activer une stratégie de parc d’appels, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e9f4c-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="e9f4c-159">Accédez\*\*\*\* > \*\*\*\* au > Centre d' **administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="e9f4c-160">Sélectionnez **nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-160">Select **New policy**.</span></span>
3. <span data-ttu-id="e9f4c-161">Attribuez un nom à la stratégie, puis basculez **autoriser le parc d’appels** sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="e9f4c-162">Sélectionnez **Save (enregistrer**).</span><span class="sxs-lookup"><span data-stu-id="e9f4c-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="e9f4c-163">Assigner une stratégie de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="e9f4c-163">Assign a call park policy</span></span>

<span data-ttu-id="e9f4c-164">Pour attribuer une stratégie de parc d’appels à un ou plusieurs utilisateurs, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e9f4c-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="e9f4c-165">Accédez\*\*\*\* > \*\*\*\* au > Centre d' **administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="e9f4c-166">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e9f4c-167">Sélectionnez **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="e9f4c-168">Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e9f4c-169">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e9f4c-170">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="e9f4c-171">Configurer le parc d’appels et récupérer avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9f4c-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="e9f4c-172">Utilisez l’applet de cmdlet PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) pour créer une stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="e9f4c-173">Utilisez l’applet de passe PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) pour accorder une stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="e9f4c-174">Vous pouvez modifier le paramètre par défaut en utilisant [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) comme suit :</span><span class="sxs-lookup"><span data-stu-id="e9f4c-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="e9f4c-175">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="e9f4c-175">Troubleshooting</span></span>

<span data-ttu-id="e9f4c-176">Si les utilisateurs ne peuvent pas voir le bouton parc ou récupérer :</span><span class="sxs-lookup"><span data-stu-id="e9f4c-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="e9f4c-177">Vérifiez que la stratégie de parc d’appels est activée pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="e9f4c-178">Si un utilisateur tente de récupérer un appel et échoue, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="e9f4c-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="e9f4c-179">Vérifier que l’utilisateur utilise le client teams ou un appareil/téléphone compatible teams</span><span class="sxs-lookup"><span data-stu-id="e9f4c-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="e9f4c-180">Regroupement : il s’agit de l’utilisateur membre du groupe de parc d’appels, qui est basé sur le fait que la même stratégie de parc d’appels d’équipes est affectée.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-180">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="e9f4c-181">Mode île : le parc d’appels et la récupération ne sont pas disponibles en mode îlot d’équipe.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="e9f4c-182">L’appel a déjà été récupéré ou arrêté.</span><span class="sxs-lookup"><span data-stu-id="e9f4c-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="e9f4c-183">More information</span><span class="sxs-lookup"><span data-stu-id="e9f4c-183">More information</span></span>

<span data-ttu-id="e9f4c-184">[Parcez un appel dans teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="e9f4c-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>
