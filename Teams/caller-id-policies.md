---
title: Gérer les stratégies d’identification d’appelant dans Microsoft teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
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
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft teams pour modifier ou bloquer l’ID d’appelant des utilisateurs de teams au sein de votre organisation.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255527"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="fda99-103">Gérer les stratégies d’identification d’appelant dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="fda99-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="fda99-104">En tant qu’administrateur, vous pouvez utiliser les stratégies d’identification d’appelant dans Microsoft teams pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel).</span><span class="sxs-lookup"><span data-stu-id="fda99-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="fda99-105">Par défaut, le nombre de numéros de téléphone des utilisateurs de teams est visible lors d’un appel vers un téléphone RTC et le numéro de téléphone des appelants PSTN peut être affiché lorsqu’ils appellent un utilisateur de teams.</span><span class="sxs-lookup"><span data-stu-id="fda99-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="fda99-106">Vous pouvez utiliser les stratégies d’identification de l’appelant pour afficher un autre numéro de téléphone pour les utilisateurs teams de votre organisation ou bloquer l’affichage d’un numéro entrant.</span><span class="sxs-lookup"><span data-stu-id="fda99-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="fda99-107">Par exemple, lorsque les utilisateurs effectuent un appel, vous pouvez modifier l’identification de l’appelant pour afficher le numéro de téléphone principal de votre organisation à la place des numéros de téléphone des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fda99-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="fda99-108">Vous gérez les stratégies d’identification de l' **Voice**appelant en accédant à  >  **stratégies d’identification** de l’appelant vocal dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fda99-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="fda99-109">Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="fda99-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="fda99-110">Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="fda99-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="fda99-111">Créer une stratégie d’ID d’appelant personnalisée</span><span class="sxs-lookup"><span data-stu-id="fda99-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="fda99-112">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à stratégies d’identification de l'  >  **appelant**vocal.</span><span class="sxs-lookup"><span data-stu-id="fda99-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="fda99-113">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fda99-113">Click **Add**.</span></span> <br>
<span data-ttu-id="fda99-114">![Capture d’écran de la nouvelle page de stratégie d’ID d’appelant dans le centre d’administration](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="fda99-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="fda99-115">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="fda99-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="fda99-116">À partir de cet emplacement, sélectionnez les paramètres de votre choix :</span><span class="sxs-lookup"><span data-stu-id="fda99-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="fda99-117">**Bloquer l’ID d’appelant entrant**: activez ce paramètre pour bloquer l’identification de l’appelant lors de l’affichage d’appels entrants.</span><span class="sxs-lookup"><span data-stu-id="fda99-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="fda99-118">**Remplacer la stratégie d’ID d’appelant**: activez ce paramètre pour permettre aux utilisateurs de remplacer les paramètres de la stratégie concernant l’affichage de leur numéro pour les appelants.</span><span class="sxs-lookup"><span data-stu-id="fda99-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="fda99-119">Cela signifie que les utilisateurs peuvent décider d’afficher leur ID d’appelant.</span><span class="sxs-lookup"><span data-stu-id="fda99-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="fda99-120">Pour plus d’informations, reportez-vous à [contrôle de l’ID d’appelant sortant par l’utilisateur final](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="fda99-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="fda99-121">**Remplacez l’identification de l’appelant**par : définissez l’ID d’appelant à afficher pour les utilisateurs en sélectionnant l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="fda99-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="fda99-122">**Numéro de**l’utilisateur : affiche le numéro de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fda99-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="fda99-123">**Numéro de service**: vous permet de définir un numéro de téléphone de service à afficher en tant qu’identifiant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="fda99-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="fda99-124">**Anonyme**: affiche l’ID de l’appelant comme anonyme.</span><span class="sxs-lookup"><span data-stu-id="fda99-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="fda99-125">**Remplacez l’identification de l’appelant par ce numéro de service**: sélectionnez un numéro de service pour remplacer l’identifiant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="fda99-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="fda99-126">Cette option n’est disponible que si vous avez sélectionné **numéro de service** dans **remplacer l’identifiant de l’appelant par**.</span><span class="sxs-lookup"><span data-stu-id="fda99-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="fda99-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fda99-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="fda99-128">Modifier une stratégie d’ID d’appelant</span><span class="sxs-lookup"><span data-stu-id="fda99-128">Edit a caller ID policy</span></span>

<span data-ttu-id="fda99-129">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="fda99-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="fda99-130">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à stratégies d’identification de l'  >  **appelant**vocal.</span><span class="sxs-lookup"><span data-stu-id="fda99-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="fda99-131">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="fda99-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="fda99-132">Modifiez les paramètres souhaités, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fda99-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="fda99-133">Attribuer une stratégie d’ID d’appelant personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fda99-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="fda99-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fda99-134">Related topics</span></span>

[<span data-ttu-id="fda99-135">Nouveau-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="fda99-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="fda99-136">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="fda99-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
