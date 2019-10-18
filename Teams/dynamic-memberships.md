---
title: Présentation de l’appartenance dynamique pour les équipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: En savoir plus sur l’appartenance aux équipes dynamiques basée sur AAD.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d22c7f068617cd4c5c73c850a37eaa89a0c8efa
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569895"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="1e2b0-103">Présentation de l’appartenance dynamique pour les équipes</span><span class="sxs-lookup"><span data-stu-id="1e2b0-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="1e2b0-104">Microsoft teams prend en charge les équipes associées aux groupes Office 365 à l’aide de l' *appartenance dynamique*.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-104">Microsoft Teams supports teams associated with Office 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="1e2b0-105">L’appartenance au groupe dynamique permet de définir l’appartenance d’une équipe à une ou plusieurs règles qui recherchent certains attributs d’utilisateur dans Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1e2b0-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="1e2b0-106">Les utilisateurs sont ajoutés ou supprimés automatiquement aux équipes appropriées en tant qu’attributs utilisateur, mais ils rejoignent et quittent le client.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="1e2b0-107">L’appartenance dynamique vous permet de configurer des équipes pour certaines cohortes d’utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="1e2b0-108">Les scénarios possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="1e2b0-108">Possible scenarios include:</span></span>
- <span data-ttu-id="1e2b0-109">Un hôpital peut créer des équipes distinctes pour les infirmières, les médecins et les chirurgiens en communication de diffusion.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="1e2b0-110">Cela est particulièrement important si l’hôpital repose sur des employés temporaires.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="1e2b0-111">Une université peut créer une équipe pour toutes les universités au sein d’un collège particulier, y compris des enseignants qui changent fréquemment.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="1e2b0-112">Une compagnie aérienne veut créer une équipe pour chaque version d’évaluation (par exemple, un mardi de l’après-midi sans arrêt de Chicago vers Atlanta) et avoir modifié automatiquement l’équipe de volée ou supprimée en conséquence.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="1e2b0-113">Cette fonctionnalité permet aux membres d’une équipe donnée de mettre à jour automatiquement en fonction d’un ensemble spécifique de critères, au lieu de gérer manuellement l’appartenance.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="1e2b0-114">Pour cela, il est nécessaire d’affecter des licences d’Azure AD Premium P1 et des membres d’une équipe à l' [aide d’un administrateur client](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) aux propriétés Azure AD de chaque utilisateur, dans la mesure où vous disposez d’un client et d’un compte d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="1e2b0-115">Microsoft Teams ne doit compter que de quelques minutes à 2 heures pour refléter les changements d’appartenance dynamique une fois qu’ils ont été appliqués dans le groupe Office 365 d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="1e2b0-116">Les règles peuvent définir qui est membre d’une équipe, sans qui est le propriétaire de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="1e2b0-117">Voir [limites et spécifications de Microsoft teams](limits-specifications-teams.md) pour les limites actuelles relatives aux tailles d’équipes et de canaux.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="1e2b0-118">Les propriétaires ne seront pas en mesure d’ajouter ou de supprimer des utilisateurs en tant que membres de l’équipe, car ils sont définis par des règles de groupe dynamique.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="1e2b0-119">Les membres ne seront pas en mesure de laisser des équipes sauvegardées par des groupes dynamiques.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="1e2b0-120">Création et gestion d’un groupe Office 365 avec appartenance dynamique</span><span class="sxs-lookup"><span data-stu-id="1e2b0-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="1e2b0-121">Lorsque vous êtes connecté en tant qu’administrateur client, suivez les instructions de la procédure de [création d’un groupe dynamique et vérification](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)de l’État.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="1e2b0-122">Le cas échéant, voir [règles d’appartenance dynamique pour les groupes dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="1e2b0-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="1e2b0-123">Créer une équipe à l’aide de votre groupe O365</span><span class="sxs-lookup"><span data-stu-id="1e2b0-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="1e2b0-124">Autorisez désormais le temps nécessaire au changement d’appartenance pour que les modifications soient prises en compte, puis créez une nouvelle équipe comme décrit dans [améliorer les groupes Office 365 existants avec Microsoft teams](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="1e2b0-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="1e2b0-125">Appliquer une appartenance dynamique à une équipe existante</span><span class="sxs-lookup"><span data-stu-id="1e2b0-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="1e2b0-126">Vous pouvez également prendre une équipe existante et la modifier pour qu’elle dispose d’une appartenance dynamique, comme décrit dans la rubrique [changer l’appartenance au groupe statique sur dynamique dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="1e2b0-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="1e2b0-127">Modifications du comportement du client</span><span class="sxs-lookup"><span data-stu-id="1e2b0-127">Changes in client behavior</span></span>

<span data-ttu-id="1e2b0-128">Une fois l’appartenance dynamique activée pour une équipe, les clients teams n’autorisent plus la gestion des membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="1e2b0-129">Options permettant d’ajouter des membres, de modifier les rôles des membres, d’envoyer et d’approuver des demandes de jointure et de laisser l’équipe tout masquée.</span><span class="sxs-lookup"><span data-stu-id="1e2b0-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
