---
title: Gérer les stratégies d’acheminement des appels d’urgence dans Microsoft teams
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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies de routage des appels d’urgence pour la fonctionnalité de E911 dynamique dans Microsoft Teams.
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: aed3b3d3cbd1023a3370c3c271e07a61179447da
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615804"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="e7b23-103">Gérer les stratégies d’acheminement des appels d’urgence dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e7b23-103">Manage emergency call routing policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="e7b23-104">Si vous avez déployé le routage direct du système téléphonique au sein de votre organisation, vous pouvez utiliser les stratégies d’acheminement des appels d’urgence de Microsoft teams pour configurer les numéros d’urgence et spécifier le mode de routage des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-104">If you've deployed Phone System Direct Routing in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="e7b23-105">Une stratégie d’acheminement des appels d’urgence détermine si les services d’urgence améliorés sont activés pour les utilisateurs auxquels la stratégie est affectée, les numéros utilisés pour appeler les services d’urgence (par exemple, 911 aux États-Unis) et comment les appels vers les services d’urgence sont routés.</span><span class="sxs-lookup"><span data-stu-id="e7b23-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="e7b23-106">Vous gérez les stratégies d’acheminement des appels d’urgence en accédant à**stratégies d’urgence** **vocale** > dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7b23-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="e7b23-107">Elles peuvent être attribuées à des utilisateurs et des [sites réseau](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e7b23-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="e7b23-108">Pour les utilisateurs, vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e7b23-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="e7b23-109">Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e7b23-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e7b23-110">Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer.</span><span class="sxs-lookup"><span data-stu-id="e7b23-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="e7b23-111">Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e7b23-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="e7b23-112">Si vous avez affecté une stratégie d’acheminement des appels d’urgence à un site réseau et à un utilisateur et que, si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e7b23-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="e7b23-113">Créer une stratégie d’acheminement des appels d’urgence personnalisée</span><span class="sxs-lookup"><span data-stu-id="e7b23-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e7b23-114">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e7b23-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e7b23-115">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’urgence** **vocale** > , puis cliquez sur l’onglet stratégies de **routage des appels** .</span><span class="sxs-lookup"><span data-stu-id="e7b23-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="e7b23-116">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-116">Click **Add**.</span></span>
3. <span data-ttu-id="e7b23-117">Entrez le nom et la description de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e7b23-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e7b23-118">Pour activer des services d’urgence avancés, activez l' **avancée services d’urgence**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-118">To enable enhanced emergency services, turn on **Enhanced emergency services**.</span></span> <span data-ttu-id="e7b23-119">Lorsque les services d’urgence améliorés sont activés, teams récupère les informations de stratégie et d’emplacement du service et inclut ces informations dans le cadre de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-119">When enhanced emergency services is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="e7b23-120">Définissez un ou plusieurs numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-120">Define one of more emergency numbers.</span></span> <span data-ttu-id="e7b23-121">Pour cela, sous **numéros d’urgence**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e7b23-121">To do this, under **Emergency numbers**, do the following:</span></span>
    1. <span data-ttu-id="e7b23-122">**Chaîne de numérotation d’urgence**: entrez la chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="e7b23-123">Cette chaîne de numérotation indique qu’un appel est un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-123">This dial string indicates that a call is an emergency call.</span></span>
    2. <span data-ttu-id="e7b23-124">**Masque de numérotation d’urgence**: pour chaque numéro d’urgence, vous pouvez spécifier zéro ou plusieurs masques de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-124">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="e7b23-125">Un masque de numérotation correspond au numéro que vous souhaitez traduire dans la valeur de la chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-125">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="e7b23-126">Cela permet d’appeler d’autres numéros d’urgence et de toujours avoir accès aux services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="e7b23-127">Par exemple, vous ajoutez 112 comme masque de numérotation d’urgence, qui est le numéro de service d’urgence pour la plupart des services d’Europe et 911 comme chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7b23-127">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="e7b23-128">Un utilisateur de teams d’Europe qui ne sait pas que 911 correspond au numéro d’urgence aux États-Unis et lorsqu’il appelle 112, l’appel est effectué à 911.</span><span class="sxs-lookup"><span data-stu-id="e7b23-128">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="e7b23-129">Pour définir plusieurs masques de numérotation, séparez chaque valeur par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="e7b23-129">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="e7b23-130">Par exemple, 112 ; 212.</span><span class="sxs-lookup"><span data-stu-id="e7b23-130">For example, 112;212.</span></span>
    3. <span data-ttu-id="e7b23-131">**Utilisation PSTN**: sélectionnez l’utilisation de réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="e7b23-131">**PSTN Usage**: Select the public switched telephone network (PSTN) usage.</span></span> <span data-ttu-id="e7b23-132">L’utilisation RTC est utilisée pour déterminer le type d’itinéraire utilisé pour diriger les appels d’urgence des utilisateurs autorisés à les utiliser.</span><span class="sxs-lookup"><span data-stu-id="e7b23-132">The PSTN usage is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="e7b23-133">L’itinéraire associé à cette utilisation doit pointer vers un Trunk SIP dédié aux appels d’urgence ou à une passerelle ELIN (Emergency Identification Number) qui route les appels d’urgence vers le point de réponse de sécurité publique le plus proche (PSAPI).</span><span class="sxs-lookup"><span data-stu-id="e7b23-133">The route associated with this usage should point to an SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7b23-134">Les chaînes de numérotation et les masques de numérotation doivent être uniques au sein d’une stratégie.</span><span class="sxs-lookup"><span data-stu-id="e7b23-134">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="e7b23-135">Cela signifie que pour une stratégie, vous pouvez définir plusieurs numéros d’urgence et définir plusieurs masques de numérotation pour une chaîne de numérotation, mais chaque chaîne de numérotation et chaque masque de numérotation doivent être utilisés une seule fois.</span><span class="sxs-lookup"><span data-stu-id="e7b23-135">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="e7b23-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-136">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e7b23-137">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7b23-137">Using PowerShell</span></span>

<span data-ttu-id="e7b23-138">Voir [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e7b23-138">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="e7b23-139">Modifier une stratégie d’acheminement des appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="e7b23-139">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e7b23-140">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e7b23-140">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e7b23-141">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="e7b23-141">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="e7b23-142">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’urgence** **vocale** > , puis cliquez sur l’onglet stratégies de **routage des appels** .</span><span class="sxs-lookup"><span data-stu-id="e7b23-142">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="e7b23-143">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e7b23-144">Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-144">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e7b23-145">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7b23-145">Using PowerShell</span></span>

<span data-ttu-id="e7b23-146">Voir [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e7b23-146">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="e7b23-147">Attribuer une stratégie d’acheminement d’appel d’urgence personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e7b23-147">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e7b23-148">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e7b23-148">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e7b23-149">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e7b23-149">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e7b23-150">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-150">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="e7b23-151">Sous **stratégie d’acheminement des appels d’urgence**, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-151">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="e7b23-152">Pour attribuer une stratégie d’équipe personnalisée à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="e7b23-152">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="e7b23-153">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7b23-153">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e7b23-154">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’urgence** **vocale** > , puis cliquez sur l’onglet stratégies de **routage des appels** .</span><span class="sxs-lookup"><span data-stu-id="e7b23-154">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="e7b23-155">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e7b23-155">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e7b23-156">Sélectionnez **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-156">Select **Manage users**.</span></span>
4. <span data-ttu-id="e7b23-157">Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e7b23-158">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="e7b23-158">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e7b23-159">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7b23-159">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e7b23-160">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7b23-160">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="e7b23-161">Attribuer une stratégie d’acheminement d’appel d’urgence personnalisée à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="e7b23-161">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="e7b23-162">Voir [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e7b23-162">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="e7b23-163">Affecter une stratégie d’acheminement d’appel d’urgence personnalisée aux utilisateurs d’un groupe</span><span class="sxs-lookup"><span data-stu-id="e7b23-163">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="e7b23-164">Il est possible que vous souhaitiez affecter une stratégie d’acheminement d’appel d’urgence personnalisée à plusieurs utilisateurs déjà identifiés.</span><span class="sxs-lookup"><span data-stu-id="e7b23-164">You may want to assign a custom emergency call routing policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="e7b23-165">Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité ou de distribution.</span><span class="sxs-lookup"><span data-stu-id="e7b23-165">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="e7b23-166">Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="e7b23-166">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="e7b23-167">Dans cet exemple, nous affectons une stratégie appelée politique d’acheminement des appels d’urgence à tous les utilisateurs du groupe RH de contoso.</span><span class="sxs-lookup"><span data-stu-id="e7b23-167">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="e7b23-168">Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="e7b23-168">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e7b23-169">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="e7b23-169">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="e7b23-170">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="e7b23-170">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e7b23-171">Attribuez à tous les utilisateurs du groupe une stratégie d’équipe particulière.</span><span class="sxs-lookup"><span data-stu-id="e7b23-171">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="e7b23-172">Dans cet exemple, il s’agit de la stratégie d’acheminement des appels d’urgence HR.</span><span class="sxs-lookup"><span data-stu-id="e7b23-172">In this example, it's HR Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="e7b23-173">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="e7b23-173">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="e7b23-174">Affecter une stratégie d’acheminement d’appel d’urgence personnalisée à un site réseau</span><span class="sxs-lookup"><span data-stu-id="e7b23-174">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="e7b23-175">Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) pour attribuer une stratégie d’acheminement des appels d’urgence à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="e7b23-175">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="e7b23-176">Cet exemple montre comment assigner une stratégie appelée politique de routage des appels d’urgence 1 au site site1.</span><span class="sxs-lookup"><span data-stu-id="e7b23-176">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="e7b23-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7b23-177">Related topics</span></span>

- [<span data-ttu-id="e7b23-178">Gérer les stratégies d’appel d’urgence dans teams</span><span class="sxs-lookup"><span data-stu-id="e7b23-178">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="e7b23-179">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7b23-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
