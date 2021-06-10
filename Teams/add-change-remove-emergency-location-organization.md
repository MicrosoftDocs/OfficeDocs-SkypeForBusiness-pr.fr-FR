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
description: 'Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le Microsoft Teams d’administration. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b918cbcbebf8edb2cd54d08e0e4a3177867fa623
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121522"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="ccc99-103">Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence</span><span class="sxs-lookup"><span data-stu-id="ccc99-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="ccc99-104">Un emplacement d’urgence doit être associé à un numéro de téléphone, mais lorsque cela se produit, cette situation peut varier d’un pays ou d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="ccc99-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="ccc99-105">Par exemple, aux États-Unis, vous devez associer un emplacement d’urgence lorsque vous attribuez le numéro de téléphone à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ccc99-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="ccc99-106">Au Royaume-Uni, vous devez associer un emplacement d’urgence au numéro de téléphone lorsque vous obtenez les numéros de téléphone à partir d’Microsoft 365 ou Office 365 ou transférez des numéros de téléphone à partir de votre fournisseur de services actuel.</span><span class="sxs-lookup"><span data-stu-id="ccc99-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="ccc99-107">Quel que soit le pays ou la région dans lesquels vous vous trouvez, vous pouvez ajouter un ou plusieurs emplacements à un emplacement d’urgence et supprimer un emplacement d’urgence.</span><span class="sxs-lookup"><span data-stu-id="ccc99-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="ccc99-108">Selon le nombre d’emplacements physiques existant dans votre organisation, vous pouvez créer des bâtiments, des étages et des bureaux.</span><span class="sxs-lookup"><span data-stu-id="ccc99-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="ccc99-109">Voir [Gérer les appels d’urgence.](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="ccc99-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="ccc99-110">Pour savoir comment obtenir un forfait d’appels et connaître son prix, consultez Teams [licences de module supplémentaire.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="ccc99-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="ccc99-111">Vous gérez les emplacements d’urgence pour votre organisation via le Microsoft Teams d’administration de l’entreprise ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccc99-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="ccc99-112">Ajouter un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="ccc99-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ccc99-113">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ccc99-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ccc99-114">Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="ccc99-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ccc99-115">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ccc99-115">Click **Add**.</span></span>
3. <span data-ttu-id="ccc99-116">Entrez un nom et une description pour l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="ccc99-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="ccc99-117">Sélectionnez le pays ou la région, puis entrez l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ccc99-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ccc99-118">En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre que, pour activer correctement un numéro de téléphone à Microsoft 365 ou Office 365, l’adresse définie dans l’emplacement d’urgence, qui est utilisé pour acquérir le numéro, doit correspondre à l’code de la zone du numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="ccc99-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="ccc99-119">Si l’adresse est in trouvée et que vous voulez la modifier manuellement, vous pouvez activer modifier l’adresse **manuellement.**</span><span class="sxs-lookup"><span data-stu-id="ccc99-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="ccc99-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ccc99-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ccc99-121">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccc99-121">Using PowerShell</span></span>

<span data-ttu-id="ccc99-122">Voir [New-CsOnlineLisCivicAddress.](/powershell/module/skype/new-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="ccc99-122">See [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="ccc99-123">Modification d'un emplacement d'urgence</span><span class="sxs-lookup"><span data-stu-id="ccc99-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ccc99-124">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ccc99-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ccc99-125">Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="ccc99-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ccc99-126">Dans la liste, sélectionnez l’emplacement à modifier, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="ccc99-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="ccc99-127">A apporter les modifications de votre souhaitez.</span><span class="sxs-lookup"><span data-stu-id="ccc99-127">Make the changes you want.</span></span>
4. <span data-ttu-id="ccc99-128">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ccc99-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ccc99-129">Vous ne pouvez modifier les informations d’adresse d’un emplacement que si l’adresse n’est pas validée.</span><span class="sxs-lookup"><span data-stu-id="ccc99-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="ccc99-130">Si l’adresse est déjà validée et que vous devez la modifier, supprimez l’emplacement, puis créez un nouvel emplacement avec l’adresse correcte.</span><span class="sxs-lookup"><span data-stu-id="ccc99-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ccc99-131">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccc99-131">Using PowerShell</span></span>

<span data-ttu-id="ccc99-132">Voir [Set-CsOnlineLisCivicAddress.](/powershell/module/skype/set-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="ccc99-132">See [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="ccc99-133">Supprimer un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="ccc99-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ccc99-134">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ccc99-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ccc99-135">Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="ccc99-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ccc99-136">Dans la liste, sélectionnez l’emplacement à supprimer, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="ccc99-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ccc99-137">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccc99-137">Using PowerShell</span></span>

<span data-ttu-id="ccc99-138">Voir [Remove-CsOnlineLisCivicAddress.](/powershell/module/skype/remove-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="ccc99-138">See [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccc99-139">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="ccc99-139">Related topics</span></span>

- [<span data-ttu-id="ccc99-140">Gérer les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="ccc99-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="ccc99-141">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="ccc99-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="ccc99-142">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="ccc99-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="ccc99-143">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="ccc99-143">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)