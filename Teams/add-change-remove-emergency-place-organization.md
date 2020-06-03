---
title: Ajout, modification et suppression de lieux pour les emplacements d’urgence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le centre d’administration Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539431"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="0c9d2-103">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="0c9d2-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="0c9d2-104">En fonction du nombre d’emplacements physiques au sein de votre organisation, vous pouvez ajouter des emplacements pour les bâtiments, planchers et bureaux pour créer un emplacement d’urgence plus précis.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="0c9d2-105">Pour plus d’informations, voir [gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md) .</span><span class="sxs-lookup"><span data-stu-id="0c9d2-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="0c9d2-106">Pour plus d’informations sur la façon d’obtenir un plan d’appels et son coût, voir [licences de module complémentaire équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0c9d2-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="0c9d2-107">Vous gérez les emplacements d’urgence de votre organisation dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="0c9d2-108">Ajouter un emplacement à un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="0c9d2-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0c9d2-109">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c9d2-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0c9d2-110">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="0c9d2-111">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez ajouter un emplacement.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="0c9d2-112">Dans l’onglet **emplacements** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="0c9d2-113">Entrez un nom de lieu, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0c9d2-114">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c9d2-114">Using PowerShell</span></span>

<span data-ttu-id="0c9d2-115">Voir [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="0c9d2-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="0c9d2-116">Modification d’un emplacement pour un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="0c9d2-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0c9d2-117">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c9d2-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0c9d2-118">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="0c9d2-119">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez modifier un emplacement.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="0c9d2-120">Dans l’onglet **emplacements** , sélectionnez l’emplacement que vous voulez modifier, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="0c9d2-121">Mettez à jour les informations de lieu, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0c9d2-122">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c9d2-122">Using PowerShell</span></span>

<span data-ttu-id="0c9d2-123">Voir [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="0c9d2-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="0c9d2-124">Supprimer un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="0c9d2-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0c9d2-125">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c9d2-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0c9d2-126">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="0c9d2-127">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez supprimer un emplacement.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="0c9d2-128">Dans l’onglet **emplacements** , sélectionnez l’emplacement que vous voulez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0c9d2-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0c9d2-129">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c9d2-129">Using PowerShell</span></span>

<span data-ttu-id="0c9d2-130">Voir [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="0c9d2-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0c9d2-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c9d2-131">Related topics</span></span>

- [<span data-ttu-id="0c9d2-132">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="0c9d2-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="0c9d2-133">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="0c9d2-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="0c9d2-134">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="0c9d2-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
