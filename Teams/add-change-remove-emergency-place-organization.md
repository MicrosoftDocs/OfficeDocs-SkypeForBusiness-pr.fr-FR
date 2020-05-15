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
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232495"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="5b7b0-103">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="5b7b0-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="5b7b0-104">En fonction du nombre d’emplacements physiques au sein de votre organisation, vous pouvez ajouter des emplacements pour les bâtiments, planchers et bureaux pour créer un emplacement d’urgence plus précis.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="5b7b0-105">Pour plus d’informations, voir [gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md) .</span><span class="sxs-lookup"><span data-stu-id="5b7b0-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="5b7b0-106">Pour plus d’informations sur la façon d’obtenir un plan d’appels et son coût, voir [licences de module complémentaire équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="5b7b0-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="5b7b0-107">Vous gérez les emplacements d’urgence de votre organisation dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="5b7b0-108">Ajouter un emplacement à un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="5b7b0-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="5b7b0-109">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b7b0-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="5b7b0-110">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="5b7b0-111">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez ajouter un emplacement.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="5b7b0-112">Dans l’onglet **emplacements** , cliquez sur **Ajouter un emplacement**.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-112">On the **Places** tab, click **Add place**.</span></span>
4. <span data-ttu-id="5b7b0-113">Entrez un nom de lieu, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5b7b0-114">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b7b0-114">Using PowerShell</span></span>

<span data-ttu-id="5b7b0-115">Voir [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="5b7b0-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="5b7b0-116">Modification d’un emplacement pour un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="5b7b0-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="5b7b0-117">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b7b0-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="5b7b0-118">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="5b7b0-119">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez modifier un emplacement.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="5b7b0-120">Dans l’onglet **emplacements** , sélectionnez l’emplacement que vous voulez modifier, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="5b7b0-121">Mettez à jour les informations de lieu, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5b7b0-122">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b7b0-122">Using PowerShell</span></span>

<span data-ttu-id="5b7b0-123">Voir [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="5b7b0-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="5b7b0-124">Supprimer un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="5b7b0-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="5b7b0-125">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b7b0-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="5b7b0-126">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="5b7b0-127">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez supprimer un emplacement.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="5b7b0-128">Dans l’onglet **emplacements** , sélectionnez l’emplacement que vous voulez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5b7b0-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5b7b0-129">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b7b0-129">Using PowerShell</span></span>

<span data-ttu-id="5b7b0-130">Voir [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="5b7b0-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5b7b0-131">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="5b7b0-131">Related topics</span></span>

- [<span data-ttu-id="5b7b0-132">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="5b7b0-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="5b7b0-133">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="5b7b0-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="5b7b0-134">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="5b7b0-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
