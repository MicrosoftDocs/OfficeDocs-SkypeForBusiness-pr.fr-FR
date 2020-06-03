---
title: Gérer les stratégies d’appel d’urgence dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des politiques d’appel d’urgence dans Microsoft teams pour définir ce qui se passe quand un utilisateur de teams dans votre organisation effectue un appel d’urgence.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98d6fb5eba98701cddccb808e5670fb34a00efbf
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539481"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="4ac9e-103">Gérer les stratégies d’appel d’urgence dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4ac9e-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="4ac9e-104">Si votre organisation utilise des [plans d’appels](set-up-calling-plans.md) ou un [routage direct du système téléphonique](direct-routing-landing-page.md), vous pouvez utiliser les politiques d’appel d’urgence de Microsoft teams pour définir ce qui se produit quand un utilisateur de teams de votre organisation effectue un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="4ac9e-105">Vous pouvez définir la personne à notifier et la manière dont elle est avertie lorsqu’un utilisateur auquel cette stratégie appelle des services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="4ac9e-106">Par exemple, vous pouvez configurer des paramètres de stratégie pour avertir automatiquement le support technique de votre organisation et les informer dans les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="4ac9e-107">Vous pouvez gérer les stratégies d’appel d' **Voice**urgence en accédant à  >  **stratégies d’urgence** vocale dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="4ac9e-108">Elles peuvent être attribuées à des utilisateurs et des [sites réseau](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4ac9e-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="4ac9e-109">Pour les utilisateurs, vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="4ac9e-110">Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="4ac9e-111">Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="4ac9e-112">Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="4ac9e-113">Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur et que ce dernier se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="4ac9e-114">Créer une stratégie d’appel d’urgence personnalisée</span><span class="sxs-lookup"><span data-stu-id="4ac9e-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4ac9e-115">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ac9e-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4ac9e-116">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet politiques d' **appel** .</span><span class="sxs-lookup"><span data-stu-id="4ac9e-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="4ac9e-117">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-117">Click **Add**.</span></span>
3. <span data-ttu-id="4ac9e-118">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="4ac9e-119">Définissez la manière dont vous souhaitez informer les membres de votre organisation, en général le centre de sécurité, lors de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="4ac9e-120">Pour ce faire, sous **mode de notification**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4ac9e-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="4ac9e-121">**Envoyer la notification uniquement**: un message de discussion teams est envoyé aux utilisateurs et aux groupes que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="4ac9e-122">**Conférences lancées, mais qui ne sont**pas activées : un message de discussion d’équipes est envoyé aux utilisateurs et aux groupes que vous spécifiez et ils peuvent écouter (mais ne pas participer) à la conversation entre l’appelant et l’opérateur PSAPI.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="4ac9e-123">**Conférences dans et** activées **(bientôt disponible)**: un message de discussion d’équipes est envoyé aux utilisateurs et aux groupes que vous spécifiez, et ils peuvent basculer entre l’appelant et l’opérateur PSAPI.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="4ac9e-124">Si vous avez sélectionné la Conférence rendez-vous, mais que vous êtes en mode **muet** , dans la zone **numéros à composer pour les notifications d’appels d’urgence** , vous pouvez entrer un numéro de téléphone PSTN d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="4ac9e-125">Par exemple, entrez le numéro du centre de sécurité de votre organisation, qui recevra un appel en cas d’appel d’urgence et peut alors écouter l’appel.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="4ac9e-126">Recherchez et sélectionnez un ou plusieurs utilisateurs ou groupes, comme le centre de sécurité de votre organisation, pour avertir en cas d’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="4ac9e-127">La notification peut être envoyée aux adresses de courrier des utilisateurs, des groupes de distribution et des groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="4ac9e-128">Un maximum de 50 utilisateurs peut être notifié.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="4ac9e-129">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4ac9e-130">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ac9e-130">Using PowerShell</span></span>

<span data-ttu-id="4ac9e-131">Voir [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="4ac9e-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="4ac9e-132">Modifier une politique d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="4ac9e-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4ac9e-133">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ac9e-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4ac9e-134">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="4ac9e-135">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet politiques d' **appel** .</span><span class="sxs-lookup"><span data-stu-id="4ac9e-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="4ac9e-136">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4ac9e-137">Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4ac9e-138">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ac9e-138">Using PowerShell</span></span>

<span data-ttu-id="4ac9e-139">Voir [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="4ac9e-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="4ac9e-140">Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4ac9e-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4ac9e-141">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ac9e-141">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4ac9e-142">Pour attribuer une stratégie à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="4ac9e-142">To assign a policy to one user:</span></span>

1. <span data-ttu-id="4ac9e-143">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="4ac9e-144">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-144">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="4ac9e-145">Sous **stratégie d’appel d’urgence**, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-145">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="4ac9e-146">Pour affecter une stratégie à plusieurs utilisateurs à la fois :</span><span class="sxs-lookup"><span data-stu-id="4ac9e-146">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="4ac9e-147">Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-147">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="4ac9e-148">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-148">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="4ac9e-149">Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-149">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="4ac9e-150">Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-150">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="4ac9e-151">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4ac9e-151">Or, you can also do the following:</span></span>

1. <span data-ttu-id="4ac9e-152">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet politiques d' **appel** .</span><span class="sxs-lookup"><span data-stu-id="4ac9e-152">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="4ac9e-153">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="4ac9e-154">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="4ac9e-155">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="4ac9e-156">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="4ac9e-157">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-157">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4ac9e-158">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ac9e-158">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="4ac9e-159">Affecter une stratégie d’appel d’urgence personnalisée à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4ac9e-159">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="4ac9e-160">Voir [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="4ac9e-160">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="4ac9e-161">Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs d’un groupe</span><span class="sxs-lookup"><span data-stu-id="4ac9e-161">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="4ac9e-162">Il est possible que vous souhaitiez affecter une stratégie d’appel d’urgence personnalisée à plusieurs utilisateurs déjà identifiés.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-162">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="4ac9e-163">Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="4ac9e-164">Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="4ac9e-165">Dans cet exemple, nous affectons une stratégie appelée stratégie d’appel d’urgence d’opérations à tous les utilisateurs du groupe opérations de contoso.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-165">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="4ac9e-166">Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="4ac9e-166">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="4ac9e-167">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-167">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="4ac9e-168">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-168">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="4ac9e-169">Attribuez à tous les utilisateurs du groupe une stratégie d’équipe particulière.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-169">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="4ac9e-170">Dans cet exemple, il s’agit de la stratégie d’acheminement des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-170">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="4ac9e-171">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-171">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="4ac9e-172">Affecter une stratégie d’appel d’urgence personnalisée à un site réseau</span><span class="sxs-lookup"><span data-stu-id="4ac9e-172">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="4ac9e-173">Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) pour attribuer une stratégie d’appel d’urgence à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-173">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="4ac9e-174">L’exemple suivant montre comment affecter une stratégie appelée stratégie d’appel d’urgence contoso 1 au site site1.</span><span class="sxs-lookup"><span data-stu-id="4ac9e-174">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="4ac9e-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ac9e-175">Related topics</span></span>

- [<span data-ttu-id="4ac9e-176">Gérer les stratégies de routage des appels d’urgence dans teams</span><span class="sxs-lookup"><span data-stu-id="4ac9e-176">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="4ac9e-177">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ac9e-177">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="4ac9e-178">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="4ac9e-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
