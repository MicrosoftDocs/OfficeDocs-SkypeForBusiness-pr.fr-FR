---
title: Utiliser la recherche d’annuaire étendue Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser la recherche dans l’annuaire dans l’étendue de Microsoft Teams pour fournir des affichages personnalisés de l’annuaire.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ede4b60878dbdd44edf369b0a3c1bb861ffe366
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094024"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="b31d3-103">Utiliser la recherche d’annuaire étendue Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b31d3-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="b31d3-104">La recherche dans l’annuaire dans l’étendue de Microsoft Teams permet aux organisations de créer des limites virtuelles qui contrôlent la façon dont les utilisateurs peuvent trouver et communiquer avec d’autres utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="b31d3-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="b31d3-105">Microsoft Teams permet aux organisations de fournir des affichages personnalisés de l’annuaire à leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b31d3-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="b31d3-106">Microsoft Teams utilise la [barrière de l’information](/microsoft-365/compliance/information-barriers) pour prendre en charge ces affichages personnalisés.</span><span class="sxs-lookup"><span data-stu-id="b31d3-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="b31d3-107">Une fois les stratégies activées, les résultats renvoyés par les recherches d’autres utilisateurs (par exemple, pour démarrer une conversation ou pour ajouter des membres à une équipe) seront étendues en fonction des stratégies configurées.</span><span class="sxs-lookup"><span data-stu-id="b31d3-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="b31d3-108">Les utilisateurs ne pourront pas effectuer de recherche ou découvrir d’équipes lorsque la recherche étendue est en vigueur, mais les membres existants de ces équipes peuvent ajouter des utilisateurs, comme le permet les stratégies actives de la barrière des informations.</span><span class="sxs-lookup"><span data-stu-id="b31d3-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b31d3-109">Dans les environnements Exchange hybrides, cette fonctionnalité fonctionne uniquement avec les boîtes aux lettres Exchange Online, et non avec les boîtes aux lettres locaux.</span><span class="sxs-lookup"><span data-stu-id="b31d3-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="b31d3-110">Quand devez-vous utiliser des recherches dans l’annuaire dans l’étendue ?</span><span class="sxs-lookup"><span data-stu-id="b31d3-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="b31d3-111">Les scénarios qui viennent s’en tirer profit sont similaires aux scénarios de stratégies de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="b31d3-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="b31d3-112">Par exemple, vous pouvez utiliser la recherche dans l’annuaire étendue dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b31d3-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="b31d3-113">Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées.</span><span class="sxs-lookup"><span data-stu-id="b31d3-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="b31d3-114">Votre école souhaite limiter les conversations entre la faculté et les étudiants.</span><span class="sxs-lookup"><span data-stu-id="b31d3-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="b31d3-115">Pour découvrir comment utiliser les stratégies du carnet d’adresses, [lisez les stratégies de](/microsoft-365/compliance/information-barriers)la barrière des informations dans Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b31d3-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b31d3-116">Les stratégies de carnet d’adresses offrent une séparation virtuelle des utilisateurs du point de vue de l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="b31d3-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="b31d3-117">Il est également important de noter que toutes les données des utilisateurs qui avaient déjà été mises en cache avant l’application de stratégies de carnet d’adresses nouvelles ou mises à jour resteront disponibles aux utilisateurs pendant 30 jours au plus.</span><span class="sxs-lookup"><span data-stu-id="b31d3-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="b31d3-118">Activer la recherche dans l’annuaire étendue</span><span class="sxs-lookup"><span data-stu-id="b31d3-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="b31d3-119">Utilisez des stratégies de barrière des informations pour configurer votre organisation en sous-groupes virtuels.</span><span class="sxs-lookup"><span data-stu-id="b31d3-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="b31d3-120">Pour plus d’informations, voir [Définir les stratégies de barrière de l’information.](/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="b31d3-120">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="b31d3-121">Dans le Centre d’administration Microsoft Teams, sélectionnez **les paramètres** Teams à l’échelle  >  **de l’organisation.**</span><span class="sxs-lookup"><span data-stu-id="b31d3-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="b31d3-122">Sous **Recherche,** en face de la recherche dans l’annuaire Scope dans Teams à l’aide d’une stratégie de carnet d’adresses **Exchange (ABP),** activer le **basculement.**</span><span class="sxs-lookup"><span data-stu-id="b31d3-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Recherche dans l’annuaire étendue dans le Centre d’administration Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="b31d3-124">La réplique de cette modification peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="b31d3-124">This change can take a few hours to replicate.</span></span>