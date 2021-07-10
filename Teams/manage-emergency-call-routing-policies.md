---
title: Gérer les stratégies de routage d’appel d’urgence pour le routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies de routage des appels d’urgence Microsoft Teams configurer des numéros d’urgence et spécifier la manière dont les appels d’urgence sont acheminés.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 86f73bed2e086efee666e5592ca3f42e9756096c
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354304"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a><span data-ttu-id="79a2d-103">Gérer les stratégies de routage d’appel d’urgence pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="79a2d-103">Manage emergency call routing policies for Direct Routing</span></span>

<span data-ttu-id="79a2d-104">Si vous avez [](direct-routing-landing-page.md) déployé Système téléphonique Routage direct dans votre organisation, vous pouvez utiliser les stratégies de routage des appels d’urgence dans Microsoft Teams pour configurer les numéros d’urgence et spécifier le routage des appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="79a2d-105">Une stratégie de routage d’appel d’urgence détermine si les services d’urgence améliorés sont activés pour les utilisateurs à qui la stratégie est affectée, les numéros utilisés pour appeler les services d’urgence (par exemple, le 112 en France) et la manière dont les appels vers les services d’urgence sont acheminés.</span><span class="sxs-lookup"><span data-stu-id="79a2d-105">An emergency call routing policy determines whether enhanced emergency services are enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="79a2d-106">Pour gérer les stratégies de routage d’appel d’urgence, vous devez vous rendre sur Voice Emergency center Microsoft Teams centre d’administration ou à l’aide  >   de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79a2d-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="79a2d-107">Les stratégies peuvent être affectées à des utilisateurs et [à des sites réseau.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="79a2d-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="79a2d-108">Pour les utilisateurs, vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="79a2d-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="79a2d-109">Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="79a2d-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="79a2d-110">N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas le renommer ou le supprimer.</span><span class="sxs-lookup"><span data-stu-id="79a2d-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="79a2d-111">Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="79a2d-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="79a2d-112">Si vous avez affecté une stratégie de routage des appels d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace la stratégie qui lui est affectée.</span><span class="sxs-lookup"><span data-stu-id="79a2d-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="79a2d-113">Créer une stratégie de routage d’appel d’urgence personnalisée</span><span class="sxs-lookup"><span data-stu-id="79a2d-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="79a2d-114">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79a2d-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="79a2d-115">Dans le panneau de navigation de gauche Microsoft Teams d’administration, allez dans Stratégies d’urgence vocale, puis cliquez sur l’onglet Stratégies  >   **de routage des** appels.</span><span class="sxs-lookup"><span data-stu-id="79a2d-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="79a2d-116">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="79a2d-116">Click **Add**.</span></span>
3. <span data-ttu-id="79a2d-117">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="79a2d-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="79a2d-118">Pour activer les appels d’urgence dynamiques, activez **l’appel d’urgence dynamique.**</span><span class="sxs-lookup"><span data-stu-id="79a2d-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="79a2d-119">Lorsque les appels d’urgence dynamiques sont activés, Teams récupère les informations de stratégie et d’emplacement du service et les inclut dans le cadre de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="79a2d-120">Définissez un ou plusieurs numéros d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="79a2d-121">Pour ce faire, sous **Numéros d’urgence,** cliquez **sur** Ajouter, puis :</span><span class="sxs-lookup"><span data-stu-id="79a2d-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="79a2d-122">**Chaîne de numérotation d’urgence**: Entrer la chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="79a2d-123">Cette chaîne de numérotation indique qu’un appel est un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="79a2d-124">Pour le routage direct, nous nous écartons des clients Teams qui envoient des appels d’urgence par un « + » devant la chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="79a2d-125">Tant que la transition n’est pas terminée, le modèle d’itinéraire vocal qui correspond à une chaîne de numérotation d’urgence doit veiller à ce qu’une correspondance soit effectuée pour les chaînes qui ont et ne sont pas précédées d’un « + », comme le 911 et le +911.</span><span class="sxs-lookup"><span data-stu-id="79a2d-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="79a2d-126">Par exemple, ^ \\ +?911 ou .\*.</span><span class="sxs-lookup"><span data-stu-id="79a2d-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="79a2d-127">**Masque de numérotation** d’urgence : pour chaque numéro d’urgence, vous pouvez spécifier un ou plusieurs masques de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="79a2d-128">Un masque de numérotation est le numéro que vous voulez traduire en valeur de la chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="79a2d-129">Cela permet d’appeler d’autres numéros d’urgence tout en permettant d’appeler les services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="79a2d-130">Par exemple, vous ajoutez le chiffre 112 comme masque de numérotation d’urgence, qui est le numéro de service d’urgence pour la plupart de l’Europe, et le 911 comme chaîne de numérotation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="79a2d-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="79a2d-131">Un utilisateur Teams d’Europe en visite peut ne pas savoir que le 911 est le numéro d’urgence aux États-Unis et, quand il compose le 112, composez le 111.</span><span class="sxs-lookup"><span data-stu-id="79a2d-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="79a2d-132">Pour définir plusieurs masques de numérotation, séparez les valeurs par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="79a2d-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="79a2d-133">Par exemple, 112;212.</span><span class="sxs-lookup"><span data-stu-id="79a2d-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="79a2d-134">**Enregistrement d’utilisation PSTN**: sélectionnez l’enregistrement d’utilisation de réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="79a2d-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="79a2d-135">L’enregistrement d’utilisation PSTN permet de déterminer l’itinéraire utilisé pour router les appels d’urgence des utilisateurs autorisés à les utiliser.</span><span class="sxs-lookup"><span data-stu-id="79a2d-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="79a2d-136">L’itinéraire associé à cette utilisation doit pointer vers une ligne SIP (Session Initiation Protocol) dédiée aux appels d’urgence ou à une passerelle ELIN (Emergency Location Identification Number) qui route les appels d’urgence vers le point de réponse de sécurité publique (PUBLIC Safety Answering Point) le plus proche.</span><span class="sxs-lookup"><span data-stu-id="79a2d-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="79a2d-137">Les chaînes de numérotation et masques de numérotation doivent être uniques dans une stratégie.</span><span class="sxs-lookup"><span data-stu-id="79a2d-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="79a2d-138">Cela signifie que pour une stratégie, vous pouvez définir plusieurs numéros d’urgence et définir plusieurs masques de numérotation pour une chaîne de numérotation, mais chaque chaîne de numérotation et masque de numérotation ne doivent être utilisés qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="79a2d-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="79a2d-139">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="79a2d-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="79a2d-140">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="79a2d-140">Using PowerShell</span></span>

<span data-ttu-id="79a2d-141">Voir [New-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="79a2d-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="79a2d-142">Modifier une stratégie de routage d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="79a2d-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="79a2d-143">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79a2d-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="79a2d-144">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="79a2d-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="79a2d-145">Dans le panneau de navigation de gauche Microsoft Teams d’administration, allez dans Stratégies d’urgence vocale, puis cliquez sur l’onglet Stratégies  >   **de routage des** appels.</span><span class="sxs-lookup"><span data-stu-id="79a2d-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="79a2d-146">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="79a2d-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="79a2d-147">A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="79a2d-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="79a2d-148">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="79a2d-148">Using PowerShell</span></span>

<span data-ttu-id="79a2d-149">Voir [Set-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="79a2d-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="79a2d-150">Affecter une stratégie personnalisée de routage des appels d’urgence aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="79a2d-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="79a2d-151">Voir également [Grant-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="79a2d-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="79a2d-152">Affecter une stratégie de routage d’appel d’urgence personnalisée à un site réseau</span><span class="sxs-lookup"><span data-stu-id="79a2d-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="79a2d-153">Utilisez la cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) pour affecter une stratégie de routage des appels d’urgence à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="79a2d-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="79a2d-154">Cet exemple montre comment affecter une stratégie appelée Stratégie de routage des appels d’urgence 1 sur le site Site1.</span><span class="sxs-lookup"><span data-stu-id="79a2d-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="79a2d-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79a2d-155">Related topics</span></span>

[<span data-ttu-id="79a2d-156">Gérer les stratégies d’appel d’urgence Teams</span><span class="sxs-lookup"><span data-stu-id="79a2d-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="79a2d-157">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="79a2d-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="79a2d-158">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="79a2d-158">Assign policies to your users in Teams</span></span>](assign-policies.md)