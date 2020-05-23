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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft teams pour modifier ou bloquer l’ID d’appelant des utilisateurs de teams au sein de votre organisation.
ms.openlocfilehash: dde534d0c74b11b3c3131a7d5c9eb8611135f70f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349778"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="c7ffc-103">Gérer les stratégies d’identification d’appelant dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="c7ffc-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="c7ffc-104">En tant qu’administrateur, vous pouvez utiliser les stratégies d’identification d’appelant dans Microsoft teams pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel).</span><span class="sxs-lookup"><span data-stu-id="c7ffc-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="c7ffc-105">Par défaut, le nombre de numéros de téléphone des utilisateurs de teams est visible lors d’un appel vers un téléphone RTC et le numéro de téléphone des appelants PSTN peut être affiché lorsqu’ils appellent un utilisateur de teams.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="c7ffc-106">Vous pouvez utiliser les stratégies d’identification de l’appelant pour afficher un autre numéro de téléphone pour les utilisateurs teams de votre organisation ou bloquer l’affichage d’un numéro entrant.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="c7ffc-107">Par exemple, lorsque les utilisateurs effectuent un appel, vous pouvez modifier l’identification de l’appelant pour afficher le numéro de téléphone principal de votre organisation à la place des numéros de téléphone des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="c7ffc-108">Vous gérez les stratégies d’identification de l' **Voice**appelant en accédant à  >  **stratégies d’identification** de l’appelant vocal dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c7ffc-109">Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer des stratégies personnalisées et les attribuer à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="c7ffc-110">Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="c7ffc-111">Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="c7ffc-112">Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="c7ffc-113">Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="c7ffc-114">Créer une stratégie d’ID d’appelant personnalisée</span><span class="sxs-lookup"><span data-stu-id="c7ffc-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="c7ffc-115">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à stratégies d’identification de l'  >  **appelant**vocal.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="c7ffc-116">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-116">Click **Add**.</span></span> <br>
<span data-ttu-id="c7ffc-117">![Capture d’écran de la nouvelle page de stratégie d’ID d’appelant dans le centre d’administration](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="c7ffc-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="c7ffc-118">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="c7ffc-119">À partir de cet emplacement, sélectionnez les paramètres de votre choix :</span><span class="sxs-lookup"><span data-stu-id="c7ffc-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="c7ffc-120">**Bloquer l’ID d’appelant entrant**: activez ce paramètre pour bloquer l’identification de l’appelant lors de l’affichage d’appels entrants.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="c7ffc-121">**Remplacer la stratégie d’ID d’appelant**: activez ce paramètre pour permettre aux utilisateurs de remplacer les paramètres de la stratégie concernant l’affichage de leur numéro pour les appelants.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="c7ffc-122">Cela signifie que les utilisateurs peuvent décider d’afficher leur ID d’appelant.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="c7ffc-123">Pour plus d’informations, reportez-vous à [contrôle de l’ID d’appelant sortant par l’utilisateur final](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="c7ffc-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="c7ffc-124">**Remplacez l’identification de l’appelant**par : définissez l’ID d’appelant à afficher pour les utilisateurs en sélectionnant l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7ffc-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="c7ffc-125">**Numéro de**l’utilisateur : affiche le numéro de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="c7ffc-126">**Numéro de service**: vous permet de définir un numéro de téléphone de service à afficher en tant qu’identifiant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="c7ffc-127">**Anonyme**: affiche l’ID de l’appelant comme anonyme.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="c7ffc-128">**Remplacez l’identification de l’appelant par ce numéro de service**: sélectionnez un numéro de service pour remplacer l’identifiant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="c7ffc-129">Cette option n’est disponible que si vous avez sélectionné **numéro de service** dans **remplacer l’identifiant de l’appelant par**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="c7ffc-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="c7ffc-131">Modifier une stratégie d’ID d’appelant</span><span class="sxs-lookup"><span data-stu-id="c7ffc-131">Edit a caller ID policy</span></span>

<span data-ttu-id="c7ffc-132">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="c7ffc-133">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à stratégies d’identification de l'  >  **appelant**vocal.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="c7ffc-134">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c7ffc-135">Modifiez les paramètres souhaités, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="c7ffc-136">Attribuer une stratégie d’ID d’appelant personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c7ffc-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="c7ffc-137">Vous pouvez utiliser le centre d’administration de Microsoft teams pour attribuer une stratégie personnalisée à un ou plusieurs utilisateurs ou au module PowerShell Skype entreprise et attribuer une stratégie personnalisée aux utilisateurs d’un groupe, tels qu’un groupe de sécurité ou un groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a><span data-ttu-id="c7ffc-138">Assigner une stratégie d’ID de ligne d’appelant personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c7ffc-138">Assign a custom caller line ID policy to users</span></span>

<span data-ttu-id="c7ffc-139">Pour attribuer une stratégie à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="c7ffc-139">To assign a policy to one user:</span></span>

1. <span data-ttu-id="c7ffc-140">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="c7ffc-141">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-141">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="c7ffc-142">Sous **stratégie d’identification**de l’appelant, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-142">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

<span data-ttu-id="c7ffc-143">Pour attribuer une stratégie à plusieurs utilisateurs à la fois :</span><span class="sxs-lookup"><span data-stu-id="c7ffc-143">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="c7ffc-144">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="c7ffc-145">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-145">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="c7ffc-146">Pour sélectionner tous les utilisateurs, cliquez sur l' &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-146">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="c7ffc-147">Cliquez sur **modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-147">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="c7ffc-148">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7ffc-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c7ffc-149">Accédez au **Centre d’administration Microsoft teams**  >  **Voice**  >  **Caller ID policies**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-149">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="c7ffc-150">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="c7ffc-151">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="c7ffc-152">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="c7ffc-153">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c7ffc-154">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-154">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="c7ffc-155">Assigner une stratégie d’ID d’appelant personnalisée aux utilisateurs d’un groupe</span><span class="sxs-lookup"><span data-stu-id="c7ffc-155">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="c7ffc-156">Vous pouvez assigner une stratégie personnalisée à plusieurs utilisateurs que vous avez déjà identifiés.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-156">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="c7ffc-157">Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="c7ffc-158">Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="c7ffc-159">Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7ffc-159">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="c7ffc-160">Dans cet exemple, nous affectons une stratégie de capot d’appelant personnalisé appelée stratégie d’ID d’appelant à tous les utilisateurs du groupe de support technique contoso.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-160">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="c7ffc-161">Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="c7ffc-161">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="c7ffc-162">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-162">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="c7ffc-163">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-163">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="c7ffc-164">Attribuez à tous les utilisateurs du groupe une stratégie d’ID d’appelant particulière.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-164">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="c7ffc-165">Dans cet exemple, la stratégie d’ID d’appelant est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-165">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="c7ffc-166">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="c7ffc-166">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="c7ffc-167">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c7ffc-167">Related topics</span></span>

- [<span data-ttu-id="c7ffc-168">Nouveau-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="c7ffc-168">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [<span data-ttu-id="c7ffc-169">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="c7ffc-169">Assign policies to your users in Teams</span></span>](assign-policies.md)
