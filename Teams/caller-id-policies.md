---
title: Gérer les stratégies d’ID d’appelant dans Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
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
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft Teams modifier ou bloquer l’ID d’appelant des Teams utilisateurs dans votre organisation.
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308373"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="84e75-103">Gérer les stratégies d’ID d’appelant dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84e75-103">Manage caller ID policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="84e75-104">Pour définir l’ID d’appelant sur un numéro de téléphone de compte de ressource et définir le nom de l’appelant, utilisez les cmdlets PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity dans le module Teams PowerShell 2.3.1 ou une ultérieure.</span><span class="sxs-lookup"><span data-stu-id="84e75-104">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="84e75-105">(Ces options ne sont actuellement pas disponibles dans le Microsoft Teams d’administration.)</span><span class="sxs-lookup"><span data-stu-id="84e75-105">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="84e75-106">Par défaut, lorsqu’Teams un utilisateur appelle un téléphone PSTN, le numéro de téléphone de l’Teams est visible.</span><span class="sxs-lookup"><span data-stu-id="84e75-106">By default, when a Teams user makes a call to a PSTN phone, the phone number of the Teams user is visible.</span></span> <span data-ttu-id="84e75-107">De même, lorsqu’un appelant PSTN appelle un Teams, le numéro de téléphone de l’appelant PSTN est visible.</span><span class="sxs-lookup"><span data-stu-id="84e75-107">Likewise, when a PSTN caller makes a call to a Teams user, the PSTN caller's phone number is visible.</span></span>

<span data-ttu-id="84e75-108">En tant qu’administrateur, vous pouvez utiliser les stratégies d’ID d’appelant pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel).</span><span class="sxs-lookup"><span data-stu-id="84e75-108">As an administrator, you can use caller ID policies to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="84e75-109">Vous pouvez utiliser les stratégies d’ID d’appelant pour afficher un autre numéro de téléphone pour les utilisateurs Teams de votre organisation, bloquer l’affichage du numéro de téléphone sortant, bloquer l’affichage d’un numéro entrant ou définir le nom de l’appelant (CNAM).</span><span class="sxs-lookup"><span data-stu-id="84e75-109">You can use caller ID policies to display an alternate phone number for Teams users in your organization, block the outbound phone number, block an incoming number from being displayed, or set the Calling Party Name (CNAM).</span></span> <span data-ttu-id="84e75-110">Par exemple, lorsqu’un utilisateur passe un appel, vous pouvez modifier l’ID de l’appelant pour afficher le numéro de téléphone principal et le nom de la société de votre organisation à la place du numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84e75-110">For example, when a user makes a call, you can change the caller ID to display your organization's main phone number and company name instead of the user's phone number.</span></span>

<span data-ttu-id="84e75-111">Pour gérer les stratégies d’ID d’appelant, vous devez vous rendre sur les stratégies d’ID d’appelant vocal dans le   >   Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="84e75-111">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="84e75-112">Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="84e75-112">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="84e75-113">Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="84e75-113">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="84e75-114">Créer une stratégie d’ID d’appelant personnalisée</span><span class="sxs-lookup"><span data-stu-id="84e75-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="84e75-115">Dans le navigation gauche du centre Microsoft Teams d’administration, allez **aux** stratégies  >  **d’ID d’appelant vocal.**</span><span class="sxs-lookup"><span data-stu-id="84e75-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="84e75-116">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="84e75-116">Click **Add**.</span></span> <br>
<span data-ttu-id="84e75-117">![Capture d’écran de la page de stratégie d’ID d’appelant dans le Centre d’administration](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="84e75-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="84e75-118">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="84e75-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="84e75-119">À partir de là, choisissez les paramètres de votre choix :</span><span class="sxs-lookup"><span data-stu-id="84e75-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="84e75-120">**Bloquer l’ID d’appelant** entrant : activer ce paramètre pour empêcher l’affichage de l’ID d’appelant des appels entrants.</span><span class="sxs-lookup"><span data-stu-id="84e75-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="84e75-121">Remplacer la stratégie **d’ID** d’appelant : activer ce paramètre pour que les utilisateurs remplacent les paramètres de la stratégie concernant l’affichage de leur numéro à des appelants ou non.</span><span class="sxs-lookup"><span data-stu-id="84e75-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="84e75-122">Cela signifie que les utilisateurs peuvent choisir d’afficher ou non leur ID d’appelant.</span><span class="sxs-lookup"><span data-stu-id="84e75-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="84e75-123">Pour plus d’informations, voir [Contrôle de l’ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)d’appelant sortant par l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="84e75-123">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="84e75-124">**Remplacez l’ID d’appelant** par : Définissez l’ID d’appelant à afficher pour les utilisateurs en sélectionnant l’une des sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="84e75-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="84e75-125">**Numéro de l’utilisateur**: affiche le numéro de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84e75-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="84e75-126">**Numéro de service**: vous permet de définir un numéro de téléphone de service à afficher en tant qu’ID d’appelant.</span><span class="sxs-lookup"><span data-stu-id="84e75-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="84e75-127">**Anonyme**: affiche l’ID de l’appelant comme anonyme.</span><span class="sxs-lookup"><span data-stu-id="84e75-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="84e75-128">**Remplacez l’ID d’appelant par ce numéro de service**: sélectionnez un numéro de service pour remplacer l’ID d’appelant des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="84e75-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="84e75-129">Cette option est disponible si vous avez sélectionné le numéro **de service** dans **Remplacer l’ID d’appelant par**.</span><span class="sxs-lookup"><span data-stu-id="84e75-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="84e75-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="84e75-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="84e75-131">Modifier une stratégie d’ID d’appelant</span><span class="sxs-lookup"><span data-stu-id="84e75-131">Edit a caller ID policy</span></span>

<span data-ttu-id="84e75-132">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="84e75-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="84e75-133">Dans le navigation gauche du centre Microsoft Teams d’administration, allez **aux** stratégies  >  **d’ID d’appelant vocal.**</span><span class="sxs-lookup"><span data-stu-id="84e75-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="84e75-134">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="84e75-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="84e75-135">Modifiez les paramètres de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="84e75-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="84e75-136">Affecter une stratégie d’ID d’appelant personnalisé aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="84e75-136">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="84e75-137">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="84e75-137">Related topics</span></span>

[<span data-ttu-id="84e75-138">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="84e75-138">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="84e75-139">Set-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="84e75-139">Set-CsCallingLineIdentity</span></span>](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="84e75-140">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="84e75-140">Assign policies to your users in Teams</span></span>](assign-policies.md)