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
ms.openlocfilehash: d49e6a5a9bc25a0c7a3e25d548e2743b7f4584fb
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278714"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="6e93a-103">Parcage et récupération d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e93a-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="6e93a-104">La fonctionnalité Parcer et récupérer des appels permet à un utilisateur de mettre un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="6e93a-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="6e93a-105">Lorsqu’un appel est paré, le service génère un code unique pour l’extraction des appels.</span><span class="sxs-lookup"><span data-stu-id="6e93a-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="6e93a-106">L’utilisateur qui a parké l’appel ou quelqu’un d’autre peut ensuite utiliser ce code avec une application ou un appareil pris en charge pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="6e93a-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="6e93a-107">(Pour plus [d’informations, voir Parcer](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) un appel dans Teams.)</span><span class="sxs-lookup"><span data-stu-id="6e93a-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="6e93a-108">Voici quelques-uns des scénarios courants d’utilisation du parc d’appels :</span><span class="sxs-lookup"><span data-stu-id="6e93a-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="6e93a-109">Un réceptioniste appelle une personne travaillant dans une usine.</span><span class="sxs-lookup"><span data-stu-id="6e93a-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="6e93a-110">Le réceptioniste annonce ensuite l’appel et le numéro de code sur le système d’adresses public.</span><span class="sxs-lookup"><span data-stu-id="6e93a-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="6e93a-111">L’utilisateur pour qui l’appel est en cours peut alors prendre un téléphone Teams en usine et entrer le code pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="6e93a-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="6e93a-112">Un utilisateur relaient un appel sur un appareil mobile parce que la batterie de l’appareil est à court de courant.</span><span class="sxs-lookup"><span data-stu-id="6e93a-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="6e93a-113">L’utilisateur peut ensuite entrer le code pour récupérer l’appel à partir d’un téléphone de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="6e93a-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="6e93a-114">Un représentant du support technique appelle un client et envoie une annonce sur un canal Teams pour qu’un expert récupère l’appel et aide le client.</span><span class="sxs-lookup"><span data-stu-id="6e93a-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="6e93a-115">Un expert entre le code dans les clients Teams pour récupérer l’appel</span><span class="sxs-lookup"><span data-stu-id="6e93a-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="6e93a-116">Pour parer et récupérer des appels, un utilisateur doit être un Voix Entreprise et être inclus dans une stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="6e93a-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="6e93a-117">Le parcage et la récupération d’appels sont uniquement disponibles en mode déploiement [de Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) uniquement et ne sont pas pris en charge sur les téléphones IP Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="6e93a-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="6e93a-118">Configurer le parc d’appel et la récupération</span><span class="sxs-lookup"><span data-stu-id="6e93a-118">Configure call park and retrieve</span></span>

<span data-ttu-id="6e93a-119">Vous devez être un administrateur Teams pour configurer le parc d’appels et la récupération.</span><span class="sxs-lookup"><span data-stu-id="6e93a-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="6e93a-120">Il est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="6e93a-120">It is disabled by default.</span></span> <span data-ttu-id="6e93a-121">Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="6e93a-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="6e93a-122">Lorsque vous appliquez la même stratégie à un groupe d’utilisateurs, ceux-là peuvent se parer et récupérer les appels entre eux.</span><span class="sxs-lookup"><span data-stu-id="6e93a-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="6e93a-123">Pour activer une stratégie de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="6e93a-123">To enable a call park policy</span></span>

1. <span data-ttu-id="6e93a-124">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez **à** La stratégie du  >  **parc des appels vocux.**</span><span class="sxs-lookup"><span data-stu-id="6e93a-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="6e93a-125">Sous **l’onglet Gérer les stratégies,** cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="6e93a-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="6e93a-126">Donnez un nom à la stratégie, puis basculez **l’accès au parc d’appels** **sur On.**</span><span class="sxs-lookup"><span data-stu-id="6e93a-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Capture d’écran des paramètres de stratégie de parc d’appel](media/call-park-add-policy.png)

4. <span data-ttu-id="6e93a-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6e93a-128">Select **Save**.</span></span>

<span data-ttu-id="6e93a-129">Vous pouvez modifier la stratégie en la sélectionnant dans la liste, puis en cliquant sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="6e93a-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="6e93a-130">Pour que la stratégie fonctionne, elle doit être attribuée aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6e93a-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="6e93a-131">Vous pouvez [affecter la stratégie à des utilisateurs individuellement](assign-policies.md) ou à un groupe.</span><span class="sxs-lookup"><span data-stu-id="6e93a-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="6e93a-132">Pour affecter une stratégie de pièce d’appel à un groupe</span><span class="sxs-lookup"><span data-stu-id="6e93a-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="6e93a-133">Dans la page **Stratégies de parc** d’appel, sous l’onglet **Affectation** de stratégie de groupe, cliquez sur Ajouter **un groupe.**</span><span class="sxs-lookup"><span data-stu-id="6e93a-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="6e93a-134">Recherchez le groupe que vous voulez utiliser, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="6e93a-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="6e93a-135">Choisissez un rang comparé aux autres affectations de groupe.</span><span class="sxs-lookup"><span data-stu-id="6e93a-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="6e93a-136">Sous **Sélectionner une stratégie,** choisissez la stratégie à qui vous voulez affecter ce groupe.</span><span class="sxs-lookup"><span data-stu-id="6e93a-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![Image stratégies de parc](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="6e93a-138">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="6e93a-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6e93a-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e93a-139">Related topics</span></span>

[<span data-ttu-id="6e93a-140">Pare-tête dans Teams</span><span class="sxs-lookup"><span data-stu-id="6e93a-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="6e93a-141">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6e93a-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="6e93a-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="6e93a-142">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="6e93a-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="6e93a-143">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="6e93a-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="6e93a-144">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
