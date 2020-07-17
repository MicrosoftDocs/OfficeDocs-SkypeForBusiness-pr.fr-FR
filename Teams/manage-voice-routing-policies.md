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
ms.openlocfilehash: e3dc656043776d3a2f0e5b37a0c35ab98b7c03f7
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938125"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="0e635-103">Gérer les stratégies de routage de messagerie vocale dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="0e635-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="0e635-104">Si vous avez déployé le [routage direct du système téléphonique](direct-routing-landing-page.md) au sein de votre organisation, vous utilisez les stratégies de routage vocal pour permettre aux équipes et aux utilisateurs de Skype entreprise Online de recevoir et de passer des appels téléphoniques à l’aide du réseau téléphonique public commuté (RTC) à l’aide de votre infrastructure de téléphonie locale.</span><span class="sxs-lookup"><span data-stu-id="0e635-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="0e635-105">Une stratégie de routage vocale est un conteneur d’enregistrements d’utilisation RTC.</span><span class="sxs-lookup"><span data-stu-id="0e635-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="0e635-106">Pour créer et gérer des stratégies de routage de messagerie vocale, vous pouvez **accéder à**  >  **stratégies de routage vocal** dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e635-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="0e635-107">Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="0e635-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="0e635-108">Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0e635-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="0e635-109">Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer.</span><span class="sxs-lookup"><span data-stu-id="0e635-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="0e635-110">Il est important de savoir que l’affectation d’une stratégie de routage vocale à un utilisateur ne permet pas à un utilisateur de passer des appels RTC dans Teams.</span><span class="sxs-lookup"><span data-stu-id="0e635-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="0e635-111">Vous devez également activer l’utilisateur pour le routage direct du système téléphonique et effectuer d’autres étapes de configuration.</span><span class="sxs-lookup"><span data-stu-id="0e635-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="0e635-112">Pour en savoir plus, voir [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="0e635-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="0e635-113">Créer une stratégie de routage vocale personnalisée</span><span class="sxs-lookup"><span data-stu-id="0e635-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0e635-114">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e635-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0e635-115">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**stratégies de routage de voix vocales, puis  >  **Voice routing policies**cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0e635-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="0e635-116">![Capture d’écran de la page Ajouter une stratégie de routage vocale dans le centre d’administration Microsoft teams](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="0e635-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="0e635-117">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="0e635-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="0e635-118">Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, puis sélectionnez les enregistrements que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="0e635-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="0e635-119">Si vous avez besoin de créer un nouvel enregistrement d’utilisation RTC, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0e635-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="0e635-120">Si vous avez ajouté plusieurs enregistrements d’utilisation RTC, réorganisez-les dans l’ordre de votre choix.</span><span class="sxs-lookup"><span data-stu-id="0e635-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="0e635-121">Lorsque vous avez terminé, cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="0e635-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="0e635-122">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0e635-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0e635-123">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e635-123">Using PowerShell</span></span>

<span data-ttu-id="0e635-124">Voir [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="0e635-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="0e635-125">Modification d’une stratégie de routage téléphonique</span><span class="sxs-lookup"><span data-stu-id="0e635-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0e635-126">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e635-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="0e635-127">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="0e635-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="0e635-128">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de routage vocal**.</span><span class="sxs-lookup"><span data-stu-id="0e635-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="0e635-129">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="0e635-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0e635-130">Cliquez sur **Ajouter/supprimer des enregistrements d’utilisation RTC**, apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0e635-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0e635-131">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e635-131">Using PowerShell</span></span>

<span data-ttu-id="0e635-132">Voir [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="0e635-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="0e635-133">Assigner une stratégie de routage vocale personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0e635-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="0e635-134">Voir aussi [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="0e635-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0e635-135">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="0e635-135">Related topics</span></span>

[<span data-ttu-id="0e635-136">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e635-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="0e635-137">Configurer le routage de la voix pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="0e635-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="0e635-138">Activer le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="0e635-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="0e635-139">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="0e635-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
