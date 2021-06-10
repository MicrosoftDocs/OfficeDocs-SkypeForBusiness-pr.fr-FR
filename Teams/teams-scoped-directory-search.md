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
description: Découvrez comment utiliser Microsoft Teams dans l’annuaire pour fournir des affichages personnalisés de l’annuaire.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1048b6451163cd7b0cdbcd3f52e48c6b0f4811d1
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717795"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="7266a-103">Utiliser la recherche d’annuaire étendue Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7266a-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="7266a-104">Microsoft Teams dans l’étendue de la recherche dans l’annuaire permet aux organisations de créer des limites virtuelles qui contrôlent la façon dont les utilisateurs peuvent trouver et communiquer avec d’autres utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="7266a-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="7266a-105">Microsoft Teams organisations de fournir des affichages personnalisés de l’annuaire à leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7266a-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="7266a-106">Microsoft Teams utilise les [stratégies de la](/microsoft-365/compliance/information-barriers) barrière des informations pour prendre en charge ces affichages personnalisés.</span><span class="sxs-lookup"><span data-stu-id="7266a-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="7266a-107">Une fois les stratégies activées, les résultats renvoyés par les recherches d’autres utilisateurs (par exemple, pour démarrer une conversation ou pour ajouter des membres à une équipe) seront étendues en fonction des stratégies configurées.</span><span class="sxs-lookup"><span data-stu-id="7266a-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="7266a-108">Les utilisateurs ne pourront pas rechercher ou découvrir des équipes lorsque la recherche étendue est en vigueur, mais les membres existants de ces équipes peuvent ajouter des utilisateurs, comme le permet les stratégies de barrière des informations actives.</span><span class="sxs-lookup"><span data-stu-id="7266a-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="7266a-109">Dans Exchange environnements hybrides, cette fonctionnalité fonctionne uniquement avec Exchange Online, et non avec les boîtes aux lettres locaux.</span><span class="sxs-lookup"><span data-stu-id="7266a-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

<span data-ttu-id="7266a-110">Voir aussi [Stratégies du carnet d’adresses Exchange Online.](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)</span><span class="sxs-lookup"><span data-stu-id="7266a-110">See also [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="7266a-111">Quand devez-vous utiliser des recherches dans l’annuaire dans l’étendue ?</span><span class="sxs-lookup"><span data-stu-id="7266a-111">When should you use scoped directory searches?</span></span>

<span data-ttu-id="7266a-112">Les scénarios qui viennent s’en tirer profit sont similaires aux scénarios de stratégies de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="7266a-112">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="7266a-113">Par exemple, vous pouvez utiliser la recherche dans l’annuaire étendue dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7266a-113">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="7266a-114">Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées.</span><span class="sxs-lookup"><span data-stu-id="7266a-114">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="7266a-115">Votre école souhaite limiter les conversations entre la faculté et les étudiants.</span><span class="sxs-lookup"><span data-stu-id="7266a-115">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="7266a-116">Pour découvrir comment utiliser les stratégies du carnet d’adresses, lisez la barrière des [informations dans Exchange Online.](/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="7266a-116">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7266a-117">Les stratégies de carnet d’adresses offrent une séparation virtuelle des utilisateurs du point de vue de l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="7266a-117">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="7266a-118">Il est également important de noter que toutes les données des utilisateurs qui avaient déjà été mises en cache avant l’application de stratégies de carnet d’adresses nouvelles ou mises à jour resteront disponibles aux utilisateurs pendant 30 jours au plus.</span><span class="sxs-lookup"><span data-stu-id="7266a-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="7266a-119">Activer la recherche dans l’annuaire étendue</span><span class="sxs-lookup"><span data-stu-id="7266a-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="7266a-120">Utilisez des stratégies de barrière des informations pour configurer votre organisation en sous-groupes virtuels.</span><span class="sxs-lookup"><span data-stu-id="7266a-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="7266a-121">Pour plus d’informations, voir [Définir les stratégies de barrière de l’information.](/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="7266a-121">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="7266a-122">Dans le Microsoft Teams d’administration, sélectionnez **Paramètres** à l’échelle de  >  **l’organisation Teams paramètres.**</span><span class="sxs-lookup"><span data-stu-id="7266a-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="7266a-123">Sous **Rechercher,** en face de la recherche dans l’étendue du répertoire Teams à l’aide d’une stratégie de carnet d’Exchange de données **(ABP),** activer le **basculement.**</span><span class="sxs-lookup"><span data-stu-id="7266a-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Recherche dans l’annuaire dans l’étendue Microsoft Teams centre d’administration](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="7266a-125">La réplique de cette modification peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="7266a-125">This change can take a few hours to replicate.</span></span>
