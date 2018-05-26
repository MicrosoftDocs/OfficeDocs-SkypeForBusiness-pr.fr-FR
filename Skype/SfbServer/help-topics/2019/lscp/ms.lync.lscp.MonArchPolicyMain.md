---
title: Stratégie d’archivage
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Vous utilisez des stratégies d’archivage pour activer et désactiver l’archivage pour les utilisateurs hébergés sur Skype pour Business Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :'
ms.openlocfilehash: 6bdccd0f717314fb36a698ee8dd9d237a47d6bdd
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2018
---
# <a name="archiving-policy"></a><span data-ttu-id="ddf7a-104">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="ddf7a-104">Archiving Policy</span></span>
 
<span data-ttu-id="ddf7a-105">Vous utilisez des stratégies d’archivage pour activer et désactiver l’archivage pour les utilisateurs hébergés sur Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="ddf7a-106">Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :</span><span class="sxs-lookup"><span data-stu-id="ddf7a-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="ddf7a-107">Communications internes</span><span class="sxs-lookup"><span data-stu-id="ddf7a-107">Internal communications</span></span>
    
- <span data-ttu-id="ddf7a-108">Communications externes (communications qui incluent au moins un utilisateur situé en dehors de votre réseau interne)</span><span class="sxs-lookup"><span data-stu-id="ddf7a-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="ddf7a-109">Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies d’archivage de site et utilisateur :</span><span class="sxs-lookup"><span data-stu-id="ddf7a-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="ddf7a-110">**Stratégie globale** La stratégie globale est créée par défaut dans tous les déploiements.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="ddf7a-111">Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="ddf7a-112">Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="ddf7a-113">**Stratégie de site (facultatif)** Vous pouvez spécifier une ou plusieurs sites d’archivage stratégies, que chacun d'entre eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un seul site.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="ddf7a-114">Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans vos stratégies d’archivage de site.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="ddf7a-115">Vous pouvez modifier ou supprimer les stratégies de site.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="ddf7a-116">**Stratégie utilisateur (facultatif)** Vous pouvez spécifier des stratégies d’archivage utilisateur un ou plusieurs, que chacun d'entre eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un utilisateur spécifique ou un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="ddf7a-117">Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et les groupes d’utilisateurs auxquels vous attribuez des stratégies d’archivage de niveau utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="ddf7a-118">Vous pouvez modifier ou supprimer les stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ddf7a-119">Stratégies d’archivage s’appliquent uniquement aux utilisateurs hébergés sur Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="ddf7a-120">Si vous utilisez l’intégration d’Exchange pour stocker les données dans Microsoft Exchange, puis Exchange 2013 stratégies d’archivage contrôle l’archivage pour les utilisateurs hébergés sur Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="ddf7a-121">Pour activer l’archivage pour les utilisateurs, boîte aux lettres de l’utilisateur doit être placé sur le blocage sur Place.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="ddf7a-p107">La page **Stratégie d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou utilisateur) et les options d’archivage activées pour chaque stratégie d’archivage. La page **Stratégie d’archivage** propose les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ddf7a-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="ddf7a-125">**Nouveau** Vous pouvez ajouter une ou plusieurs des stratégies d’archivage facultatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="ddf7a-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="ddf7a-126">Stratégie de site</span><span class="sxs-lookup"><span data-stu-id="ddf7a-126">Site policy</span></span>
    
  - <span data-ttu-id="ddf7a-127">Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="ddf7a-127">User policy</span></span>
    
- <span data-ttu-id="ddf7a-128">**Modifier** Vous pouvez modifier les options d’une des stratégies d’archivage répertoriées sur la page.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="ddf7a-129">Utilisez cette option, vous pouvez procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ddf7a-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="ddf7a-130">**Afficher les détails** : cette option affiche une boîte de dialogue qui permet de modifier les options d’archivage pour une stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="ddf7a-131">**Sélectionner tout** : cette option sélectionne toutes les stratégies d’archivage répertoriées.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="ddf7a-132">**Supprimer** : cette option supprime toutes les stratégies d’archivage sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="ddf7a-133">**Action** Vous pouvez utiliser cette option pour activer ou désactiver l’archivage des communications internes ou externes dans toute stratégie répertorié dans la page, plutôt qu’une modification de la stratégie de rapidement.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="ddf7a-134">Les options disponibles sous **Action** dépendent de l’option est actuellement spécifiée dans la stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="ddf7a-135">Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="ddf7a-136">Les options sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ddf7a-136">Options include the following:</span></span>
    
  - <span data-ttu-id="ddf7a-137">**Activer l’archivage des communications internes**</span><span class="sxs-lookup"><span data-stu-id="ddf7a-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="ddf7a-138">**Désactiver l’archivage des communications internes**</span><span class="sxs-lookup"><span data-stu-id="ddf7a-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="ddf7a-139">**Activer l’archivage des communications externes**</span><span class="sxs-lookup"><span data-stu-id="ddf7a-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="ddf7a-140">**Désactiver l’archivage des communications externes**</span><span class="sxs-lookup"><span data-stu-id="ddf7a-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="ddf7a-141">**Actualiser** Vous pouvez actualiser la page **Stratégie d’archivage** pour vérifier le statut des options de toutes les stratégies d’archivage.</span><span class="sxs-lookup"><span data-stu-id="ddf7a-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="ddf7a-142">Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [planifier l’archivage dans Skype pour Business Server 2015](../../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server 2015](../../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour Entreprise 2015 Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ddf7a-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../../manage/archiving/archiving.md).</span></span>

