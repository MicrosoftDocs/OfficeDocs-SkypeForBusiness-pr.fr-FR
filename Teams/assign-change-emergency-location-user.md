---
title: Affecter ou modifier un emplacement d’urgence pour un utilisateur
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
description: Dans cet article, vous allez découvrir comment affecter ou modifier un emplacement d’urgence pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 450fe848052af1e331964da3d7b695daf0f1567a
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610993"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="31f45-103">Affecter ou modifier un emplacement d’urgence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="31f45-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="31f45-104">Lorsque vous configurez des plans d’appel, vous devez attribuer un emplacement d’urgence à chaque numéro de téléphone ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31f45-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="31f45-105">Dans les pays d’Europe, l’emplacement d’urgence est associé au numéro de téléphone lorsque vous l’obtenez de Microsoft 365 ou d’Office 365 ou lorsque vous transférez un numéro de téléphone vers Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="31f45-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="31f45-106">Aux États-Unis, l’emplacement d’urgence est associé au numéro de téléphone attribué à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31f45-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="31f45-107">L’adresse de secours peut être changée si l’utilisateur auquel elle est affectée se déplace vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="31f45-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="31f45-108">Pour en savoir plus sur les adresses de secours et les emplacements d’urgence, voir [que sont les emplacements d’urgence, les emplacements d’urgence et le routage des appels ?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="31f45-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="31f45-109">Pour plus d’informations sur la façon d’obtenir des offres d’appels et leur coût, voir [licences de complément d’équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="31f45-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="31f45-110">Vous pouvez attribuer ou modifier un emplacement d’urgence pour un utilisateur dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31f45-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="31f45-111">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31f45-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="31f45-112">Dans le volet de navigation de gauche du centre d’administration de **Voice**Microsoft Teams, cliquez sur  >  **numéros de téléphone**vocaux.</span><span class="sxs-lookup"><span data-stu-id="31f45-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="31f45-113">Dans la page **numéros de téléphone** , cliquez sur l’onglet **numéros** , sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="31f45-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="31f45-114">Dans le volet **édition** , sous **emplacement d’urgence**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="31f45-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="31f45-115">Pour attribuer un emplacement d’urgence, recherchez et sélectionnez un emplacement d’urgence.</span><span class="sxs-lookup"><span data-stu-id="31f45-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="31f45-116">Pour modifier l’emplacement d’urgence qui est déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement existant, puis recherchez et sélectionnez l’emplacement que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="31f45-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="31f45-117">Si vous souhaitez envoyer à l’utilisateur un message électronique contenant son numéro de téléphone, désactivez ou activez l’option **courrier électronique avec les informations**sur le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="31f45-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="31f45-118">Par défaut, ce paramètre est activé.</span><span class="sxs-lookup"><span data-stu-id="31f45-118">By default, this is on.</span></span>

5. <span data-ttu-id="31f45-119">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="31f45-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="31f45-120">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="31f45-120">Using PowerShell</span></span>

<span data-ttu-id="31f45-121">Voir [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="31f45-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="31f45-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="31f45-122">Related topics</span></span>

- [<span data-ttu-id="31f45-123">Gérer les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="31f45-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="31f45-124">Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="31f45-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="31f45-125">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="31f45-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="31f45-126">Affecter ou modifier un lieu pour un emplacement d’urgence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="31f45-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="31f45-127">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="31f45-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="31f45-128">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="31f45-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="31f45-129">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="31f45-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
