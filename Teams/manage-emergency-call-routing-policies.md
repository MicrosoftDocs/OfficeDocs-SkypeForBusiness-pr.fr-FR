---
title: Gérer les stratégies de routage d’appel d’urgence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’acheminement des appels d’urgence dans Microsoft teams pour configurer des numéros d’urgence et définir le mode de routage des appels d’urgence.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 67ef3bb5700c223f3057ef0ba44c9df07a2e7be6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217695"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="7f43d-103">Gérer les stratégies d’acheminement des appels d’urgence dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="7f43d-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="7f43d-104">Si vous avez déployé le [routage direct du système téléphonique](direct-routing-landing-page.md) au sein de votre organisation, vous pouvez utiliser les stratégies d’acheminement des appels d’urgence de Microsoft teams pour configurer les numéros d’urgence et spécifier le mode de routage des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="7f43d-105">Une stratégie d’acheminement des appels d’urgence détermine si les services d’urgence améliorés sont activés pour les utilisateurs auxquels la stratégie est affectée, les numéros utilisés pour appeler les services d’urgence (par exemple, 911 aux États-Unis) et comment les appels vers les services d’urgence sont routés.</span><span class="sxs-lookup"><span data-stu-id="7f43d-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="7f43d-106">Vous gérez les stratégies d’acheminement des appels **Voice**d’urgence en accédant à  >  **stratégies d’urgence** vocale dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f43d-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="7f43d-107">Elles peuvent être attribuées à des utilisateurs et des [sites réseau](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7f43d-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="7f43d-108">Pour les utilisateurs, vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="7f43d-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="7f43d-109">Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="7f43d-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="7f43d-110">Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer.</span><span class="sxs-lookup"><span data-stu-id="7f43d-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="7f43d-111">Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="7f43d-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="7f43d-112">Si vous avez affecté une stratégie d’acheminement des appels d’urgence à un site réseau et à un utilisateur et que, si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7f43d-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="7f43d-113">Créer une stratégie d’acheminement des appels d’urgence personnalisée</span><span class="sxs-lookup"><span data-stu-id="7f43d-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="7f43d-114">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f43d-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="7f43d-115">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet stratégies de routage des **appels** .</span><span class="sxs-lookup"><span data-stu-id="7f43d-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="7f43d-116">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="7f43d-116">Click **Add**.</span></span>
3. <span data-ttu-id="7f43d-117">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="7f43d-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="7f43d-118">Pour activer les appels d’urgence dynamiques, activez les **appels d’urgence dynamiques**.</span><span class="sxs-lookup"><span data-stu-id="7f43d-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="7f43d-119">Lorsque les appels d’urgence dynamiques sont activés, teams récupère les informations de stratégie et d’emplacement du service et inclut ces informations dans le cadre de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="7f43d-120">Définissez un ou plusieurs numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="7f43d-121">Pour ce faire, sous **numéros d’urgence**, cliquez sur **Ajouter**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f43d-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="7f43d-122">**Chaîne de numérotation d’urgence**: entrez la chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="7f43d-123">Cette chaîne de numérotation indique qu’un appel est un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="7f43d-124">Pour le routage direct, nous faisons en sorte que les clients teams envoient les appels d’urgence en utilisant le signe « + » en face de la chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="7f43d-125">Tant que la transition ne s’est pas terminée, le modèle d’itinéraire vocal correspondant à une chaîne de numérotation d’urgence doit garantir la prise de correspondances pour les chaînes qui contiennent et ne possèdent pas de « + », comme 911 et + 911.</span><span class="sxs-lookup"><span data-stu-id="7f43d-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="7f43d-126">Par exemple, ^ \\ + ? 911 ou. \*.</span><span class="sxs-lookup"><span data-stu-id="7f43d-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="7f43d-127">**Masque de numérotation d’urgence**: pour chaque numéro d’urgence, vous pouvez spécifier zéro ou plusieurs masques de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="7f43d-128">Un masque de numérotation correspond au numéro que vous souhaitez traduire dans la valeur de la chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="7f43d-129">Cela permet d’appeler d’autres numéros d’urgence et de toujours avoir accès aux services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="7f43d-130">Par exemple, vous ajoutez 112 comme masque de numérotation d’urgence, qui est le numéro de service d’urgence pour la plupart des services d’Europe et 911 comme chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7f43d-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="7f43d-131">Un utilisateur de teams d’Europe qui ne sait pas que 911 correspond au numéro d’urgence aux États-Unis et lorsqu’il appelle 112, l’appel est effectué à 911.</span><span class="sxs-lookup"><span data-stu-id="7f43d-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="7f43d-132">Pour définir plusieurs masques de numérotation, séparez chaque valeur par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="7f43d-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="7f43d-133">Par exemple, 112 ; 212.</span><span class="sxs-lookup"><span data-stu-id="7f43d-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="7f43d-134">**Enregistrement d’utilisation RTC**: sélectionnez l’enregistrement d’utilisation du réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="7f43d-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="7f43d-135">L’enregistrement d’utilisation RTC détermine quel itinéraire est utilisé pour acheminer les appels d’urgence de la part des utilisateurs autorisés à les utiliser.</span><span class="sxs-lookup"><span data-stu-id="7f43d-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="7f43d-136">L’itinéraire associé à cette utilisation doit pointer vers une ligne SIP (Session Initiation Protocol) dédiée aux appels d’urgence ou à une passerelle ELIN (Emergency Identification Number) qui route les appels d’urgence vers le point de réponse de sécurité publique le plus proche (PSAPI).</span><span class="sxs-lookup"><span data-stu-id="7f43d-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f43d-137">Les chaînes de numérotation et les masques de numérotation doivent être uniques au sein d’une stratégie.</span><span class="sxs-lookup"><span data-stu-id="7f43d-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="7f43d-138">Cela signifie que pour une stratégie, vous pouvez définir plusieurs numéros d’urgence et définir plusieurs masques de numérotation pour une chaîne de numérotation, mais chaque chaîne de numérotation et chaque masque de numérotation doivent être utilisés une seule fois.</span><span class="sxs-lookup"><span data-stu-id="7f43d-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="7f43d-139">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7f43d-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="7f43d-140">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f43d-140">Using PowerShell</span></span>

<span data-ttu-id="7f43d-141">Voir [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="7f43d-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="7f43d-142">Modifier une stratégie d’acheminement des appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="7f43d-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="7f43d-143">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f43d-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="7f43d-144">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="7f43d-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="7f43d-145">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet stratégies de routage des **appels** .</span><span class="sxs-lookup"><span data-stu-id="7f43d-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="7f43d-146">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="7f43d-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="7f43d-147">Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7f43d-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="7f43d-148">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f43d-148">Using PowerShell</span></span>

<span data-ttu-id="7f43d-149">Voir [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="7f43d-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="7f43d-150">Attribuer une stratégie d’acheminement d’appel d’urgence personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7f43d-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="7f43d-151">Voir aussi [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="7f43d-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="7f43d-152">Affecter une stratégie d’acheminement d’appel d’urgence personnalisée à un site réseau</span><span class="sxs-lookup"><span data-stu-id="7f43d-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="7f43d-153">Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) pour attribuer une stratégie d’acheminement des appels d’urgence à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="7f43d-153">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="7f43d-154">Cet exemple montre comment assigner une stratégie appelée politique de routage des appels d’urgence 1 au site site1.</span><span class="sxs-lookup"><span data-stu-id="7f43d-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="7f43d-155">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="7f43d-155">Related topics</span></span>

[<span data-ttu-id="7f43d-156">Gérer les stratégies d’appel d’urgence dans teams</span><span class="sxs-lookup"><span data-stu-id="7f43d-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="7f43d-157">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f43d-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="7f43d-158">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="7f43d-158">Assign policies to your users in Teams</span></span>](assign-policies.md)
