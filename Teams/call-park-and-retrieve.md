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
description: En savoir plus sur l’utilisation du parc d’appels et la récupération pour mettre un appel en attente dans Microsoft Teams.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424592"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="52efb-103">Parcage et récupération d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52efb-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="52efb-104">Le parc et la récupération des appels est une fonctionnalité qui permet à un utilisateur de mettre un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="52efb-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="52efb-105">Lorsqu’un appel est parqué, le service génère un code unique pour la récupération des appels.</span><span class="sxs-lookup"><span data-stu-id="52efb-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="52efb-106">L’utilisateur qui a parqué l’appel ou quelqu’un d’autre peut alors utiliser ce code avec une application ou un appareil pris en charge pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="52efb-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="52efb-107">(Pour plus d’informations, consultez la section voir [Park a Call in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) .)</span><span class="sxs-lookup"><span data-stu-id="52efb-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="52efb-108">Voici quelques-uns des scénarios les plus courants d’utilisation du parc d’appel :</span><span class="sxs-lookup"><span data-stu-id="52efb-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="52efb-109">Un réceptionniste est un appel pour une personne qui travaille dans une fabrique.</span><span class="sxs-lookup"><span data-stu-id="52efb-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="52efb-110">La réceptionniste annonce ensuite l’appel et le numéro de code sur le système d’adresses publiques.</span><span class="sxs-lookup"><span data-stu-id="52efb-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="52efb-111">L’utilisateur pour lequel l’appel est destiné peut alors décrocher un téléphone d’équipe sur le plancher et entrer le code permettant de récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="52efb-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="52efb-112">Un utilisateur a un appel sur un appareil mobile, car la batterie de l’appareil est épuisée.</span><span class="sxs-lookup"><span data-stu-id="52efb-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="52efb-113">L’utilisateur peut ensuite entrer le code permettant de récupérer l’appel à partir d’un téléphone de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="52efb-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="52efb-114">Un représentant du support technique Centre un appel client et envoie une annonce à un canal d’équipe pour permettre à un expert de récupérer l’appel et d’aider le client.</span><span class="sxs-lookup"><span data-stu-id="52efb-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="52efb-115">Un expert entre le code dans les clients teams pour récupérer l’appel</span><span class="sxs-lookup"><span data-stu-id="52efb-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="52efb-116">Pour le stationnement et la récupération des appels, l’utilisateur doit être un utilisateur de voix entreprise et doit être inclus dans une stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="52efb-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="52efb-117">Le parc et la récupération d’appels ne sont disponibles qu’en [mode de déploiement d’équipes](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et ne sont pas pris en charge sur les téléphones IP Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="52efb-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="52efb-118">Configurer le parc d’appels et la récupération</span><span class="sxs-lookup"><span data-stu-id="52efb-118">Configure call park and retrieve</span></span>

<span data-ttu-id="52efb-119">Vous devez être administrateur d’équipes pour configurer le parc d’appels et la récupération.</span><span class="sxs-lookup"><span data-stu-id="52efb-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="52efb-120">Elle est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="52efb-120">It is disabled by default.</span></span> <span data-ttu-id="52efb-121">Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="52efb-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="52efb-122">Lorsque vous appliquez la même politique à un ensemble d’utilisateurs, ces derniers peuvent se parcer et récupérer les appels entre eux.</span><span class="sxs-lookup"><span data-stu-id="52efb-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="52efb-123">Pour activer une stratégie de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="52efb-123">To enable a call park policy</span></span>

1. <span data-ttu-id="52efb-124">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies de parc d’appels**vocaux.</span><span class="sxs-lookup"><span data-stu-id="52efb-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="52efb-125">Sous l’onglet **gérer les stratégies** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="52efb-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="52efb-126">Attribuez un nom à la stratégie, puis basculez **autoriser le parc d’appels** sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="52efb-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Capture d’écran des paramètres de stratégie de parc d’appels](media/call-park-add-policy.png)

4. <span data-ttu-id="52efb-128">Sélectionnez **Save (enregistrer**).</span><span class="sxs-lookup"><span data-stu-id="52efb-128">Select **Save**.</span></span>

<span data-ttu-id="52efb-129">Vous pouvez modifier la stratégie en la sélectionnant dans la liste, puis en cliquant sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="52efb-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="52efb-130">Pour que la stratégie puisse fonctionner, elle doit être attribuée à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="52efb-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="52efb-131">Vous pouvez [affecter la stratégie aux utilisateurs individuellement](assign-policies.md) ou les affecter à un groupe.</span><span class="sxs-lookup"><span data-stu-id="52efb-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="52efb-132">Pour attribuer une stratégie de composant d’appel à un groupe</span><span class="sxs-lookup"><span data-stu-id="52efb-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="52efb-133">Dans la page **stratégies de parc d’appels** , sous l’onglet affectation de stratégie de **Groupe** , cliquez sur Ajouter un **groupe**.</span><span class="sxs-lookup"><span data-stu-id="52efb-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="52efb-134">Recherchez le groupe que vous voulez utiliser, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="52efb-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="52efb-135">Choisissez un classement par rapport aux autres affectations de groupe.</span><span class="sxs-lookup"><span data-stu-id="52efb-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="52efb-136">Sous **Sélectionner une stratégie**, sélectionnez la stratégie que vous souhaitez attribuer à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="52efb-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="52efb-137">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="52efb-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="52efb-138">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="52efb-138">Related topics</span></span>

[<span data-ttu-id="52efb-139">Park a Call en teams</span><span class="sxs-lookup"><span data-stu-id="52efb-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="52efb-140">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="52efb-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="52efb-141">Nouveau-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="52efb-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="52efb-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="52efb-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="52efb-143">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="52efb-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)