---
title: Vue d’ensemble de membres dynamiques pour les équipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 10/10/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez les membres de l’équipe dynamique en fonction DAS.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a98009237d6575e97705ae7a8eea4b444ac77a0
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25682365"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="bedd1-103">Vue d’ensemble de membres dynamiques pour les équipes</span><span class="sxs-lookup"><span data-stu-id="bedd1-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="bedd1-104">Teams Microsoft prend en charge les équipes associées aux groupes de Office 365 à l’aide de membres dynamiques.</span><span class="sxs-lookup"><span data-stu-id="bedd1-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="bedd1-105">Membres dynamiques permet l’appartenance d’une équipe à être définis par une ou plusieurs règles qui vérifient pour certains attributs de l’utilisateur dans Azure Active Directory (DAS).</span><span class="sxs-lookup"><span data-stu-id="bedd1-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="bedd1-106">Les utilisateurs sont automatiquement ajoutées ou supprimées pour les équipes corrects que modifier les attributs de l’utilisateur ou les utilisateurs rejoignent ou quittent de client.</span><span class="sxs-lookup"><span data-stu-id="bedd1-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="bedd1-107">Avec appartenance dynamique, que vous pouvez le programme d’installation des équipes pour certaines cohortes d’utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="bedd1-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="bedd1-108">Les scénarios possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="bedd1-108">Possible scenarios include:</span></span>
- <span data-ttu-id="bedd1-109">Un hôpital peut créer des équipes distinctes pour personnel, les médecins et chirurgiens de diffuser des communications.</span><span class="sxs-lookup"><span data-stu-id="bedd1-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="bedd1-110">Ceci est particulièrement important si l’hôpital repose sur les employés temp.</span><span class="sxs-lookup"><span data-stu-id="bedd1-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="bedd1-111">Une université peut créer une équipe pour tous les enseignants au sein d’une université particulier, y compris une faculté auxiliaire du qui change fréquemment.</span><span class="sxs-lookup"><span data-stu-id="bedd1-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="bedd1-112">Une compagnie souhaite créer une équipe pour chaque vol (par exemple une mardi MIDI sans interruption de Chicago à Atlanta) et disposer d’une équipe de vol régulièrement modifié automatiquement affectées ou supprimés selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="bedd1-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="bedd1-113">À l’aide de cette fonctionnalité, mise à jour des membres d’une équipe donnée automatiquement selon un ensemble spécifique de critères, au lieu de gérer manuellement les appartenances.</span><span class="sxs-lookup"><span data-stu-id="bedd1-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="bedd1-114">Cela nécessite des licences d’Azure AD Premium P1 et l’appartenance de l’équipe peut être [attribué par un administrateur du client](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) pour les propriétés de l’utilisateur DAS à condition qu’un client et un compte d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="bedd1-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="bedd1-115">Microsoft Teams peut prendre de quelques minutes à 2 heures pour refléter les modifications d’appartenance dynamique une fois qu’ils prennent effet dans le groupe d’Office 365 pour une équipe.</span><span class="sxs-lookup"><span data-stu-id="bedd1-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> <span data-ttu-id="bedd1-116">Les règles peuvent définir des membres de l’équipe, mais pas les propriétaires de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bedd1-116">Rules can define Team members, but not team Owners.</span></span>

## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="bedd1-117">Création et gestion d’un groupe d’Office 365 avec appartenance dynamique</span><span class="sxs-lookup"><span data-stu-id="bedd1-117">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="bedd1-118">En étant connecté le client d’administration, suivez les instructions de [Création d’un groupe dynamique et de vérifier l’état](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="bedd1-118">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="bedd1-119">Selon vos besoins, font référence aux [règles de membres dynamiques pour les groupes dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="bedd1-119">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="bedd1-120">Créer une nouvelle équipe avec votre groupe O365</span><span class="sxs-lookup"><span data-stu-id="bedd1-120">Create a new team with your O365 group</span></span>

<span data-ttu-id="bedd1-121">Attendez que les modifications d’appartenance prennent effet maintenant et créer une nouvelle équipe comme décrit dans les [groupes d’améliorer existant Office 365 avec les équipes Microsoft](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="bedd1-121">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="bedd1-122">Appliquer l’appartenance dynamique à une équipe existante</span><span class="sxs-lookup"><span data-stu-id="bedd1-122">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="bedd1-123">Vous pouvez également prendre une équipe existante et modifier pour avoir une appartenance dynamique, comme décrit dans [Modifier l’appartenance au groupe statique dynamique dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="bedd1-123">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="bedd1-124">Changements de comportement du client</span><span class="sxs-lookup"><span data-stu-id="bedd1-124">Changes in client behavior</span></span>

<span data-ttu-id="bedd1-125">Une fois que l’appartenance dynamique est activé pour une équipe, les clients équipes n’autorise plus gestion des membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bedd1-125">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="bedd1-126">Toutes les options pour ajouter des membres, modifier des rôles, envoyer approuver les demandes de participation et laissez l’équipe sont masquées.</span><span class="sxs-lookup"><span data-stu-id="bedd1-126">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
