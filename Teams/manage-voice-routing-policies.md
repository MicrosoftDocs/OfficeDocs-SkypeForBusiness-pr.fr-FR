---
title: Gérer les stratégies de routage de messagerie vocale dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment créer et gérer des stratégies de routage de messagerie vocale dans Microsoft Teams.
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350188"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="82f1b-103">Gérer les stratégies de routage de messagerie vocale dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="82f1b-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="82f1b-104">Si vous avez déployé le [routage direct du système téléphonique](direct-routing-landing-page.md) au sein de votre organisation, vous utilisez les stratégies de routage vocal pour permettre aux équipes et aux utilisateurs de Skype entreprise Online de recevoir et de passer des appels téléphoniques à l’aide du réseau téléphonique public commuté (RTC) à l’aide de votre infrastructure de téléphonie locale.</span><span class="sxs-lookup"><span data-stu-id="82f1b-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="82f1b-105">Une stratégie de routage vocale est un conteneur d’enregistrements d’utilisation RTC.</span><span class="sxs-lookup"><span data-stu-id="82f1b-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="82f1b-106">Pour créer et gérer des stratégies de routage de messagerie vocale, vous pouvez **accéder à**  >  **stratégies de routage vocal** dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82f1b-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="82f1b-107">Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="82f1b-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="82f1b-108">Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="82f1b-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="82f1b-109">Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer.</span><span class="sxs-lookup"><span data-stu-id="82f1b-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="82f1b-110">Il est important de savoir que l’affectation d’une stratégie de routage vocale à un utilisateur ne permet pas à un utilisateur de passer des appels RTC dans Teams.</span><span class="sxs-lookup"><span data-stu-id="82f1b-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="82f1b-111">Vous devez également activer l’utilisateur pour le routage direct du système téléphonique et effectuer d’autres étapes de configuration.</span><span class="sxs-lookup"><span data-stu-id="82f1b-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="82f1b-112">Pour en savoir plus, voir [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="82f1b-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="82f1b-113">Créer une stratégie de routage vocale personnalisée</span><span class="sxs-lookup"><span data-stu-id="82f1b-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="82f1b-114">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82f1b-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="82f1b-115">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**stratégies de routage de voix vocales, puis  >  **Voice routing policies**cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="82f1b-116">![Capture d’écran de la page Ajouter une stratégie de routage vocale dans le centre d’administration Microsoft teams](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="82f1b-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="82f1b-117">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="82f1b-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="82f1b-118">Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, puis sélectionnez les enregistrements que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="82f1b-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="82f1b-119">Si vous avez besoin de créer un nouvel enregistrement d’utilisation RTC, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="82f1b-120">Si vous avez ajouté plusieurs enregistrements d’utilisation RTC, réorganisez-les dans l’ordre de votre choix.</span><span class="sxs-lookup"><span data-stu-id="82f1b-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="82f1b-121">Lorsque vous avez terminé, cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="82f1b-122">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="82f1b-123">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="82f1b-123">Using PowerShell</span></span>

<span data-ttu-id="82f1b-124">Voir [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="82f1b-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="82f1b-125">Modification d’une stratégie de routage téléphonique</span><span class="sxs-lookup"><span data-stu-id="82f1b-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="82f1b-126">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82f1b-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="82f1b-127">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="82f1b-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="82f1b-128">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de routage vocal**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="82f1b-129">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="82f1b-130">Cliquez sur **Ajouter/supprimer des enregistrements d’utilisation RTC**, apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="82f1b-131">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="82f1b-131">Using PowerShell</span></span>

<span data-ttu-id="82f1b-132">Voir [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="82f1b-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="82f1b-133">Assigner une stratégie de routage vocale personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="82f1b-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="82f1b-134">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82f1b-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="82f1b-135">Pour attribuer une stratégie à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="82f1b-135">To assign a policy to one user:</span></span>

1. <span data-ttu-id="82f1b-136">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82f1b-136">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="82f1b-137">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-137">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="82f1b-138">Sous **stratégie de routage**de la voix, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-138">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="82f1b-139">Pour attribuer une stratégie à plusieurs utilisateurs à la fois :</span><span class="sxs-lookup"><span data-stu-id="82f1b-139">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="82f1b-140">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.</span><span class="sxs-lookup"><span data-stu-id="82f1b-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="82f1b-141">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="82f1b-141">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="82f1b-142">Pour sélectionner tous les utilisateurs, cliquez sur l' &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="82f1b-142">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="82f1b-143">Cliquez sur **modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-143">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="82f1b-144">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="82f1b-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="82f1b-145">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de routage vocal**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="82f1b-146">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="82f1b-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="82f1b-147">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="82f1b-148">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="82f1b-149">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="82f1b-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="82f1b-150">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="82f1b-150">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="82f1b-151">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="82f1b-151">Using PowerShell</span></span>

<span data-ttu-id="82f1b-152">Voir [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="82f1b-152">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="82f1b-153">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="82f1b-153">Related topics</span></span>

- [<span data-ttu-id="82f1b-154">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="82f1b-154">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="82f1b-155">Configurer le routage de la voix pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="82f1b-155">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="82f1b-156">Activer le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="82f1b-156">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="82f1b-157">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="82f1b-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
