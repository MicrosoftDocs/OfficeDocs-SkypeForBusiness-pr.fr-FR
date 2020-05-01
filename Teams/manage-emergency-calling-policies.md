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
ms.openlocfilehash: 62a6314435aa3af44d0c44ab6a6790212c62d8de
ms.sourcegitcommit: 5692900c0fc0a2552fe3f8ece40920c839e1ea23
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43952433"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="f3fd5-103">Gérer les stratégies d’appel d’urgence dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="f3fd5-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="f3fd5-104">Si votre organisation utilise des plans d’appels ou un routage direct du système téléphonique, vous pouvez utiliser les politiques d’appel d’urgence de Microsoft teams pour définir ce qui se produit quand un utilisateur de teams de votre organisation effectue un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-104">If your organization uses Calling Plans or deployed Phone System Direct Routing, you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="f3fd5-105">Vous pouvez définir la personne à notifier et la manière dont elle est avertie lorsqu’un utilisateur auquel cette stratégie appelle des services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="f3fd5-106">Par exemple, vous pouvez configurer des paramètres de stratégie pour avertir automatiquement le support technique de votre organisation et les informer dans les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="f3fd5-107">Vous pouvez gérer les stratégies d’appel d’urgence en accédant à**stratégies d’urgence** **vocale** > dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="f3fd5-108">Elles peuvent être attribuées à des utilisateurs et des [sites réseau](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f3fd5-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="f3fd5-109">Pour les utilisateurs, vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="f3fd5-110">Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="f3fd5-111">Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="f3fd5-112">Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="f3fd5-113">Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur et que ce dernier se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="f3fd5-114">Créer une stratégie d’appel d’urgence personnalisée</span><span class="sxs-lookup"><span data-stu-id="f3fd5-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f3fd5-115">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3fd5-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="f3fd5-116">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’urgence** **vocale** > , puis cliquez sur l’onglet **politiques d’appel** .</span><span class="sxs-lookup"><span data-stu-id="f3fd5-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="f3fd5-117">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-117">Click **Add**.</span></span>
3. <span data-ttu-id="f3fd5-118">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="f3fd5-119">Définissez la manière dont vous souhaitez informer les membres de votre organisation, en général le centre de sécurité, lors de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="f3fd5-120">Pour ce faire, sous **mode de notification**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f3fd5-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="f3fd5-121">**Envoyer la notification uniquement**: un message de discussion teams est envoyé aux utilisateurs et aux groupes que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="f3fd5-122">**Conférences lancées, mais qui ne sont**pas activées : un message de discussion d’équipes est envoyé aux utilisateurs et aux groupes que vous spécifiez et ils peuvent écouter (mais ne pas participer) à la conversation entre l’appelant et l’opérateur PSAPI.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="f3fd5-123">**Conférences dans et** activées **(bientôt disponible)**: un message de discussion d’équipes est envoyé aux utilisateurs et aux groupes que vous spécifiez, et ils peuvent basculer entre l’appelant et l’opérateur PSAPI.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="f3fd5-124">Si vous avez sélectionné la **conférence téléphonique en mode muet** , dans la boîte **de message numéro de téléphone pour les notifications** , vous pouvez entrer le numéro de téléphone PSTN d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-124">If you selected the **Conferenced in but are muted** notification mode, in the **Dial-out number for notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="f3fd5-125">Par exemple, entrez le numéro du centre de sécurité de votre organisation, qui recevra un appel en cas d’appel d’urgence et peut alors écouter l’appel.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="f3fd5-126">Recherchez et sélectionnez un ou plusieurs utilisateurs ou groupes, comme le centre de sécurité de votre organisation, pour avertir en cas d’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="f3fd5-127">La notification peut être envoyée aux adresses de courrier des utilisateurs, des groupes de distribution et des groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="f3fd5-128">Un maximum de 50 utilisateurs peut être notifié.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="f3fd5-129">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-129">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f3fd5-130">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3fd5-130">Using PowerShell</span></span>

<span data-ttu-id="f3fd5-131">Voir [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="f3fd5-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="f3fd5-132">Modifier une politique d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="f3fd5-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f3fd5-133">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3fd5-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f3fd5-134">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="f3fd5-135">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’urgence** **vocale** > , puis cliquez sur l’onglet **politiques d’appel** .</span><span class="sxs-lookup"><span data-stu-id="f3fd5-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="f3fd5-136">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="f3fd5-137">Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f3fd5-138">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3fd5-138">Using PowerShell</span></span>

<span data-ttu-id="f3fd5-139">Voir [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="f3fd5-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="f3fd5-140">Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f3fd5-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f3fd5-141">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3fd5-141">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="f3fd5-142">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-142">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f3fd5-143">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-143">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="f3fd5-144">Sous **stratégie d’appel d’urgence**, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-144">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="f3fd5-145">Pour attribuer une stratégie d’équipe personnalisée à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="f3fd5-145">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="f3fd5-146">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f3fd5-146">Or, you can also do the following:</span></span>

1. <span data-ttu-id="f3fd5-147">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’urgence** **vocale** > , puis cliquez sur l’onglet **politiques d’appel** .</span><span class="sxs-lookup"><span data-stu-id="f3fd5-147">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="f3fd5-148">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-148">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="f3fd5-149">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-149">Select **Manage users**.</span></span>
4. <span data-ttu-id="f3fd5-150">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-150">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="f3fd5-151">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-151">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f3fd5-152">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-152">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f3fd5-153">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3fd5-153">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="f3fd5-154">Affecter une stratégie d’appel d’urgence personnalisée à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f3fd5-154">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="f3fd5-155">Voir [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="f3fd5-155">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="f3fd5-156">Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs d’un groupe</span><span class="sxs-lookup"><span data-stu-id="f3fd5-156">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="f3fd5-157">Il est possible que vous souhaitiez affecter une stratégie d’appel d’urgence personnalisée à plusieurs utilisateurs déjà identifiés.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-157">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="f3fd5-158">Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-158">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="f3fd5-159">Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-159">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="f3fd5-160">Dans cet exemple, nous affectons une stratégie appelée stratégie d’appel d’urgence d’opérations à tous les utilisateurs du groupe opérations de contoso.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-160">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="f3fd5-161">Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="f3fd5-161">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="f3fd5-162">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-162">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="f3fd5-163">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-163">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="f3fd5-164">Attribuez à tous les utilisateurs du groupe une stratégie d’équipe particulière.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-164">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="f3fd5-165">Dans cet exemple, il s’agit de la stratégie d’acheminement des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-165">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="f3fd5-166">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-166">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="f3fd5-167">Affecter une stratégie d’appel d’urgence personnalisée à un site réseau</span><span class="sxs-lookup"><span data-stu-id="f3fd5-167">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="f3fd5-168">Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) pour attribuer une stratégie d’appel d’urgence à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-168">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="f3fd5-169">L’exemple suivant montre comment affecter une stratégie appelée stratégie d’appel d’urgence contoso 1 au site site1.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-169">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="f3fd5-170">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="f3fd5-170">Related topics</span></span>

- [<span data-ttu-id="f3fd5-171">Gérer les stratégies de routage des appels d’urgence dans teams</span><span class="sxs-lookup"><span data-stu-id="f3fd5-171">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="f3fd5-172">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3fd5-172">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
