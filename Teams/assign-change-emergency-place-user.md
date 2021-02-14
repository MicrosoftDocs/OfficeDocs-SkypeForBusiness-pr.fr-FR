---
title: Affectation, modification des emplacements d’urgence pour les utilisateurs
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
description: Dans cet article, vous allez découvrir comment affecter ou modifier l’emplacement d’urgence d’un emplacement pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809524"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="266fe-103">Affectation ou modification de l’emplacement d’urgence d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="266fe-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="266fe-104">Chaque numéro de téléphone actif doit avoir un emplacement d’urgence associé lorsque vous attribuez le numéro de téléphone à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="266fe-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="266fe-105">(Vous associez l’adresse lorsque vous obtenez un numéro de téléphone dans Office 365 ou lorsque vous transférez un numéro de téléphone.) Lorsque vous associez le numéro à un emplacement d’urgence, vous pouvez également ajouter un emplacement pour fournir un emplacement plus exact dans un emplacement physique.</span><span class="sxs-lookup"><span data-stu-id="266fe-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="266fe-106">Il peut s’agit de l’étage, de l’aile d’un bâtiment ou du numéro du bureau où se trouve l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="266fe-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="266fe-107">Vous pouvez avoir un nombre illimité d’emplacements pour un emplacement d’urgence donné, et vous pouvez changer d’emplacement si l’utilisateur change de bureau ou de bâtiment.</span><span class="sxs-lookup"><span data-stu-id="266fe-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="266fe-108">Par exemple, si l’utilisateur passe du 34e au 35e étage.</span><span class="sxs-lookup"><span data-stu-id="266fe-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="266fe-109">Pour savoir comment obtenir des forfaits d’appels et leurs tarifs, consultez la gestion des [licences de module supplémentaire Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="266fe-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="266fe-110">Vous pouvez affecter ou modifier l’emplacement d’urgence d’un utilisateur dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="266fe-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="266fe-111">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="266fe-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="266fe-112">Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Numéros de**  >  **téléphone vocal.**</span><span class="sxs-lookup"><span data-stu-id="266fe-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="266fe-113">Dans la page **Numéros de** téléphone, cliquez sur **l’onglet** Numéros, sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="266fe-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="266fe-114">Dans le **volet Édition,** sous Emplacement **d’urgence,** faites l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="266fe-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="266fe-115">Pour attribuer un lieu, recherchez l’emplacement, puis sélectionnez-le dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="266fe-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="266fe-116">Pour modifier l’emplacement déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement et l’emplacement existants, recherchez et sélectionnez l’emplacement à affecter.</span><span class="sxs-lookup"><span data-stu-id="266fe-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="266fe-117">Selon que vous voulez envoyer un courrier électronique à l’utilisateur avec ses informations de numéro de téléphone, désactiver ou activer l’utilisateur de courrier avec des **informations de numéro de téléphone.**</span><span class="sxs-lookup"><span data-stu-id="266fe-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="266fe-118">Par défaut, c’est le cas.</span><span class="sxs-lookup"><span data-stu-id="266fe-118">By default, this is on.</span></span>

5. <span data-ttu-id="266fe-119">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="266fe-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="266fe-120">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="266fe-120">Using PowerShell</span></span>

<span data-ttu-id="266fe-121">Voir [Set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="266fe-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="266fe-122">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="266fe-122">Related topics</span></span>

- [<span data-ttu-id="266fe-123">Gestion des appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="266fe-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="266fe-124">Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="266fe-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="266fe-125">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="266fe-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="266fe-126">Affecter ou modifier un emplacement d’urgence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="266fe-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="266fe-127">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="266fe-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="266fe-128">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="266fe-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
