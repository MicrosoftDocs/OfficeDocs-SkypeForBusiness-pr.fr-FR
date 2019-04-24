---
title: Stratégie d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous utilisez des stratégies d’archivage pour activer et désactiver l’archivage pour les utilisateurs hébergés sur Skype pour Business Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :'
ms.openlocfilehash: 4af5b5d8eb0f59d6899a73b7de6516d665fe041e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215459"
---
# <a name="archiving-policy"></a><span data-ttu-id="9a507-104">Stratégie d’archivage</span><span class="sxs-lookup"><span data-stu-id="9a507-104">Archiving Policy</span></span>
 
<span data-ttu-id="9a507-105">Vous utilisez des stratégies d’archivage pour activer et désactiver l’archivage pour les utilisateurs hébergés sur Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9a507-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="9a507-106">Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :</span><span class="sxs-lookup"><span data-stu-id="9a507-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="9a507-107">Communications internes</span><span class="sxs-lookup"><span data-stu-id="9a507-107">Internal communications</span></span>
    
- <span data-ttu-id="9a507-108">Communications externes (communications qui incluent au moins un utilisateur situé en dehors de votre réseau interne)</span><span class="sxs-lookup"><span data-stu-id="9a507-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="9a507-109">Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies d’archivage de site et utilisateur :</span><span class="sxs-lookup"><span data-stu-id="9a507-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="9a507-110">**Stratégie globale** La stratégie globale est créée par défaut dans tous les déploiements.</span><span class="sxs-lookup"><span data-stu-id="9a507-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="9a507-111">Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="9a507-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="9a507-112">Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="9a507-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="9a507-113">**Stratégie de site (facultatif)** Vous pouvez spécifier une ou plusieurs sites d’archivage stratégies, que chacun d'entre eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un seul site.</span><span class="sxs-lookup"><span data-stu-id="9a507-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="9a507-114">Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans vos stratégies d’archivage de site.</span><span class="sxs-lookup"><span data-stu-id="9a507-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="9a507-115">Vous pouvez modifier ou supprimer les stratégies de site.</span><span class="sxs-lookup"><span data-stu-id="9a507-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="9a507-116">**Stratégie utilisateur (facultatif)** Vous pouvez spécifier des stratégies d’archivage utilisateur un ou plusieurs, que chacun d'entre eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un utilisateur spécifique ou un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9a507-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="9a507-117">Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et les groupes d’utilisateurs auxquels vous attribuez des stratégies d’archivage de niveau utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a507-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="9a507-118">Vous pouvez modifier ou supprimer les stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a507-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9a507-119">Stratégies d’archivage s’appliquent uniquement aux utilisateurs hébergés sur Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9a507-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="9a507-120">Si vous utilisez l’intégration d’Exchange pour stocker les données d’archivage dans Microsoft Exchange, Exchange l’archivage de contrôle des stratégies pour les utilisateurs hébergés sur Exchange.</span><span class="sxs-lookup"><span data-stu-id="9a507-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="9a507-121">Pour activer l’archivage pour les utilisateurs, boîte aux lettres de l’utilisateur doit être placé sur le blocage sur Place.</span><span class="sxs-lookup"><span data-stu-id="9a507-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="9a507-p107">La page **Stratégie d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou utilisateur) et les options d’archivage activées pour chaque stratégie d’archivage. La page **Stratégie d’archivage** propose les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a507-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="9a507-125">**Nouveau** Vous pouvez ajouter une ou plusieurs des stratégies d’archivage facultatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a507-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="9a507-126">Stratégie de site</span><span class="sxs-lookup"><span data-stu-id="9a507-126">Site policy</span></span>
    
  - <span data-ttu-id="9a507-127">Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="9a507-127">User policy</span></span>
    
- <span data-ttu-id="9a507-128">**Modifier** Vous pouvez modifier les options d’une des stratégies d’archivage répertoriées sur la page.</span><span class="sxs-lookup"><span data-stu-id="9a507-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="9a507-129">Utilisez cette option, vous pouvez procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9a507-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9a507-130">**Afficher les détails** : cette option affiche une boîte de dialogue qui permet de modifier les options d’archivage pour une stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="9a507-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="9a507-131">**Sélectionner tout** : cette option sélectionne toutes les stratégies d’archivage répertoriées.</span><span class="sxs-lookup"><span data-stu-id="9a507-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="9a507-132">**Supprimer** : cette option supprime toutes les stratégies d’archivage sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="9a507-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="9a507-133">**Action** Vous pouvez utiliser cette option pour activer ou désactiver l’archivage des communications internes ou externes dans toute stratégie répertorié dans la page, plutôt qu’une modification de la stratégie de rapidement.</span><span class="sxs-lookup"><span data-stu-id="9a507-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="9a507-134">Les options disponibles sous **Action** dépendent de l’option est actuellement spécifiée dans la stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="9a507-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="9a507-135">Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="9a507-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="9a507-136">Les options sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a507-136">Options include the following:</span></span>
    
  - <span data-ttu-id="9a507-137">**Activer l’archivage des communications internes**</span><span class="sxs-lookup"><span data-stu-id="9a507-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9a507-138">**Désactiver l’archivage des communications internes**</span><span class="sxs-lookup"><span data-stu-id="9a507-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9a507-139">**Activer l’archivage des communications externes**</span><span class="sxs-lookup"><span data-stu-id="9a507-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="9a507-140">**Désactiver l’archivage des communications externes**</span><span class="sxs-lookup"><span data-stu-id="9a507-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="9a507-141">**Actualiser** Vous pouvez actualiser la page **Stratégie d’archivage** pour vérifier le statut des options de toutes les stratégies d’archivage.</span><span class="sxs-lookup"><span data-stu-id="9a507-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="9a507-142">Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [planifier l’archivage dans Skype pour Business Server](../../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour les entreprises Serveur](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="9a507-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

