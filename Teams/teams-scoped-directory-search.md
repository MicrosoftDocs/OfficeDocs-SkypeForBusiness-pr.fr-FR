---
title: Utiliser Microsoft Teams étendue de recherche dans l’annuaire
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser recherche dans l’annuaire sur lesquelles porte Teams Microsoft pour fournir des vues personnalisées du répertoire.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c8173445fff6acaa3a5381199220a376401076c
ms.sourcegitcommit: 6d30cfdd8c8b8908d4e4f278c39fd22062f4a888
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890696"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="90841-103">Utiliser Microsoft Teams étendue de recherche dans l’annuaire</span><span class="sxs-lookup"><span data-stu-id="90841-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="90841-104">Recherche dans l’annuaire étendue Microsoft Teams permet aux organisations de créer des limites virtuels qui contrôlent la façon dont les utilisateurs peuvent rechercher et communiquer avec d’autres utilisateurs dans leur organisation.</span><span class="sxs-lookup"><span data-stu-id="90841-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="90841-105">Microsoft Teams permet aux entreprises de fournir des vues personnalisées du répertoire à leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="90841-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="90841-106">Teams Microsoft utilise les [stratégies de carnet d’adresses Exchange](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) pour prendre en charge ces affichages personnalisés.</span><span class="sxs-lookup"><span data-stu-id="90841-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) to support these custom views.</span></span> <span data-ttu-id="90841-107">Une fois que les stratégies sont activées, les résultats renvoyés par la recherche pour d’autres utilisateurs (par exemple, pour lancer une conversation ou pour ajouter des membres à une équipe) seront étendus en fonction des stratégies configurées.</span><span class="sxs-lookup"><span data-stu-id="90841-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="90841-108">Les utilisateurs ne sera pas en mesure de rechercher ou de découvrir les équipes lors de la recherche à étendue définie est en vigueur.</span><span class="sxs-lookup"><span data-stu-id="90841-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="90841-109">Quand utiliser les recherches dans l’annuaire étendue ?</span><span class="sxs-lookup"><span data-stu-id="90841-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="90841-110">Scénarios qui tirent parti des recherches dans l’annuaire étendue définie sont similaires aux scénarios téléchargeable stratégie.</span><span class="sxs-lookup"><span data-stu-id="90841-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="90841-111">Par exemple, vous souhaiterez peut-être utiliser la recherche dans l’annuaire étendue dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="90841-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="90841-112">Votre organisation possède plusieurs sociétés dans son client que vous souhaitez conserver séparément.</span><span class="sxs-lookup"><span data-stu-id="90841-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="90841-113">Votre école veut limiter les conversations entre la faculté et aux étudiants.</span><span class="sxs-lookup"><span data-stu-id="90841-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="90841-114">Vous pouvez en savoir plus sur l’utilisation des stratégies de carnet d’adresses [ici](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="90841-114">You can learn more about how address book policies can be used [here](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90841-115">Stratégies de carnet d’adresses fournissent uniquement une séparation virtuelle d’utilisateurs du point de vue de répertoire.</span><span class="sxs-lookup"><span data-stu-id="90841-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="90841-116">Les utilisateurs peuvent lancer toujours les communications avec d’autres personnes en fournissant des adresses de messagerie complète.</span><span class="sxs-lookup"><span data-stu-id="90841-116">Users can still initiate communications with others by providing complete email addresses.</span></span> 

## <a name="enable-scoped-directory-search"></a><span data-ttu-id="90841-117">Activer la recherche de répertoire sur lesquelles porte</span><span class="sxs-lookup"><span data-stu-id="90841-117">Enable scoped directory search</span></span>

1.  <span data-ttu-id="90841-118">Stratégies de carnet d’adresses permet de configurer votre organisation en sous-groupes virtuels.</span><span class="sxs-lookup"><span data-stu-id="90841-118">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="90841-119">Pour plus d’informations, voir [procédures de stratégies de carnet d’adresses](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="90841-119">For more information, see [Procedures for address book policies](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span></span>

2.  <span data-ttu-id="90841-120">Se connecter au centre d’administration Microsoft 365, sélectionnez **centre Admin**et sélectionnez **équipes & Skype**.</span><span class="sxs-lookup"><span data-stu-id="90841-120">Sign in to the Microsoft 365 admin center, select **Admin centers**, and then select **Teams & Skype**.</span></span>
 
3.  <span data-ttu-id="90841-121">Dans Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres à l’échelle de la société** > **paramètres équipes**.</span><span class="sxs-lookup"><span data-stu-id="90841-121">In the Microsoft Teams & Skype for Business admin center, select **Org-wide settings** > **Teams settings**.</span></span>

4.  <span data-ttu-id="90841-122">Sous **recherche**, en regard de **recherche dans l’annuaire étendue dans les équipes à l’aide d’une stratégie de carnet d’adresses Exchange (APB)**, activez la bascule **sur**.</span><span class="sxs-lookup"><span data-stu-id="90841-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span> 

    ![Étendue de recherche dans l’annuaire dans les équipes & Skype entreprise centre d’administration](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="90841-124">Configurations hybrides (équipes avec Exchange local) ne prennent pas charge en mode de recherche à étendue définie.</span><span class="sxs-lookup"><span data-stu-id="90841-124">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

