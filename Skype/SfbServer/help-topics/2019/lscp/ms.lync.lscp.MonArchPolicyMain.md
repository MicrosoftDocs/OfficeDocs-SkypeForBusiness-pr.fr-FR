---
title: Stratégie d’archivage
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 'Les stratégies d’archivage vous permettent d’activer et de désactiver l’archivage pour les utilisateurs de Skype Entreprise Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’une des opérations suivantes ou les deux :'
ms.openlocfilehash: 041fc71da18ff38b14e82ce9d2ab14f366326b29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833614"
---
# <a name="archiving-policy"></a><span data-ttu-id="48a7e-104">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="48a7e-104">Archiving Policy</span></span>
 
<span data-ttu-id="48a7e-105">Les stratégies d’archivage vous permettent d’activer et de désactiver l’archivage pour les utilisateurs de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="48a7e-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="48a7e-106">Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’une des opérations suivantes ou les deux :</span><span class="sxs-lookup"><span data-stu-id="48a7e-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="48a7e-107">Communications internes</span><span class="sxs-lookup"><span data-stu-id="48a7e-107">Internal communications</span></span>
    
- <span data-ttu-id="48a7e-108">Communications externes (communications qui incluent au moins un utilisateur en dehors de votre réseau interne)</span><span class="sxs-lookup"><span data-stu-id="48a7e-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="48a7e-109">Les stratégies d’archivage incluent la stratégie globale et, éventuellement, une ou plusieurs stratégies d’archivage de site et d’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="48a7e-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="48a7e-110">**Stratégie globale** La stratégie globale est créée par défaut dans tous les déploiements.</span><span class="sxs-lookup"><span data-stu-id="48a7e-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="48a7e-111">Vous pouvez modifier la stratégie globale mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="48a7e-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="48a7e-112">Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont réinitialisées.</span><span class="sxs-lookup"><span data-stu-id="48a7e-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="48a7e-113">**Stratégie de site (facultatif)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage de site, que vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un site unique.</span><span class="sxs-lookup"><span data-stu-id="48a7e-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="48a7e-114">Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans vos stratégies de site d’archivage.</span><span class="sxs-lookup"><span data-stu-id="48a7e-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="48a7e-115">Vous pouvez modifier ou supprimer les stratégies de site.</span><span class="sxs-lookup"><span data-stu-id="48a7e-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="48a7e-116">**Stratégie utilisateur (facultative)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage utilisateur, que vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un utilisateur ou un groupe d’utilisateurs spécifique.</span><span class="sxs-lookup"><span data-stu-id="48a7e-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="48a7e-117">Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et les groupes d’utilisateurs auxquels vous attribuez des stratégies d’archivage au niveau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48a7e-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="48a7e-118">Vous pouvez modifier ou supprimer les stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48a7e-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="48a7e-119">Les stratégies d’archivage s’appliquent uniquement aux utilisateurs sur Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="48a7e-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="48a7e-120">Si vous utilisez l’intégration Exchange pour stocker des données d’archivage dans Microsoft Exchange, les stratégies Exchange contrôlent l’archivage pour les utilisateurs d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="48a7e-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="48a7e-121">Pour activer l’archivage pour ces utilisateurs, la boîte aux lettres de l’utilisateur doit être placée en In-Place archive.</span><span class="sxs-lookup"><span data-stu-id="48a7e-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="48a7e-122">La page **Stratégie d’archivage** répertorie chaque stratégie d’archivage configurée pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="48a7e-122">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment.</span></span> <span data-ttu-id="48a7e-123">Il indique également le nom de la stratégie, l’étendue (globale, de site ou utilisateur) et les options d’archivage activées pour chaque stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="48a7e-123">It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy.</span></span> <span data-ttu-id="48a7e-124">Dans la page **Stratégie d’archivage,** vous avez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="48a7e-124">From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="48a7e-125">**Nouveau** Vous pouvez ajouter une ou plusieurs des stratégies d’archivage facultatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="48a7e-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="48a7e-126">Stratégie de site</span><span class="sxs-lookup"><span data-stu-id="48a7e-126">Site policy</span></span>
    
  - <span data-ttu-id="48a7e-127">Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="48a7e-127">User policy</span></span>
    
- <span data-ttu-id="48a7e-128">**Modifier** Vous pouvez modifier les options de n’importe quelle stratégie d’archivage répertoriée sur la page.</span><span class="sxs-lookup"><span data-stu-id="48a7e-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="48a7e-129">À l’aide de cette option, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="48a7e-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="48a7e-130">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’archivage d’une stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="48a7e-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="48a7e-131">**Sélectionner tout** Cette option sélectionne toutes les stratégies d’archivage de la liste.</span><span class="sxs-lookup"><span data-stu-id="48a7e-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="48a7e-132">**Supprimer** Cette option supprime toutes les stratégies d’archivage sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="48a7e-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="48a7e-133">**Action** Vous pouvez utiliser cette option pour activer ou désactiver rapidement l’archivage des communications internes ou externes dans n’importe quelle stratégie répertoriée sur la page, au lieu de modifier la stratégie.</span><span class="sxs-lookup"><span data-stu-id="48a7e-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="48a7e-134">Les options disponibles sous **Action** dépendent de l’option actuellement spécifiée dans la stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="48a7e-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="48a7e-135">Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="48a7e-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="48a7e-136">Les options sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="48a7e-136">Options include the following:</span></span>
    
  - <span data-ttu-id="48a7e-137">**Activer l’archivage des communications internes**</span><span class="sxs-lookup"><span data-stu-id="48a7e-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="48a7e-138">**Désactiver l’archivage des communications internes**</span><span class="sxs-lookup"><span data-stu-id="48a7e-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="48a7e-139">**Activer l’archivage des communications externes**</span><span class="sxs-lookup"><span data-stu-id="48a7e-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="48a7e-140">**Désactiver l’archivage des communications externes**</span><span class="sxs-lookup"><span data-stu-id="48a7e-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="48a7e-141">**Actualiser** Vous pouvez actualiser la page **Stratégie** d’archivage pour vérifier l’état des options de toutes les stratégies d’archivage.</span><span class="sxs-lookup"><span data-stu-id="48a7e-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="48a7e-142">Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), Deploy [archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and Manage [archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="48a7e-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

