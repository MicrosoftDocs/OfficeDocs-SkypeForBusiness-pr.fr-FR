---
title: Affecter ou modifier un emplacement d’urgence pour un utilisateur
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
description: Dans cet article, vous allez découvrir comment affecter ou modifier un emplacement d’urgence pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102980"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="c9246-103">Affecter ou modifier un emplacement d’urgence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9246-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="c9246-104">Lorsque vous planifiez des forfaits d’appels, vous devez affecter un emplacement d’urgence à chaque numéro de téléphone ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c9246-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="c9246-105">En Europe, l’emplacement d’urgence est associé au numéro de téléphone lorsque vous l’obtenez à partir de Microsoft 365 ou d’Office 365, ou lorsque vous transférez un numéro de téléphone vers Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9246-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c9246-106">Aux États-Unis, l’emplacement d’urgence est associé au numéro de téléphone lorsqu’il est affecté à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c9246-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="c9246-107">L’adresse de secours peut être modifiée si l’utilisateur à qui elle est affectée change d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c9246-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="c9246-108">Pour plus d’informations sur les adresses de secours et les emplacements d’urgence, voir Que sont les emplacements d’urgence, les lieux d’urgence et le [routage des appels](./what-are-emergency-locations-addresses-and-call-routing.md)?</span><span class="sxs-lookup"><span data-stu-id="c9246-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](./what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="c9246-109">Pour savoir comment obtenir un plan d’appel et combien cela coûte, consultez la gestion des [licences de module supplémentaire Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="c9246-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="c9246-110">Vous pouvez affecter ou modifier un emplacement d’urgence pour un utilisateur dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9246-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c9246-111">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9246-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c9246-112">Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Numéros de**  >  **téléphone vocal.**</span><span class="sxs-lookup"><span data-stu-id="c9246-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="c9246-113">Dans la page **Numéros de** téléphone, cliquez sur **l’onglet** Numéros, sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="c9246-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="c9246-114">Dans le **volet Édition,** sous Emplacement **d’urgence,** faites l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9246-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="c9246-115">Pour affecter un emplacement d’urgence, recherchez et sélectionnez un emplacement d’urgence.</span><span class="sxs-lookup"><span data-stu-id="c9246-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="c9246-116">Pour modifier l’emplacement d’urgence déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement existant, puis recherchez et sélectionnez l’emplacement que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="c9246-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="c9246-117">Selon que vous voulez envoyer un courrier électronique à l’utilisateur avec ses informations de numéro de téléphone, désactiver ou activer l’utilisateur de courrier avec des **informations de numéro de téléphone.**</span><span class="sxs-lookup"><span data-stu-id="c9246-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="c9246-118">Par défaut, c’est le cas.</span><span class="sxs-lookup"><span data-stu-id="c9246-118">By default, this is on.</span></span>

5. <span data-ttu-id="c9246-119">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="c9246-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="c9246-120">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9246-120">Using PowerShell</span></span>

<span data-ttu-id="c9246-121">Voir [Set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser)</span><span class="sxs-lookup"><span data-stu-id="c9246-121">See [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="c9246-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c9246-122">Related topics</span></span>

- [<span data-ttu-id="c9246-123">Gestion des appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="c9246-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="c9246-124">Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="c9246-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="c9246-125">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="c9246-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="c9246-126">Affecter ou modifier un lieu pour un emplacement d’urgence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9246-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="c9246-127">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="c9246-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="c9246-128">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="c9246-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)
- [<span data-ttu-id="c9246-129">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9246-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)