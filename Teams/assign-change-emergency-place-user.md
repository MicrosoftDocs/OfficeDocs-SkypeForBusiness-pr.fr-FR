---
title: Attribution, modification des emplacements d’urgence pour les utilisateurs
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
description: Dans cet article, vous allez découvrir comment affecter ou changer l’emplacement d’un emplacement d’urgence pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539511"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="d3584-103">Affectation ou modification de l’emplacement d’un emplacement d’urgence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="d3584-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="d3584-104">Chaque numéro de téléphone actif doit disposer d’un emplacement d’urgence associé lorsque vous attribuez le numéro de téléphone à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d3584-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="d3584-105">(Vous associez l’adresse lorsque vous recevez un numéro de téléphone dans Office 365 ou lorsque vous transférez un numéro de téléphone.) Lorsque vous associez le numéro à un emplacement d’urgence, vous pouvez également ajouter un emplacement pour fournir un emplacement plus précis au sein d’un emplacement physique.</span><span class="sxs-lookup"><span data-stu-id="d3584-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="d3584-106">Un lieu peut être le plancher, l’aile de bâtiment ou le numéro de bureau où se trouve l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d3584-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="d3584-107">Vous pouvez avoir un nombre illimité d’emplacements pour un emplacement d’urgence donné et vous pouvez modifier l’endroit où l’utilisateur se déplace vers un autre bureau ou bâtiment.</span><span class="sxs-lookup"><span data-stu-id="d3584-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="d3584-108">Par exemple, si l’utilisateur passe de l’étage 34 au sol 35.</span><span class="sxs-lookup"><span data-stu-id="d3584-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="d3584-109">Pour plus d’informations sur la façon d’obtenir des plans d’appel et leur coût, voir [licences de complément d’équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="d3584-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="d3584-110">Vous pouvez attribuer ou modifier l’emplacement d’un emplacement d’urgence pour un utilisateur dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3584-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d3584-111">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3584-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="d3584-112">Dans le volet de navigation de gauche du centre d’administration de **Voice**Microsoft Teams, cliquez sur  >  **numéros de téléphone**vocaux.</span><span class="sxs-lookup"><span data-stu-id="d3584-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="d3584-113">Dans la page **numéros de téléphone** , cliquez sur l’onglet **numéros** , sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="d3584-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="d3584-114">Dans le volet **édition** , sous **emplacement d’urgence**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3584-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="d3584-115">Pour attribuer un emplacement, recherchez l’emplacement ou l’emplacement, puis sélectionnez l’emplacement dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="d3584-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="d3584-116">Pour modifier l’emplacement qui est déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement et l’emplacement, recherchez et sélectionnez l’emplacement que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="d3584-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="d3584-117">Si vous souhaitez envoyer à l’utilisateur un message électronique contenant son numéro de téléphone, désactivez ou activez l’option **courrier électronique avec les informations**sur le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="d3584-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="d3584-118">Par défaut, ce paramètre est activé.</span><span class="sxs-lookup"><span data-stu-id="d3584-118">By default, this is on.</span></span>

5. <span data-ttu-id="d3584-119">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="d3584-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="d3584-120">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3584-120">Using PowerShell</span></span>

<span data-ttu-id="d3584-121">Voir [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="d3584-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d3584-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3584-122">Related topics</span></span>

- [<span data-ttu-id="d3584-123">Gérer les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="d3584-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="d3584-124">Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="d3584-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="d3584-125">Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="d3584-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="d3584-126">Affecter ou modifier un emplacement d’urgence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="d3584-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="d3584-127">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="d3584-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="d3584-128">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="d3584-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
