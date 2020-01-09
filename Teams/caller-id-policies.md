---
title: Gérer les stratégies d’identification d’appelant dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft teams pour modifier ou bloquer l’ID d’appelant des utilisateurs de teams au sein de votre organisation.
ms.openlocfilehash: aed6e3cbe2053ddc16b049608247f56705626249
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992884"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="0f57c-103">Gérer les stratégies d’identification d’appelant dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="0f57c-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="0f57c-104">En tant qu’administrateur, vous pouvez utiliser les stratégies d’identification d’appelant dans Microsoft teams pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel).</span><span class="sxs-lookup"><span data-stu-id="0f57c-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="0f57c-105">Par défaut, le nombre de numéros de téléphone des utilisateurs de teams est visible lors d’un appel vers un téléphone RTC et le numéro de téléphone des appelants PSTN peut être affiché lorsqu’ils appellent un utilisateur de teams.</span><span class="sxs-lookup"><span data-stu-id="0f57c-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="0f57c-106">Vous pouvez utiliser les stratégies d’identification de l’appelant pour afficher un autre numéro de téléphone pour les utilisateurs teams de votre organisation ou bloquer l’affichage d’un numéro entrant.</span><span class="sxs-lookup"><span data-stu-id="0f57c-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="0f57c-107">Par exemple, lorsque les utilisateurs effectuent un appel, vous pouvez modifier l’identification de l’appelant pour afficher le numéro de téléphone principal de votre organisation à la place des numéros de téléphone des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0f57c-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="0f57c-108">Vous gérez les stratégies d’identification de l’appelant en accédant à**stratégies d’identification** de l’appelant **vocal** > dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0f57c-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0f57c-109">Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer des stratégies personnalisées et les affecter à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0f57c-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="0f57c-110">Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0f57c-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="0f57c-111">Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0f57c-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="0f57c-112">Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f57c-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="0f57c-113">Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f57c-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="0f57c-114">Créer une stratégie d’ID d’appelant personnalisée</span><span class="sxs-lookup"><span data-stu-id="0f57c-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="0f57c-115">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’identification**de l’appelant **vocal** > .</span><span class="sxs-lookup"><span data-stu-id="0f57c-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="0f57c-116">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-116">Click **Add**.</span></span>
<span data-ttu-id="0f57c-117">![Capture d’écran de la nouvelle page de stratégie d’ID d’appelant dans le centre d’administration](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="0f57c-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="0f57c-118">Entrez le nom et la description de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="0f57c-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="0f57c-119">À partir de cet emplacement, sélectionnez les paramètres de votre choix :</span><span class="sxs-lookup"><span data-stu-id="0f57c-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="0f57c-120">**Bloquer l’ID d’appelant entrant**: activez ce paramètre pour bloquer l’identification de l’appelant lors de l’affichage d’appels entrants.</span><span class="sxs-lookup"><span data-stu-id="0f57c-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="0f57c-121">**Les utilisateurs peuvent ignorer la stratégie d’ID d’appelant**: activez ce paramètre pour permettre aux utilisateurs de remplacer les paramètres de la stratégie concernant l’affichage de leur numéro pour les appelants.</span><span class="sxs-lookup"><span data-stu-id="0f57c-121">**Users can override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="0f57c-122">Cela signifie que les utilisateurs peuvent décider d’afficher leur ID d’appelant.</span><span class="sxs-lookup"><span data-stu-id="0f57c-122">This means that users can choose whether to display their caller ID.</span></span>
    - <span data-ttu-id="0f57c-123">**Remplacer l’identification**de l’appelant : définissez l’ID de l’appelant à afficher pour les utilisateurs en sélectionnant l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0f57c-123">**Replace caller ID**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="0f57c-124">**Numéro de**l’utilisateur : affiche le numéro de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f57c-124">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="0f57c-125">**Numéro de service**: vous permet de définir un numéro de téléphone de service à afficher en tant qu’identifiant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0f57c-125">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="0f57c-126">**Anonyme**: affiche l’ID de l’appelant comme anonyme.</span><span class="sxs-lookup"><span data-stu-id="0f57c-126">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="0f57c-127">**Numéro de service à utiliser pour remplacer l’identifiant de l’appelant**: sélectionnez un numéro de service pour remplacer l’identifiant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0f57c-127">**Service number to use to replace the caller ID**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="0f57c-128">Cette option n’est disponible que si vous avez sélectionné **numéro de service** dans **remplacer l’identifiant**de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0f57c-128">This option is available if you selected **Service number** in **Replace caller ID**.</span></span>

5. <span data-ttu-id="0f57c-129">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-129">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="0f57c-130">Modifier une stratégie d’ID d’appelant</span><span class="sxs-lookup"><span data-stu-id="0f57c-130">Edit a caller ID policy</span></span>

<span data-ttu-id="0f57c-131">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="0f57c-131">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="0f57c-132">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’identification**de l’appelant **vocal** > .</span><span class="sxs-lookup"><span data-stu-id="0f57c-132">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="0f57c-133">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-133">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0f57c-134">Modifiez les paramètres souhaités, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-134">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="0f57c-135">Attribuer une stratégie d’ID d’appelant personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0f57c-135">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="0f57c-136">Vous pouvez utiliser le centre d’administration de Microsoft teams pour attribuer une stratégie personnalisée à un ou plusieurs utilisateurs ou au module PowerShell Skype entreprise pour attribuer une stratégie personnalisée à des groupes d’utilisateurs, tels qu’un groupe de sécurité ou un groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="0f57c-136">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="0f57c-137">Assigner une stratégie d’ID de ligne d’appelant personnalisée à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="0f57c-137">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="0f57c-138">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f57c-138">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="0f57c-139">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-139">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="0f57c-140">Sous **stratégie d’identification**de l’appelant, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-140">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="0f57c-141">Assigner une stratégie d’ID de ligne d’appel personnalisée à plusieurs utilisateurs à la fois</span><span class="sxs-lookup"><span data-stu-id="0f57c-141">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="0f57c-142">Pour assigner une stratégie d’ID de ligne d’appel personnalisée à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="0f57c-142">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="0f57c-143">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0f57c-143">Or, you can also do the following:</span></span>

1. <span data-ttu-id="0f57c-144">Accédez\*\*\*\* > \*\*\*\* au > Centre d' **administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-144">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="0f57c-145">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="0f57c-145">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="0f57c-146">Sélectionnez **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-146">Select **Manage users**.</span></span>
4. <span data-ttu-id="0f57c-147">Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-147">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="0f57c-148">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="0f57c-148">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="0f57c-149">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0f57c-149">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="0f57c-150">Assigner une stratégie d’ID d’appelant personnalisée aux utilisateurs d’un groupe</span><span class="sxs-lookup"><span data-stu-id="0f57c-150">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="0f57c-151">Vous pouvez assigner une stratégie personnalisée à plusieurs utilisateurs que vous avez déjà identifiés.</span><span class="sxs-lookup"><span data-stu-id="0f57c-151">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="0f57c-152">Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0f57c-152">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="0f57c-153">Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="0f57c-153">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="0f57c-154">Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f57c-154">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="0f57c-155">Dans cet exemple, nous affectons une stratégie de capot d’appelant personnalisé appelée stratégie d’ID d’appelant à tous les utilisateurs du groupe de support technique contoso.</span><span class="sxs-lookup"><span data-stu-id="0f57c-155">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="0f57c-156">Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="0f57c-156">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="0f57c-157">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="0f57c-157">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="0f57c-158">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="0f57c-158">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="0f57c-159">Attribuez à tous les utilisateurs du groupe une stratégie d’ID d’appelant particulière.</span><span class="sxs-lookup"><span data-stu-id="0f57c-159">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="0f57c-160">Dans cet exemple, la stratégie d’ID d’appelant est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0f57c-160">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="0f57c-161">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="0f57c-161">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="0f57c-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f57c-162">Related topics</span></span>

- [<span data-ttu-id="0f57c-163">Nouveau-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="0f57c-163">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

