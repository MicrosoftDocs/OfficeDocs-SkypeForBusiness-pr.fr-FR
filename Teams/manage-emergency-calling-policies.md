---
title: Gérer les stratégies d’appels d’urgence Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe quand un Teams de votre organisation effectue un appel d’urgence.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120565"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="fc310-103">Gérer les stratégies d’appels d’urgence Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc310-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="fc310-104">Si votre [](set-up-calling-plans.md) organisation utilise des plans d’appel ou un routage direct [Système téléphonique,](direct-routing-landing-page.md)vous pouvez utiliser des stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe lorsqu’un utilisateur Teams dans votre organisation effectue un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fc310-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="fc310-105">Vous pouvez définir les personnes à informer et la manière dont ils sont avertis lorsqu’un utilisateur affecté à la stratégie appelle les services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fc310-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="fc310-106">Par exemple, vous pouvez configurer les paramètres de stratégie pour avertir automatiquement le service de sécurité de votre organisation et lui faire écouter les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fc310-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="fc310-107">Pour gérer les stratégies d’appel d’urgence, vous devez vous rendre dans le Centre d’administration Microsoft Teams d’urgence ou à l’aide de  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc310-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="fc310-108">Les stratégies peuvent être affectées à des utilisateurs et [à des sites réseau.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fc310-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="fc310-109">Pour les utilisateurs, vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="fc310-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="fc310-110">Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="fc310-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="fc310-111">N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas le renommer ou le supprimer.</span><span class="sxs-lookup"><span data-stu-id="fc310-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="fc310-112">Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="fc310-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="fc310-113">Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace la stratégie qui lui est affectée.</span><span class="sxs-lookup"><span data-stu-id="fc310-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="fc310-114">Créer une stratégie personnalisée d’appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="fc310-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fc310-115">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc310-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fc310-116">Dans le navigation gauche du centre Microsoft Teams d’administration, allez sur Stratégies d’urgence vocale, puis cliquez sur  >   **l’onglet Stratégies d’appel.**</span><span class="sxs-lookup"><span data-stu-id="fc310-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="fc310-117">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fc310-117">Click **Add**.</span></span>
3. <span data-ttu-id="fc310-118">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="fc310-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="fc310-119">Définissez la façon dont vous voulez avertir les personnes de votre organisation, généralement le service de sécurité, lorsqu’un appel d’urgence est effectué.</span><span class="sxs-lookup"><span data-stu-id="fc310-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="fc310-120">Pour ce faire, sous **Mode de notification,** sélectionnez l’une des sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc310-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="fc310-121">**Envoyer une notification uniquement**: un message Teams conversation instantanée est envoyé aux utilisateurs et groupes que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="fc310-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="fc310-122">Conférence en mode muet impossible d’activer le son : un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez et ils peuvent écouter la conversation (mais ne peuvent pas y participer) entre l’appelant et l’opérateur PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="fc310-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="fc310-123">Conférence en mode muet, mais possibilité d’activer le son : un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez, et ils peuvent activer le son pour écouter l’appelant et participer à la conversation entre l’appelant et l’opérateur PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="fc310-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="fc310-124">Si vous avez sélectionné l’un des modes de **notification** muet, dans la zone Numéros pour appeler les **notifications** d’appel d’urgence, vous pouvez entrer le numéro de téléphone PSTN d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fc310-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="fc310-125">Par exemple, entrez le numéro du service de sécurité de votre organisation, qui recevra un appel lorsqu’un appel d’urgence sera effectué et pourra ensuite écouter l’appel.</span><span class="sxs-lookup"><span data-stu-id="fc310-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="fc310-126">Le téléphone PSTN ne peut pas être réactive même lorsque le mode est réglé sur Conférence en mode Muet, mais est en mesure **d’activer le son.**</span><span class="sxs-lookup"><span data-stu-id="fc310-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="fc310-127">Recherchez et sélectionnez un ou plusieurs utilisateurs ou groupes, tels que le service de sécurité de votre organisation, pour être informé lorsqu’un appel d’urgence est effectué.</span><span class="sxs-lookup"><span data-stu-id="fc310-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="fc310-128">La notification peut être envoyée à des adresses e-mail d’utilisateurs, de groupes de distribution et de groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="fc310-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="fc310-129">Un maximum de 50 utilisateurs peuvent en être informés.</span><span class="sxs-lookup"><span data-stu-id="fc310-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="fc310-130">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="fc310-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fc310-131">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc310-131">Using PowerShell</span></span>

<span data-ttu-id="fc310-132">Voir [New-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="fc310-132">See [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="fc310-133">Modifier une stratégie d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="fc310-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fc310-134">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc310-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="fc310-135">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="fc310-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="fc310-136">Dans le navigation gauche du centre Microsoft Teams d’administration, allez sur Stratégies d’urgence vocale, puis cliquez sur  >   **l’onglet Stratégies d’appel.**</span><span class="sxs-lookup"><span data-stu-id="fc310-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="fc310-137">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fc310-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="fc310-138">A apporter les modifications de votre souhaitez, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="fc310-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fc310-139">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc310-139">Using PowerShell</span></span>

<span data-ttu-id="fc310-140">Voir [Set-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="fc310-140">See [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="fc310-141">Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fc310-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="fc310-142">Voir aussi [Grant-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="fc310-142">See also [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="fc310-143">Affecter une stratégie personnalisée d’appel d’urgence à un site réseau</span><span class="sxs-lookup"><span data-stu-id="fc310-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="fc310-144">Utilisez la [cmdlet Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) pour affecter une stratégie d’appel d’urgence à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="fc310-144">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="fc310-145">L’exemple suivant montre comment affecter une stratégie appelée Stratégie d’appel d’urgence de Contoso 1 au site Site1.</span><span class="sxs-lookup"><span data-stu-id="fc310-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="fc310-146">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="fc310-146">Related topics</span></span>

[<span data-ttu-id="fc310-147">Gérer les stratégies de routage d’appel d’urgence Teams</span><span class="sxs-lookup"><span data-stu-id="fc310-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="fc310-148">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc310-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="fc310-149">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fc310-149">Assign policies to your users in Teams</span></span>](assign-policies.md)