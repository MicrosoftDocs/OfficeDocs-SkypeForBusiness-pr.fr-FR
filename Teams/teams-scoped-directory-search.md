---
title: Utiliser la recherche d’annuaire étendue Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
description: Découvrez comment utiliser la recherche dans l’annuaire d’étendues de Microsoft teams pour fournir des vues personnalisées de l’annuaire.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e81e2fb588e718060ffbdf90a51c020ff2d6556c
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326591"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="96881-103">Utiliser la recherche d’annuaire étendue Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96881-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="96881-104">La fonction de recherche dans l’arborescence de Microsoft teams permet aux organisations de créer des frontières virtuelles qui contrôlent la façon dont les utilisateurs peuvent trouver et communiquer avec d’autres utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="96881-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="96881-105">Microsoft teams permet aux organisations d’offrir des vues personnalisées de l’annuaire à leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="96881-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="96881-106">Microsoft teams utilise des [stratégies de barrage des informations](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) pour prendre en charge ces affichages personnalisés.</span><span class="sxs-lookup"><span data-stu-id="96881-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="96881-107">Une fois les stratégies activées, les résultats renvoyés par les recherches d’autres utilisateurs (par exemple, pour lancer une discussion ou ajouter des membres à une équipe) seront définis dans l’étendue conformément aux stratégies configurées.</span><span class="sxs-lookup"><span data-stu-id="96881-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="96881-108">Les utilisateurs ne seront pas en mesure de rechercher ou de découvrir les équipes lorsque la recherche avec l’étendue est en vigueur.</span><span class="sxs-lookup"><span data-stu-id="96881-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="96881-109">Dans les environnements Exchange hybrides, cette fonctionnalité fonctionne uniquement avec les boîtes aux lettres Exchange Online, et non avec les boîtes aux lettres locales.</span><span class="sxs-lookup"><span data-stu-id="96881-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="96881-110">Quand utiliser les recherches dans l’annuaire avec une application ?</span><span class="sxs-lookup"><span data-stu-id="96881-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="96881-111">Les scénarios qui s’offrent à vous pour les recherches dans l’annuaire sont similaires aux scénarios de stratégie de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="96881-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="96881-112">Par exemple, vous pouvez utiliser la recherche dans l’annuaire avec l’étendue dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="96881-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="96881-113">Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées.</span><span class="sxs-lookup"><span data-stu-id="96881-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="96881-114">Votre école souhaite limiter les conversations entre la faculté et les étudiants.</span><span class="sxs-lookup"><span data-stu-id="96881-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="96881-115">Pour plus d’informations sur l’utilisation des stratégies de carnet d’adresses, voir [stratégies de protection des informations dans Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span><span class="sxs-lookup"><span data-stu-id="96881-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96881-116">Les politiques du carnet d’adresses fournissent uniquement une séparation virtuelle des utilisateurs du point de vue du répertoire.</span><span class="sxs-lookup"><span data-stu-id="96881-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="96881-117">Les utilisateurs peuvent toujours lancer des communications avec d’autres personnes en leur fournissant des adresses de messagerie complètes.</span><span class="sxs-lookup"><span data-stu-id="96881-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="96881-118">Il est également important de noter que toutes les données utilisateur qui ont déjà été mises en cache avant d’appliquer les stratégies de carnet d’adresses nouvelles ou mises à jour restent disponibles pour les utilisateurs pendant 30 jours maximum.</span><span class="sxs-lookup"><span data-stu-id="96881-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="96881-119">Activez la recherche dans l’annuaire avec étendue</span><span class="sxs-lookup"><span data-stu-id="96881-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="96881-120">Utiliser des stratégies de cloisonnement des informations pour configurer votre organisation en sous-groupes virtuels.</span><span class="sxs-lookup"><span data-stu-id="96881-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="96881-121">Pour plus d’informations, consultez [définir des stratégies de barrière des informations](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span><span class="sxs-lookup"><span data-stu-id="96881-121">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="96881-122">Dans le centre d’administration de Microsoft Teams, sélectionnez Paramètres d’équipe **des paramètres à l’échelle de l’organisation**  >  **Teams settings**.</span><span class="sxs-lookup"><span data-stu-id="96881-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="96881-123">Sous **recherche**, en regard de la **zone Rechercher dans l’annuaire dans teams à l’aide d’une stratégie de carnet d’adresses Exchange (ABP)**, activez le bouton **bascule.**</span><span class="sxs-lookup"><span data-stu-id="96881-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Recherche dans l’annuaire dans l’étendue dans le centre d’administration Microsoft teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="96881-125">La réplication de cette modification peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="96881-125">This change can take a few hours to replicate.</span></span>
