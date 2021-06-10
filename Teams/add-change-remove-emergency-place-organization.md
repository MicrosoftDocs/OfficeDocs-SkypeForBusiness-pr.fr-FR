---
title: Ajout, modification, suppression d’emplacements d’urgence
author: cichur
ms.author: v-cichur
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
description: Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le Microsoft Teams d’administration.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121502"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="9e2e9-103">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="9e2e9-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="9e2e9-104">Selon le nombre d’emplacements physiques existant dans votre organisation, vous pouvez ajouter des bâtiments, des étages et des bureaux pour créer un emplacement d’urgence plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="9e2e9-105">Pour plus [d’informations, voir](what-are-emergency-locations-addresses-and-call-routing.md) Gérer les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="9e2e9-106">Pour savoir comment obtenir un forfait d’appels et connaître son prix, consultez Teams [licences de module supplémentaire.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="9e2e9-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="9e2e9-107">Vous gérez les emplacements d’urgence pour votre organisation dans le Microsoft Teams d’administration de l’entreprise ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="9e2e9-108">Ajout d’un emplacement à un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="9e2e9-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9e2e9-109">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e2e9-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9e2e9-110">Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="9e2e9-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="9e2e9-111">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez ajouter un lieu.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="9e2e9-112">Sous **l’onglet** Espaces, cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="9e2e9-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="9e2e9-113">Entrez un nom d’lieu, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="9e2e9-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9e2e9-114">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e2e9-114">Using PowerShell</span></span>

<span data-ttu-id="9e2e9-115">Voir [New-CsOnlineLisLocation.](/powershell/module/skype/new-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="9e2e9-115">See [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="9e2e9-116">Modification d’un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="9e2e9-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9e2e9-117">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e2e9-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9e2e9-118">Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="9e2e9-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="9e2e9-119">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez modifier un emplacement.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="9e2e9-120">Sous **l’onglet** Espaces, sélectionnez l’endroit que vous voulez modifier, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="9e2e9-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="9e2e9-121">Mettez à jour les informations sur l’endroit, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="9e2e9-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9e2e9-122">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e2e9-122">Using PowerShell</span></span>

<span data-ttu-id="9e2e9-123">Voir [Set-CsOnlineLisLocation.](/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="9e2e9-123">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="9e2e9-124">Supprimer un emplacement d’un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="9e2e9-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9e2e9-125">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e2e9-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9e2e9-126">Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="9e2e9-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="9e2e9-127">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez supprimer un lieu.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="9e2e9-128">Sous **l’onglet** Espaces, sélectionnez l’endroit que vous voulez supprimer, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="9e2e9-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9e2e9-129">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e2e9-129">Using PowerShell</span></span>

<span data-ttu-id="9e2e9-130">Voir [Remove-CsOnlineLisLocation.](/powershell/module/skype/remove-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="9e2e9-130">See [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9e2e9-131">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="9e2e9-131">Related topics</span></span>

- [<span data-ttu-id="9e2e9-132">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="9e2e9-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="9e2e9-133">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="9e2e9-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="9e2e9-134">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="9e2e9-134">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)