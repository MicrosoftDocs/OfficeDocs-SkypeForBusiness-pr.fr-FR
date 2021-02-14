---
title: Gérer les stratégies de routage vocal dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
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
description: Découvrez comment créer et gérer des stratégies de routage vocal dans Microsoft Teams.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802554"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="6a13b-103">Gérer les stratégies de routage vocal dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a13b-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="6a13b-104">Si vous avez [](direct-routing-landing-page.md) déployé le routage direct du système téléphonique dans votre organisation, vous utilisez les stratégies de routage vocal pour permettre aux utilisateurs de Teams et de Skype Entreprise Online de recevoir et de passer des appels téléphoniques vers le réseau téléphonique commuté (PSTN) à l’aide de votre infrastructure téléphonique locale.</span><span class="sxs-lookup"><span data-stu-id="6a13b-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="6a13b-105">Une stratégie de routage vocal est un conteneur pour les enregistrements d’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="6a13b-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="6a13b-106">Pour créer et gérer des stratégies de routage voix, vous devez vous rendre sur les stratégies de routage de voix dans le Centre d’administration de Microsoft Teams ou à l’aide  >   de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a13b-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="6a13b-107">Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="6a13b-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="6a13b-108">Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="6a13b-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="6a13b-109">N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas le renommer ou le supprimer.</span><span class="sxs-lookup"><span data-stu-id="6a13b-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="6a13b-110">Il est important de savoir que l’affectation d’une stratégie de routage vocal à un utilisateur ne l’autorise pas à effectuer des appels PSTN dans Teams.</span><span class="sxs-lookup"><span data-stu-id="6a13b-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="6a13b-111">Vous devrez également activer le routage direct de l’utilisateur pour Phone System et effectuer d’autres étapes de configuration.</span><span class="sxs-lookup"><span data-stu-id="6a13b-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="6a13b-112">Pour plus d’informations, [voir Configurer le routage direct.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="6a13b-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="6a13b-113">Créer une stratégie de routage vocal personnalisée</span><span class="sxs-lookup"><span data-stu-id="6a13b-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6a13b-114">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a13b-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6a13b-115">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez sur Stratégies de routage de **Voice**  >  **Voice,** puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="6a13b-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="6a13b-116">![Capture d’écran de la page Ajouter une stratégie de routage vocal dans le Centre d’administration Microsoft Teams ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="6a13b-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="6a13b-117">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="6a13b-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="6a13b-118">Sous **Enregistrements d’utilisation PSTN,** cliquez sur Ajouter une utilisation **PSTN,** puis sélectionnez les enregistrements à ajouter.</span><span class="sxs-lookup"><span data-stu-id="6a13b-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="6a13b-119">Si vous avez besoin de créer un enregistrement d’utilisation PSTN, cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="6a13b-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="6a13b-120">Si vous avez ajouté plusieurs enregistrements d’utilisation PSTN, organisez-les dans l’ordre de votre choix.</span><span class="sxs-lookup"><span data-stu-id="6a13b-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="6a13b-121">Lorsque vous avez terminé, cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="6a13b-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="6a13b-122">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a13b-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6a13b-123">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a13b-123">Using PowerShell</span></span>

<span data-ttu-id="6a13b-124">Voir [New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="6a13b-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="6a13b-125">Modifier une stratégie de routage vocal</span><span class="sxs-lookup"><span data-stu-id="6a13b-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6a13b-126">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a13b-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6a13b-127">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="6a13b-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="6a13b-128">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez aux stratégies de routage de **Voice**  >  **Voice.**</span><span class="sxs-lookup"><span data-stu-id="6a13b-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="6a13b-129">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6a13b-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6a13b-130">Cliquez **sur Ajouter/supprimer des enregistrements d’utilisation PSTN,** a apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="6a13b-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6a13b-131">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a13b-131">Using PowerShell</span></span>

<span data-ttu-id="6a13b-132">Voir [Set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="6a13b-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="6a13b-133">Affecter une stratégie de routage vocal personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6a13b-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="6a13b-134">Voir également [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="6a13b-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a13b-135">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="6a13b-135">Related topics</span></span>

[<span data-ttu-id="6a13b-136">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a13b-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="6a13b-137">Configurer le routage vocal pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="6a13b-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="6a13b-138">Activer le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="6a13b-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="6a13b-139">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6a13b-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
