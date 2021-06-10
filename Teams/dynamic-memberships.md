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
description: Découvrez comment votre Microsoft Teams prend en charge les équipes associées Microsoft 365 groupes à l’aide de l’appartenance dynamique.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856323"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="fdde6-103">Présentation de l’appartenance dynamique pour les équipes</span><span class="sxs-lookup"><span data-stu-id="fdde6-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="fdde6-104">Microsoft Teams prend en charge les équipes associées Microsoft 365 groupes à l’aide *d’une appartenance dynamique.*</span><span class="sxs-lookup"><span data-stu-id="fdde6-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="fdde6-105">L’appartenance dynamique permet de définir l’appartenance d’une équipe par une ou plusieurs règles qui vérifient certains attributs d’utilisateur dans Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="fdde6-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="fdde6-106">Les utilisateurs sont ajoutés ou supprimés automatiquement des équipes correctes à mesure que les attributs des utilisateurs changent ou que des utilisateurs rejoignent et quittent le client.</span><span class="sxs-lookup"><span data-stu-id="fdde6-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="fdde6-107">L’appartenance dynamique vous permet de configurer des équipes pour certains utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fdde6-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="fdde6-108">Les scénarios possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="fdde6-108">Possible scenarios include:</span></span>
- <span data-ttu-id="fdde6-109">Un hôpital peut créer des équipes distinctes pour les infirmières, les médecins et les infirmières pour diffuser les communications.</span><span class="sxs-lookup"><span data-stu-id="fdde6-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="fdde6-110">Ceci est particulièrement important si l’hôpital s’appuie sur des employés temporaires.</span><span class="sxs-lookup"><span data-stu-id="fdde6-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="fdde6-111">Une université peut créer une équipe pour tous les enseignants d’une université en particulier, y compris un enseignant agrégé qui change fréquemment.</span><span class="sxs-lookup"><span data-stu-id="fdde6-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="fdde6-112">Une compagnie aérienne souhaite créer une équipe pour chaque vol (par exemple, un mardi après-midi sans s’arrêter de Chicago à Atlanta) et supprimer automatiquement ou automatiquement une équipe de vol en modification fréquente, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fdde6-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="fdde6-113">Cette fonctionnalité permet aux membres d’une équipe donnée de se mettre à jour automatiquement en fonction d’un ensemble spécifique de critères, au lieu de gérer manuellement l’appartenance.</span><span class="sxs-lookup"><span data-stu-id="fdde6-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="fdde6-114">Pour ce faire, les licences Azure AD Premium [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) P1 et l’appartenance à une équipe peuvent être attribuées par un administrateur de client aux propriétés Azure AD de n’importe quel utilisateur, à condition que vous utilisiez un client et un compte d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="fdde6-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="fdde6-115">Microsoft Teams peuvent prendre de quelques minutes à 2 heures pour refléter les changements d’appartenance dynamiques une fois qu’ils prennent effet dans le groupe Microsoft 365 d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="fdde6-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="fdde6-116">Lors de l’utilisation d’équipes avec des groupes dynamiques :</span><span class="sxs-lookup"><span data-stu-id="fdde6-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="fdde6-117">Les règles peuvent définir qui est membre d’une équipe, mais pas qui est propriétaire de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="fdde6-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="fdde6-118">Les propriétaires ne pourront pas ajouter ou supprimer des utilisateurs en tant que membres de l’équipe, car les membres sont définis par des règles de groupe dynamiques.</span><span class="sxs-lookup"><span data-stu-id="fdde6-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="fdde6-119">Teams clients n’autorisent pas la gestion des membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="fdde6-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="fdde6-120">Les options pour ajouter des membres, modifier les rôles de membre, envoyer et approuver des demandes d’adhésion et quitter l’équipe sont masquées.</span><span class="sxs-lookup"><span data-stu-id="fdde6-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="fdde6-121">Pour créer une équipe qui utilise [](/azure/active-directory/users-groups-roles/groups-create-rule) une appartenance dynamique, commencez par créer un groupe de Microsoft 365 dynamique, puis créez une équipe à partir [de ce groupe.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="fdde6-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="fdde6-122">Vous pouvez modifier une équipe existante pour avoir une appartenance dynamique.</span><span class="sxs-lookup"><span data-stu-id="fdde6-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="fdde6-123">Voir [Modifier l’appartenance aux groupes statiques](/azure/active-directory/users-groups-roles/groups-change-type) en dynamique dans Azure Active Directory pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="fdde6-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fdde6-124">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="fdde6-124">Related topics</span></span>

[<span data-ttu-id="fdde6-125">Limites et spécifications de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fdde6-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="fdde6-126">Règles d’appartenance dynamique pour les groupes dans Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fdde6-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
