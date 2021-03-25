---
title: Présentation de l’appartenance dynamique pour les équipes
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment Microsoft Teams prend en charge les équipes associées aux groupes Microsoft 365 en utilisant l’appartenance dynamique.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120766"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="50f93-103">Présentation de l’appartenance dynamique pour les équipes</span><span class="sxs-lookup"><span data-stu-id="50f93-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="50f93-104">Microsoft Teams prend en charge les équipes associées aux groupes Microsoft 365 en utilisant *l’appartenance dynamique.*</span><span class="sxs-lookup"><span data-stu-id="50f93-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="50f93-105">L’appartenance dynamique permet de définir l’appartenance d’une équipe par une ou plusieurs règles qui vérifient certains attributs d’utilisateur dans Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="50f93-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="50f93-106">Les utilisateurs sont ajoutés ou supprimés automatiquement des équipes correctes à mesure que les attributs des utilisateurs changent ou que des utilisateurs rejoignent et quittent le client.</span><span class="sxs-lookup"><span data-stu-id="50f93-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="50f93-107">L’appartenance dynamique vous permet de configurer des équipes pour certains utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="50f93-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="50f93-108">Les scénarios possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="50f93-108">Possible scenarios include:</span></span>
- <span data-ttu-id="50f93-109">Un hôpital peut créer des équipes distinctes pour les infirmières, les médecins et les infirmières pour diffuser les communications.</span><span class="sxs-lookup"><span data-stu-id="50f93-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="50f93-110">Ceci est particulièrement important si l’hôpital s’appuie sur des employés temporaires.</span><span class="sxs-lookup"><span data-stu-id="50f93-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="50f93-111">Une université peut créer une équipe pour tous les enseignants d’une université en particulier, y compris un enseignant agrégé qui change fréquemment.</span><span class="sxs-lookup"><span data-stu-id="50f93-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="50f93-112">Une compagnie aérienne souhaite créer une équipe pour chaque vol (par exemple, un mardi après-midi sans s’arrêter de Chicago à Atlanta) et supprimer automatiquement ou automatiquement une équipe de vol en modification fréquente, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="50f93-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="50f93-113">Cette fonctionnalité permet aux membres d’une équipe donnée de se mettre à jour automatiquement en fonction d’un ensemble spécifique de critères, au lieu de gérer manuellement l’appartenance.</span><span class="sxs-lookup"><span data-stu-id="50f93-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="50f93-114">Pour ce faire, les licences Azure AD [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) Premium P1 et l’appartenance à une équipe peuvent être attribuées par un administrateur client aux propriétés Azure AD de n’importe quel utilisateur, à condition que vous utilisiez un client et un compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="50f93-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="50f93-115">Microsoft Teams peut prendre de quelques minutes à 2 heures pour refléter les changements d’appartenance dynamiques une fois qu’ils prennent effet dans le groupe Microsoft 365 d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="50f93-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="50f93-116">Les règles peuvent définir qui est membre d’une équipe, mais pas qui est propriétaire de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="50f93-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="50f93-117">Consultez [les limites et les spécifications de Microsoft Teams pour](limits-specifications-teams.md) les limites actuelles sur la taille des équipes et des canaux.</span><span class="sxs-lookup"><span data-stu-id="50f93-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="50f93-118">Les propriétaires ne pourront pas ajouter ou supprimer des utilisateurs en tant que membres de l’équipe, car les membres sont définis par des règles de groupe dynamiques.</span><span class="sxs-lookup"><span data-stu-id="50f93-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="50f93-119">Les membres ne peuvent pas laisser les équipes dosées par des groupes dynamiques.</span><span class="sxs-lookup"><span data-stu-id="50f93-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="50f93-120">Création et gestion d’un groupe Microsoft 365 avec une appartenance dynamique</span><span class="sxs-lookup"><span data-stu-id="50f93-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="50f93-121">Lorsque vous êtes connecté en tant qu’administrateur client, suivez les instructions dans Créer un groupe [dynamique et vérifiez l’état.](/azure/active-directory/users-groups-roles/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="50f93-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="50f93-122">Selon les besoins, reportez-vous aux règles [d’appartenance dynamique pour les groupes dans Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-dynamic-membership)</span><span class="sxs-lookup"><span data-stu-id="50f93-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="50f93-123">Créer une équipe avec votre groupe Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="50f93-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="50f93-124">Accordez à présent le temps que les changements d’appartenance prennent effet et créez une équipe comme décrit dans Créer une équipe à partir [d’un groupe existant.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="50f93-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="50f93-125">Appliquer une appartenance dynamique à une équipe existante</span><span class="sxs-lookup"><span data-stu-id="50f93-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="50f93-126">Vous pouvez également prendre une équipe existante et la modifier pour avoir une appartenance dynamique, comme décrit dans Modifier l’appartenance à un groupe statique en dynamique dans [Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-change-type)</span><span class="sxs-lookup"><span data-stu-id="50f93-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="50f93-127">Modifications du comportement du client</span><span class="sxs-lookup"><span data-stu-id="50f93-127">Changes in client behavior</span></span>

<span data-ttu-id="50f93-128">Une fois l’appartenance dynamique activée pour une équipe, les clients Teams n’autoriseront plus la gestion des membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="50f93-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="50f93-129">Les options pour ajouter des membres, modifier les rôles de membre, envoyer et approuver des demandes d’adhésion et quitter l’équipe sont masquées.</span><span class="sxs-lookup"><span data-stu-id="50f93-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>