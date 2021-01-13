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
description: 'Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le Centre d’administration Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799944"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="b27aa-103">Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence</span><span class="sxs-lookup"><span data-stu-id="b27aa-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="b27aa-104">Un emplacement d’urgence doit être associé à un numéro de téléphone, mais lorsque cela se produit, cette situation peut varier d’un pays ou d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="b27aa-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="b27aa-105">Par exemple, aux États-Unis, vous devez associer un emplacement d’urgence lorsque vous attribuez le numéro de téléphone à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b27aa-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="b27aa-106">Au Royaume-Uni, vous devez associer un emplacement d’urgence au numéro de téléphone lorsque vous obtenez les numéros de téléphone de Microsoft 365 ou Office 365, ou transférez des numéros de téléphone à partir de votre fournisseur de services actuel.</span><span class="sxs-lookup"><span data-stu-id="b27aa-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="b27aa-107">Quel que soit le pays ou la région dans lesquels vous vous trouvez, vous pouvez ajouter un ou plusieurs emplacements à un emplacement d’urgence et supprimer un emplacement d’urgence.</span><span class="sxs-lookup"><span data-stu-id="b27aa-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="b27aa-108">Selon le nombre d’emplacements physiques existant dans votre organisation, vous pouvez créer des bâtiments, des étages et des bureaux.</span><span class="sxs-lookup"><span data-stu-id="b27aa-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="b27aa-109">Voir [Gérer les appels d’urgence.](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="b27aa-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="b27aa-110">Pour savoir comment obtenir un plan d’appels et connaître son prix, consultez la gestion des [licences de module supplémentaire Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="b27aa-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="b27aa-111">Vous gérez les emplacements d’urgence pour votre organisation dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b27aa-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="b27aa-112">Ajouter un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="b27aa-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b27aa-113">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b27aa-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b27aa-114">Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur  >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="b27aa-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b27aa-115">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b27aa-115">Click **Add**.</span></span>
3. <span data-ttu-id="b27aa-116">Entrez un nom et une description pour l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="b27aa-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="b27aa-117">Sélectionnez le pays ou la région, puis entrez l’adresse.</span><span class="sxs-lookup"><span data-stu-id="b27aa-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b27aa-118">En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre que, pour activer avec succès un numéro de téléphone dans Microsoft 365 ou Office 365, l’adresse définie dans l’emplacement d’urgence, qui est utilisé pour acquérir le numéro, doit correspondre à l’code de la zone du numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="b27aa-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="b27aa-119">Si l’adresse est in trouvée et que vous voulez la modifier manuellement, activer la modification **manuelle de l’adresse.**</span><span class="sxs-lookup"><span data-stu-id="b27aa-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="b27aa-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b27aa-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b27aa-121">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="b27aa-121">Using PowerShell</span></span>

<span data-ttu-id="b27aa-122">Voir [New-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="b27aa-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="b27aa-123">Modification d'un emplacement d'urgence</span><span class="sxs-lookup"><span data-stu-id="b27aa-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b27aa-124">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b27aa-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b27aa-125">Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur  >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="b27aa-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b27aa-126">Dans la liste, sélectionnez l’emplacement à modifier, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="b27aa-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="b27aa-127">A apporter les modifications de votre souhaitez.</span><span class="sxs-lookup"><span data-stu-id="b27aa-127">Make the changes you want.</span></span>
4. <span data-ttu-id="b27aa-128">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b27aa-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b27aa-129">Vous ne pouvez modifier les informations d’adresse d’un emplacement que si l’adresse n’est pas validée.</span><span class="sxs-lookup"><span data-stu-id="b27aa-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="b27aa-130">Si l’adresse est déjà validée et que vous devez la modifier, supprimez l’emplacement, puis créez un nouvel emplacement avec l’adresse correcte.</span><span class="sxs-lookup"><span data-stu-id="b27aa-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b27aa-131">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="b27aa-131">Using PowerShell</span></span>

<span data-ttu-id="b27aa-132">Voir [Set-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="b27aa-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="b27aa-133">Supprimer un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="b27aa-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b27aa-134">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b27aa-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b27aa-135">Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur  >  **Adresses d’urgence d’emplacements.**</span><span class="sxs-lookup"><span data-stu-id="b27aa-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b27aa-136">Dans la liste, sélectionnez l’emplacement à supprimer, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="b27aa-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b27aa-137">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="b27aa-137">Using PowerShell</span></span>

<span data-ttu-id="b27aa-138">Voir [Remove-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="b27aa-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b27aa-139">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="b27aa-139">Related topics</span></span>

- [<span data-ttu-id="b27aa-140">Gérer les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="b27aa-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="b27aa-141">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="b27aa-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="b27aa-142">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="b27aa-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="b27aa-143">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="b27aa-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
