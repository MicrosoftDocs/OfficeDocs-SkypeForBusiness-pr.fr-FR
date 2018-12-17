---
title: Le parcage d’appel et de récupérer dans Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/17/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Utilisez parcage d’appel et de récupération pour passer un appel en attente dans le service d’équipes dans le nuage.
ms.openlocfilehash: 004a5b12e178a6460ef05f7c6f5c5738c8ced042
ms.sourcegitcommit: 0e671e6e6fdd25227068c7e3a3a5509b6536d2b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2018
ms.locfileid: "27294187"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="c4ff6-103">Le parcage d’appel et de récupérer dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4ff6-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="c4ff6-104">Mise en garde d’appels et de récupération est une fonctionnalité qui permet à un utilisateur de passer un appel en attente dans le service d’équipes dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="c4ff6-105">Lors de la mise en garde un appel, le service génère un code unique pour la récupération de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="c4ff6-106">L’utilisateur qui a été mis en garde l’appel ou une autre personne peut ensuite utiliser ce code et une applications pris en charge ou périphérique pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="c4ff6-107">Les scénarios courants d’utilisation de parcage d’appel sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c4ff6-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="c4ff6-108">Un réceptionniste parcs élevage un appel d’une personne travaillant dans une fabrique.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="c4ff6-109">Le réceptionniste annonce puis l’appel et le numéro de code dans le système.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="c4ff6-110">L’utilisateur pour l’appel peut sélectionner un téléphone équipes en usine, puis entrez le code pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="c4ff6-111">Un utilisateur parcs élevage un appel sur un appareil mobile, car la batterie de l’appareil manque d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="c4ff6-112">L’utilisateur peut entrer puis de code pour récupérer l’appel à partir d’un téléphone de bureau équipes.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="c4ff6-113">Un parcs représentant prise en charge un client d’appel et envoie une annonce sur un canal d’équipes pour récupérer l’appel et aider le client à un expert.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="c4ff6-114">Un expert entre le code dans les clients des équipes pour récupérer l’appel</span><span class="sxs-lookup"><span data-stu-id="c4ff6-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4ff6-115">Cette fonctionnalité est uniquement disponible en mode de déploiement équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="c4ff6-116">Pour plus d’informations sur les modes de déploiement d’équipes, voir [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="c4ff6-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="c4ff6-117">Licence requise</span><span class="sxs-lookup"><span data-stu-id="c4ff6-117">License required</span></span>

<span data-ttu-id="c4ff6-118">Pour mettre en garde et récupérer des appels, l’utilisateur doit être un utilisateur Enterprise Voice et un administrateur doit accorder à l’utilisateur une stratégie de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="c4ff6-119">Pour plus d’informations sur le modèle de licence, voir [Gestion des licences Office 365 pour les équipes Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c4ff6-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="c4ff6-120">Le parcage d’appel et de récupérer la disponibilité des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="c4ff6-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="c4ff6-121">Parcage d’appel et de récupérer est actuellement pris en charge par les périphériques clients suivants.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="c4ff6-122">(Pris en charge en mode équipes uniquement, avec ou sans connectivité PSTN).</span><span class="sxs-lookup"><span data-stu-id="c4ff6-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="c4ff6-123">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="c4ff6-123">Capability</span></span> | <span data-ttu-id="c4ff6-124">Bureau des équipes</span><span class="sxs-lookup"><span data-stu-id="c4ff6-124">Teams Desktop</span></span> | <span data-ttu-id="c4ff6-125">Les équipes Mac application</span><span class="sxs-lookup"><span data-stu-id="c4ff6-125">Teams Mac App</span></span> | <span data-ttu-id="c4ff6-126">Les équipes Web App (périmètre)</span><span class="sxs-lookup"><span data-stu-id="c4ff6-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="c4ff6-127">Les équipes mobile iOS/Android application</span><span class="sxs-lookup"><span data-stu-id="c4ff6-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="c4ff6-128">Téléphone IP d’équipes</span><span class="sxs-lookup"><span data-stu-id="c4ff6-128">Teams IP phone</span></span> | <span data-ttu-id="c4ff6-129">Skype pour téléphone IP d’entreprise</span><span class="sxs-lookup"><span data-stu-id="c4ff6-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="c4ff6-130">Mise en garde d’un appel</span><span class="sxs-lookup"><span data-stu-id="c4ff6-130">Park a call</span></span> | <span data-ttu-id="c4ff6-131">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-131">Yes</span></span> | <span data-ttu-id="c4ff6-132">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-132">Yes</span></span> | <span data-ttu-id="c4ff6-133">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-133">Yes</span></span> | <span data-ttu-id="c4ff6-134">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="c4ff6-134">Coming soon</span></span> | <span data-ttu-id="c4ff6-135">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="c4ff6-135">Coming soon</span></span>| <span data-ttu-id="c4ff6-136">Non</span><span class="sxs-lookup"><span data-stu-id="c4ff6-136">No</span></span> |
| <span data-ttu-id="c4ff6-137">Récupérer un appel mis en garde</span><span class="sxs-lookup"><span data-stu-id="c4ff6-137">Retrieve a parked call</span></span> | <span data-ttu-id="c4ff6-138">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-138">Yes</span></span> | <span data-ttu-id="c4ff6-139">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-139">Yes</span></span> | <span data-ttu-id="c4ff6-140">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-140">Yes</span></span> | <span data-ttu-id="c4ff6-141">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="c4ff6-141">Coming soon</span></span> | <span data-ttu-id="c4ff6-142">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="c4ff6-142">Coming soon</span></span>| <span data-ttu-id="c4ff6-143">Non</span><span class="sxs-lookup"><span data-stu-id="c4ff6-143">No</span></span> |
| <span data-ttu-id="c4ff6-144">Sonnerie d’appel non récupérées précédent</span><span class="sxs-lookup"><span data-stu-id="c4ff6-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="c4ff6-145">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-145">Yes</span></span> | <span data-ttu-id="c4ff6-146">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-146">Yes</span></span> | <span data-ttu-id="c4ff6-147">Oui</span><span class="sxs-lookup"><span data-stu-id="c4ff6-147">Yes</span></span> | <span data-ttu-id="c4ff6-148">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="c4ff6-148">Coming soon</span></span> | <span data-ttu-id="c4ff6-149">Bientôt disponible</span><span class="sxs-lookup"><span data-stu-id="c4ff6-149">Coming soon</span></span>| <span data-ttu-id="c4ff6-150">Non</span><span class="sxs-lookup"><span data-stu-id="c4ff6-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="c4ff6-151">Configuration de mise en garde d’appels et de récupération</span><span class="sxs-lookup"><span data-stu-id="c4ff6-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="c4ff6-152">Vous devez être un administrateur de configurer la mise en garde d’appels et de récupération, et la fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="c4ff6-153">Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="c4ff6-154">Lorsque vous appliquez la même stratégie à un ensemble d’utilisateurs, ils seront en mesure de mettre en garde et récupérer des appels entre eux.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="c4ff6-155">Pour configurer la mise en garde d’appels pour les utilisateurs et créer des groupes d’utilisateurs appel park, suivez la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="c4ff6-156">Pour plus d’informations sur la façon d’utiliser la mise en garde d’appels et de récupérer la fonctionnalité, voir [mise en garde d’un appel en équipe](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="c4ff6-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="c4ff6-157">Configurer la mise en garde d’appels et récupérer l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ff6-157">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="c4ff6-158">Utilisez l’applet de commande PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) pour créer une stratégie de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-158">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="c4ff6-159">Utilisez l’applet de commande PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) pour accorder une stratégie de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-159">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="c4ff6-160">Vous pouvez modifier le paramètre par défaut à l’aide de [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) comme suit :</span><span class="sxs-lookup"><span data-stu-id="c4ff6-160">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="c4ff6-161">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="c4ff6-161">Troubleshooting</span></span>

<span data-ttu-id="c4ff6-162">Si les utilisateurs ne peuvent pas voir le parc ou récupérer le bouton :</span><span class="sxs-lookup"><span data-stu-id="c4ff6-162">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="c4ff6-163">Vérifiez que l’utilisateur dispose de la stratégie de parcage d’appel activée.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-163">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="c4ff6-164">Si un utilisateur tente de récupérer un appel échoue, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="c4ff6-164">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="c4ff6-165">Vérifiez que l’utilisateur utilise le client équipes ou un téléphone/appareil prenant en charge les équipes</span><span class="sxs-lookup"><span data-stu-id="c4ff6-165">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="c4ff6-166">Regroupement – est l’utilisateur membre du groupe de parcage d’appel ?</span><span class="sxs-lookup"><span data-stu-id="c4ff6-166">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="c4ff6-167">Mode (îles) – mise en garde d’appels et de récupération n’est pas disponible en mode îlot d’équipes.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-167">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="c4ff6-168">L’appel a déjà été récupéré ou interrompue.</span><span class="sxs-lookup"><span data-stu-id="c4ff6-168">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="c4ff6-169">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="c4ff6-169">More information</span></span>

<span data-ttu-id="c4ff6-170">[Mise en garde d’un appel en équipe](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="c4ff6-170">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>