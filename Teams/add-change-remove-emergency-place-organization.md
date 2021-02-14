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
description: Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le Centre d’administration Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806274"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="74cc5-103">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="74cc5-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="74cc5-104">Selon le nombre d’emplacements physiques existant dans votre organisation, vous pouvez ajouter des bâtiments, des étages et des bureaux pour créer un emplacement d’urgence plus spécifique.</span><span class="sxs-lookup"><span data-stu-id="74cc5-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="74cc5-105">Pour plus [d’informations, voir](what-are-emergency-locations-addresses-and-call-routing.md) Gérer les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="74cc5-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="74cc5-106">Pour savoir comment obtenir un plan d’appels et connaître son prix, consultez la gestion des [licences de module supplémentaire Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="74cc5-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="74cc5-107">Vous gérez les emplacements d’urgence pour votre organisation dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74cc5-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="74cc5-108">Ajout d’un emplacement à un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="74cc5-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="74cc5-109">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74cc5-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="74cc5-110">Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur  >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="74cc5-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="74cc5-111">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez ajouter un lieu.</span><span class="sxs-lookup"><span data-stu-id="74cc5-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="74cc5-112">Sous **l’onglet** Lieux, cliquez **sur Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="74cc5-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="74cc5-113">Entrez un nom d’lieu, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="74cc5-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="74cc5-114">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="74cc5-114">Using PowerShell</span></span>

<span data-ttu-id="74cc5-115">Voir [New-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="74cc5-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="74cc5-116">Modification d’un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="74cc5-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="74cc5-117">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74cc5-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="74cc5-118">Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur  >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="74cc5-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="74cc5-119">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez modifier un emplacement.</span><span class="sxs-lookup"><span data-stu-id="74cc5-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="74cc5-120">Sous **l’onglet** Espaces, sélectionnez l’endroit que vous voulez modifier, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="74cc5-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="74cc5-121">Mettez à jour les informations sur l’endroit, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="74cc5-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="74cc5-122">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="74cc5-122">Using PowerShell</span></span>

<span data-ttu-id="74cc5-123">Voir [Set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="74cc5-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="74cc5-124">Supprimer un emplacement d’un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="74cc5-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="74cc5-125">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74cc5-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="74cc5-126">Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur  >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="74cc5-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="74cc5-127">Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez supprimer un lieu.</span><span class="sxs-lookup"><span data-stu-id="74cc5-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="74cc5-128">Sous **l’onglet** Espaces, sélectionnez l’endroit que vous voulez supprimer, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="74cc5-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="74cc5-129">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="74cc5-129">Using PowerShell</span></span>

<span data-ttu-id="74cc5-130">Voir [Remove-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="74cc5-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="74cc5-131">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="74cc5-131">Related topics</span></span>

- [<span data-ttu-id="74cc5-132">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="74cc5-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="74cc5-133">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="74cc5-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="74cc5-134">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="74cc5-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
