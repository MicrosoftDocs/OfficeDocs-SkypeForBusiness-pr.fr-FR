---
title: Parcage et récupération d’appel dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Découvrez comment utiliser le parc d’appels et récupérer pour mettre un appel en attente dans Microsoft Teams.
ms.openlocfilehash: fb60e09148f2b96ce9b4d059d7d112c817239822
ms.sourcegitcommit: 355c7858b98518f6a922110390c51eb7e2cd6690
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53147182"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="9a91b-103">Parcage et récupération d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a91b-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="9a91b-104">La fonctionnalité Parcer et récupérer des appels permet à un utilisateur de mettre un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="9a91b-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="9a91b-105">Lorsqu’un appel est paré, le service génère un code unique pour l’extraction des appels.</span><span class="sxs-lookup"><span data-stu-id="9a91b-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="9a91b-106">L’utilisateur qui a parké l’appel ou quelqu’un d’autre peut ensuite utiliser ce code avec une application ou un appareil pris en charge pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="9a91b-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="9a91b-107">(Pour plus [d’informations, voir Park a call in Teams.)](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)</span><span class="sxs-lookup"><span data-stu-id="9a91b-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="9a91b-108">Voici quelques-uns des scénarios courants d’utilisation du parc d’appels :</span><span class="sxs-lookup"><span data-stu-id="9a91b-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="9a91b-109">Un appelant appelle une personne travaillant dans une usine.</span><span class="sxs-lookup"><span data-stu-id="9a91b-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="9a91b-110">Le réceptioniste annonce ensuite l’appel et le numéro de code sur le système d’adresses public.</span><span class="sxs-lookup"><span data-stu-id="9a91b-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="9a91b-111">L’utilisateur pour qui l’appel est en cours peut alors prendre un téléphone Teams aux ateliers et entrer le code pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="9a91b-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="9a91b-112">Un utilisateur relaient un appel sur un appareil mobile parce que la batterie de l’appareil est à court de courant.</span><span class="sxs-lookup"><span data-stu-id="9a91b-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="9a91b-113">L’utilisateur peut ensuite entrer le code pour récupérer l’appel à partir Teams téléphone de bureau.</span><span class="sxs-lookup"><span data-stu-id="9a91b-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="9a91b-114">Un représentant du support technique appelle un client et envoie une annonce sur un canal Teams un expert pour récupérer l’appel et aider le client.</span><span class="sxs-lookup"><span data-stu-id="9a91b-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="9a91b-115">Un expert entre le code dans Teams clients pour récupérer l’appel</span><span class="sxs-lookup"><span data-stu-id="9a91b-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="9a91b-116">Pour parer et récupérer des appels, un utilisateur doit être un Voix Entreprise et doit être inclus dans une stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="9a91b-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="9a91b-117">Le parcage et la récupération d’appels sont disponibles uniquement [dans Teams mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) déploiement uniquement et ne sont pas pris en charge Skype Entreprise téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="9a91b-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="9a91b-118">Configurer le parc d’appel et la récupération</span><span class="sxs-lookup"><span data-stu-id="9a91b-118">Configure call park and retrieve</span></span>

<span data-ttu-id="9a91b-119">Vous devez être un administrateur Teams configuration du parc d’appels et de la récupération.</span><span class="sxs-lookup"><span data-stu-id="9a91b-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="9a91b-120">Il est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="9a91b-120">It is disabled by default.</span></span> <span data-ttu-id="9a91b-121">Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="9a91b-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="9a91b-122">Lorsque vous appliquez la même stratégie à un groupe d’utilisateurs, ceux-là peuvent se parer et récupérer des appels entre eux.</span><span class="sxs-lookup"><span data-stu-id="9a91b-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="9a91b-123">La plage de numéros d’appel est prédéfinée de 10 à 99 et ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="9a91b-123">The range of call pickup numbers is predefined to be from 10-99 and cannot be modified.</span></span> <span data-ttu-id="9a91b-124">Le premier appel paré s’intituera sur un code de pick-up du 10, le code d’appel 11, etc. sera restituer l’appel en place.</span><span class="sxs-lookup"><span data-stu-id="9a91b-124">The first parked call will be rendered a pickup code of 10, the next parked call will be rendered a pickup code of 11, etc.</span></span> <span data-ttu-id="9a91b-125">jusqu’à ce que 99 soit rendu en tant que code de pick-up.</span><span class="sxs-lookup"><span data-stu-id="9a91b-125">until 99 is rendered as a pickup code.</span></span> <span data-ttu-id="9a91b-126">Par la suite, les codes d’pick-up restituer à partir de 10 recommencent.</span><span class="sxs-lookup"><span data-stu-id="9a91b-126">After which, the rendered pickup codes start over from 10 once again.</span></span>  <span data-ttu-id="9a91b-127">S’il y a plus de 89 appels en cours parés, les codes d’pick-up restituer continueront d’être incrémentés au-delà de 99, de telle telle que le 90e appel par parcé sera rendu 100 pour un code de pick-up, le 91e appel en cours sera rendu avec le code de collecte 101.</span><span class="sxs-lookup"><span data-stu-id="9a91b-127">If there are more than 89 active parked calls, the rendered pickup codes will keep incrementing beyond 99 such that the 90th active parked call would be rendered 100 for a pickup code, the 91st active parked call would be rendered a pickup code of 101.</span></span>

<span data-ttu-id="9a91b-128">Pour activer une stratégie de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="9a91b-128">To enable a call park policy</span></span>

1. <span data-ttu-id="9a91b-129">Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez à **Stratégies**  >  **de parc d’appel vocal.**</span><span class="sxs-lookup"><span data-stu-id="9a91b-129">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="9a91b-130">Sous **l’onglet Gérer les stratégies,** cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="9a91b-130">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="9a91b-131">Donnez un nom à la stratégie, puis basculez **l’accès au parc d’appels** **sur On.**</span><span class="sxs-lookup"><span data-stu-id="9a91b-131">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Capture d’écran des paramètres de stratégie de parc d’appel](media/call-park-add-policy.png)

4. <span data-ttu-id="9a91b-133">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9a91b-133">Select **Save**.</span></span>

<span data-ttu-id="9a91b-134">Vous pouvez modifier la stratégie en la sélectionnant dans la liste et en cliquant sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="9a91b-134">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="9a91b-135">Pour que la stratégie fonctionne, elle doit être attribuée aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9a91b-135">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="9a91b-136">Vous pouvez [affecter la stratégie à des utilisateurs individuellement](assign-policies.md) ou à un groupe.</span><span class="sxs-lookup"><span data-stu-id="9a91b-136">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="9a91b-137">Pour affecter une stratégie de parc d’appels à un groupe</span><span class="sxs-lookup"><span data-stu-id="9a91b-137">To assign a call park policy to a group</span></span>

1. <span data-ttu-id="9a91b-138">Dans la page **Stratégies de parc** d’appel, sous l’onglet **Affectation** de stratégie de groupe, cliquez sur Ajouter **un groupe.**</span><span class="sxs-lookup"><span data-stu-id="9a91b-138">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="9a91b-139">Recherchez le groupe que vous voulez utiliser, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="9a91b-139">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="9a91b-140">Choisissez un rang comparé aux autres affectations de groupe.</span><span class="sxs-lookup"><span data-stu-id="9a91b-140">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="9a91b-141">Sous **Sélectionner une stratégie,** choisissez la stratégie à qui vous voulez affecter ce groupe.</span><span class="sxs-lookup"><span data-stu-id="9a91b-141">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![Image stratégies de parc](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="9a91b-143">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="9a91b-143">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a91b-144">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="9a91b-144">Related topics</span></span>

[<span data-ttu-id="9a91b-145">Par parcer un appel dans Teams</span><span class="sxs-lookup"><span data-stu-id="9a91b-145">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="9a91b-146">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9a91b-146">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="9a91b-147">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="9a91b-147">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="9a91b-148">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="9a91b-148">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="9a91b-149">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="9a91b-149">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
