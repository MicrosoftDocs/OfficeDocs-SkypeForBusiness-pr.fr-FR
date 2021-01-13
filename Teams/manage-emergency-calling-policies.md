---
title: Gérer les stratégies d’appel d’urgence dans Microsoft Teams
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
description: Découvrez comment utiliser et gérer les stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe lorsqu’un utilisateur de Teams dans votre organisation effectue un appel d’urgence.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1e516252317a0e5f14e705b674255048fb3defb5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804684"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="605c5-103">Gérer les stratégies d’appel d’urgence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="605c5-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="605c5-104">Si votre organisation utilise des [plans](set-up-calling-plans.md) d’appels ou un routage direct de système téléphonique [déployé,](direct-routing-landing-page.md)vous pouvez utiliser les stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe lorsqu’un utilisateur de Teams dans votre organisation effectue un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="605c5-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="605c5-105">Vous pouvez définir les personnes à informer et la manière dont ils sont avertis lorsqu’un utilisateur affecté à la stratégie appelle les services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="605c5-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="605c5-106">Par exemple, vous pouvez configurer les paramètres de stratégie pour avertir automatiquement le service de sécurité de votre organisation et lui faire écouter les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="605c5-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="605c5-107">Pour gérer les stratégies d’appel d’urgence, vous devez utiliser le Centre d’administration Microsoft Teams pour utiliser les stratégies d’urgence vocales  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="605c5-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="605c5-108">Les stratégies peuvent être affectées à des utilisateurs et [à des sites réseau.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="605c5-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="605c5-109">Pour les utilisateurs, vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="605c5-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="605c5-110">Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="605c5-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="605c5-111">N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas le renommer ou le supprimer.</span><span class="sxs-lookup"><span data-stu-id="605c5-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="605c5-112">Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="605c5-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="605c5-113">Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie affectée au site réseau remplace la stratégie qui lui est affectée.</span><span class="sxs-lookup"><span data-stu-id="605c5-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="605c5-114">Créer une stratégie personnalisée d’appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="605c5-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="605c5-115">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="605c5-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="605c5-116">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez sur Stratégies d’urgence vocale, puis cliquez sur  >   **l’onglet Stratégies d’appel.**</span><span class="sxs-lookup"><span data-stu-id="605c5-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="605c5-117">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="605c5-117">Click **Add**.</span></span>
3. <span data-ttu-id="605c5-118">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="605c5-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="605c5-119">Définissez la façon dont vous voulez avertir les personnes de votre organisation, généralement le service de sécurité, lorsqu’un appel d’urgence est effectué.</span><span class="sxs-lookup"><span data-stu-id="605c5-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="605c5-120">Pour ce faire, sous **Mode de notification,** sélectionnez l’une des sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="605c5-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="605c5-121">**Envoyer une notification uniquement**: un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="605c5-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="605c5-122">Conférence en cours, mais muet : un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez et ils peuvent écouter (mais ne peuvent pas participer) à la conversation entre l’appelant et l’opérateur PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="605c5-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="605c5-123"> Conférences au téléphone et réactives **(bientôt disponible)**: un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez, et ils peuvent activer le son pour écouter l’appelant et participer à la conversation entre l’appelant et l’opérateur CENTRE.PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="605c5-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="605c5-124">Si vous avez sélectionné la conférence entrante mais que vous êtes en mode de **notification** muet, dans la zone des **notifications** d’appel d’urgence numérotation pour les numéros de téléphone, vous pouvez entrer le numéro de téléphone PSTN d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="605c5-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="605c5-125">Par exemple, entrez le numéro du service de sécurité de votre organisation, qui recevra un appel lorsqu’un appel d’urgence sera effectué et pourra ensuite écouter l’appel.</span><span class="sxs-lookup"><span data-stu-id="605c5-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="605c5-126">Recherchez et sélectionnez un ou plusieurs utilisateurs ou groupes, tels que le service de sécurité de votre organisation, pour être informé lorsqu’un appel d’urgence est effectué.</span><span class="sxs-lookup"><span data-stu-id="605c5-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="605c5-127">La notification peut être envoyée à des adresses e-mail d’utilisateurs, de groupes de distribution et de groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="605c5-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="605c5-128">Un maximum de 50 utilisateurs peuvent en être informés.</span><span class="sxs-lookup"><span data-stu-id="605c5-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="605c5-129">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="605c5-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="605c5-130">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="605c5-130">Using PowerShell</span></span>

<span data-ttu-id="605c5-131">Voir [New-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="605c5-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="605c5-132">Modifier une stratégie d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="605c5-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="605c5-133">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="605c5-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="605c5-134">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="605c5-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="605c5-135">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez sur Stratégies d’urgence vocale, puis cliquez sur  >   **l’onglet Stratégies d’appel.**</span><span class="sxs-lookup"><span data-stu-id="605c5-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="605c5-136">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="605c5-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="605c5-137">A apporter les modifications de votre souhaitez, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="605c5-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="605c5-138">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="605c5-138">Using PowerShell</span></span>

<span data-ttu-id="605c5-139">Voir [Set-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="605c5-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="605c5-140">Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="605c5-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="605c5-141">Voir également [Grant-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="605c5-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="605c5-142">Affecter une stratégie personnalisée d’appel d’urgence à un site réseau</span><span class="sxs-lookup"><span data-stu-id="605c5-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="605c5-143">Utilisez la [cmdlet Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) pour affecter une stratégie d’appel d’urgence à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="605c5-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="605c5-144">L’exemple suivant montre comment affecter une stratégie appelée Stratégie d’appel d’urgence de Contoso 1 au site Site1.</span><span class="sxs-lookup"><span data-stu-id="605c5-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="605c5-145">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="605c5-145">Related topics</span></span>

[<span data-ttu-id="605c5-146">Gérer les stratégies de routage d’appel d’urgence dans Teams</span><span class="sxs-lookup"><span data-stu-id="605c5-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="605c5-147">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="605c5-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="605c5-148">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="605c5-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
