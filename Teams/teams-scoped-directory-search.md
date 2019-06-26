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
- Teams_ITAdmin_Help
description: Découvrez comment utiliser la recherche dans l’annuaire d’étendues de Microsoft teams pour fournir des vues personnalisées de l’annuaire.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf65cec72c21e34e0aab8338d20ae36549497846
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221730"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="841ce-103">Utiliser la recherche d’annuaire étendue Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="841ce-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="841ce-104">La fonction de recherche dans l’arborescence de Microsoft teams permet aux organisations de créer des frontières virtuelles qui contrôlent la façon dont les utilisateurs peuvent trouver et communiquer avec d’autres utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="841ce-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="841ce-105">Microsoft teams permet aux organisations d’offrir des vues personnalisées de l’annuaire à leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="841ce-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="841ce-106">Microsoft teams utilise des [stratégies de carnet d’adresses Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) pour prendre en charge ces affichages personnalisés.</span><span class="sxs-lookup"><span data-stu-id="841ce-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="841ce-107">Une fois les stratégies activées, les résultats renvoyés par les recherches d’autres utilisateurs (par exemple, pour lancer une discussion ou ajouter des membres à une équipe) seront définis dans l’étendue conformément aux stratégies configurées.</span><span class="sxs-lookup"><span data-stu-id="841ce-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="841ce-108">Les utilisateurs ne seront pas en mesure de rechercher ou de découvrir les équipes lorsque la recherche avec l’étendue est en vigueur.</span><span class="sxs-lookup"><span data-stu-id="841ce-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="841ce-109">Quand utiliser les recherches dans l’annuaire avec une application?</span><span class="sxs-lookup"><span data-stu-id="841ce-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="841ce-110">Les scénarios qui s’offrent à vous pour les recherches dans l’annuaire sont similaires aux scénarios de stratégie de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="841ce-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="841ce-111">Par exemple, vous pouvez utiliser la recherche dans l’annuaire avec l’étendue dans les situations suivantes:</span><span class="sxs-lookup"><span data-stu-id="841ce-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="841ce-112">Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées.</span><span class="sxs-lookup"><span data-stu-id="841ce-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="841ce-113">Votre école souhaite limiter les conversations entre la faculté et les étudiants.</span><span class="sxs-lookup"><span data-stu-id="841ce-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="841ce-114">Pour plus d’informations sur l’utilisation des stratégies du carnet d’adresses, voir [stratégies du carnet d’adresses dans Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="841ce-114">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="841ce-115">Les politiques du carnet d’adresses fournissent uniquement une séparation virtuelle des utilisateurs du point de vue du répertoire.</span><span class="sxs-lookup"><span data-stu-id="841ce-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="841ce-116">Les utilisateurs peuvent toujours lancer des communications avec d’autres personnes en leur fournissant des adresses de messagerie complètes.</span><span class="sxs-lookup"><span data-stu-id="841ce-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="841ce-117">Il est également important de noter que toutes les données utilisateur qui ont déjà été mises en cache avant d’appliquer les stratégies de carnet d’adresses nouvelles ou mises à jour restent disponibles pour les utilisateurs pendant 30 jours maximum.</span><span class="sxs-lookup"><span data-stu-id="841ce-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="841ce-118">Activez la recherche dans l’annuaire avec étendue</span><span class="sxs-lookup"><span data-stu-id="841ce-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="841ce-119">Utilisez les stratégies du carnet d’adresses pour configurer votre organisation en sous-groupes virtuels.</span><span class="sxs-lookup"><span data-stu-id="841ce-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="841ce-120">Pour plus d’informations, consultez la rubrique [procédures pour les stratégies du carnet d’adresses](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="841ce-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2. <span data-ttu-id="841ce-121">Dans le centre d’administration de Microsoft Teams, sélectionnez > **paramètres d’équipe** **des paramètres à l’échelle**de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="841ce-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="841ce-122">Sous **recherche**, en regard de la **zone Rechercher dans l’annuaire dans teams à l’aide d’une stratégie de carnet d’adresses Exchange (APB)**, activez le bouton bascule. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="841ce-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Recherche dans l’annuaire dans l’étendue dans le centre d’administration Microsoft teams](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="841ce-124">Les configurations hybrides (teams avec Exchange local) ne prennent pas en charge le mode de recherche étendu.</span><span class="sxs-lookup"><span data-stu-id="841ce-124">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

