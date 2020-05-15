---
title: Ajout, modification et suppression d’emplacements d’urgence
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
description: 'Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le centre d’administration Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 72730a326c6239b195d77f8a7bdde1b376da646f
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232485"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="45b8e-103">Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence</span><span class="sxs-lookup"><span data-stu-id="45b8e-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="45b8e-104">Un emplacement d’urgence doit être associé à un numéro de téléphone, mais lorsque cela se produit peut varier d’un pays à l’autre.</span><span class="sxs-lookup"><span data-stu-id="45b8e-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="45b8e-105">Par exemple, aux États-Unis, vous devez associer un emplacement d’urgence lorsque vous attribuez le numéro de téléphone à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="45b8e-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="45b8e-106">Au Royaume-Uni, vous devez associer un emplacement d’urgence au numéro de téléphone lorsque vous recevez les numéros de téléphone d’Office 365 ou que vous transférez des numéros de téléphone de votre fournisseur de services actuel.</span><span class="sxs-lookup"><span data-stu-id="45b8e-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="45b8e-107">Quel que soit le pays ou la région où vous vous trouvez, vous pouvez ajouter un lieu ou des lieux à un emplacement d’urgence et supprimer un emplacement d’urgence.</span><span class="sxs-lookup"><span data-stu-id="45b8e-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="45b8e-108">En fonction du nombre d’emplacements physiques au sein de votre organisation, vous pouvez créer des lieux pour les bâtiments, les étages et les bureaux.</span><span class="sxs-lookup"><span data-stu-id="45b8e-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="45b8e-109">Voir [gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="45b8e-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="45b8e-110">Pour plus d’informations sur la façon d’obtenir un plan d’appels et son coût, voir [licences de module complémentaire équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="45b8e-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="45b8e-111">Vous gérez les emplacements d’urgence de votre organisation dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45b8e-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="45b8e-112">Ajouter un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="45b8e-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="45b8e-113">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45b8e-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="45b8e-114">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="45b8e-115">Cliquez sur **Ajouter un emplacement**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-115">Click **Add Location**.</span></span>
3. <span data-ttu-id="45b8e-116">Entrez un nom et une description pour l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="45b8e-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="45b8e-117">Sélectionnez le pays ou la région, puis entrez l’adresse.</span><span class="sxs-lookup"><span data-stu-id="45b8e-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="45b8e-118">En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre qu’il est nécessaire d’activer un numéro de téléphone dans Office 365, mais que l’adresse définie au lieu d’urgence, qui est utilisée pour acquérir le numéro, doit correspondre à l’indicatif de la région du numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="45b8e-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>
5. <span data-ttu-id="45b8e-119">Si l’adresse est introuvable et que vous voulez modifier manuellement l’adresse, activez la case à cobesoin **modifier le formulaire d’adresse manuellement si vous ne trouvez pas l’adresse**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-119">If the address isn't found and you want to manually edit the address, turn on **Let me edit the address form manually if the address selected can't be found**.</span></span>
6. <span data-ttu-id="45b8e-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="45b8e-121">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="45b8e-121">Using PowerShell</span></span>

<span data-ttu-id="45b8e-122">Voir [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="45b8e-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="45b8e-123">Modification d'un emplacement d'urgence</span><span class="sxs-lookup"><span data-stu-id="45b8e-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="45b8e-124">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45b8e-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="45b8e-125">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="45b8e-126">Dans la liste, sélectionnez l’emplacement que vous voulez modifier, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="45b8e-127">Apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="45b8e-127">Make the changes you want.</span></span>
4. <span data-ttu-id="45b8e-128">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="45b8e-129">Vous pouvez modifier les informations d’adresse d’un emplacement uniquement si l’adresse n’est pas validée.</span><span class="sxs-lookup"><span data-stu-id="45b8e-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="45b8e-130">Si l’adresse est déjà validée et que vous devez modifier l’adresse, supprimez l’emplacement, puis créez un nouvel emplacement avec l’adresse correcte.</span><span class="sxs-lookup"><span data-stu-id="45b8e-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="45b8e-131">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="45b8e-131">Using PowerShell</span></span>

<span data-ttu-id="45b8e-132">Voir [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="45b8e-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="45b8e-133">Supprimer un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="45b8e-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="45b8e-134">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45b8e-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="45b8e-135">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="45b8e-136">Dans la liste, sélectionnez l’emplacement que vous voulez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="45b8e-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="45b8e-137">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="45b8e-137">Using PowerShell</span></span>

<span data-ttu-id="45b8e-138">Voir [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="45b8e-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="45b8e-139">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="45b8e-139">Related topics</span></span>

- [<span data-ttu-id="45b8e-140">Gérer les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="45b8e-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="45b8e-141">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="45b8e-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="45b8e-142">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="45b8e-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="45b8e-143">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="45b8e-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
