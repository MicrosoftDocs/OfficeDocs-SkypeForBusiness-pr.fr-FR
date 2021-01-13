---
title: Configuration de l’archivage
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Vous utilisez les configurations d’archivage pour contrôler les options d’archivage de votre déploiement Skype Entreprise Server, y compris l’activation et la désactivation des options suivantes :'
ms.openlocfilehash: 96a01579f43833017978fc6067b5a86f9e9951aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827004"
---
# <a name="archiving-configuration"></a><span data-ttu-id="9c704-103">Configuration de l’archivage</span><span class="sxs-lookup"><span data-stu-id="9c704-103">Archiving Configuration</span></span>
 
<span data-ttu-id="9c704-104">Vous utilisez les configurations d’archivage pour contrôler les options d’archivage de votre déploiement Skype Entreprise Server, y compris l’activation et la désactivation des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c704-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="9c704-105">Blocage des sessions de messagerie instantanée ou de conférence en cas d’échec de l’archivage</span><span class="sxs-lookup"><span data-stu-id="9c704-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="9c704-106">Intégration au stockage Exchange 2013, pour les utilisateurs d’Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="9c704-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="9c704-107">Purge des données archivées</span><span class="sxs-lookup"><span data-stu-id="9c704-107">Purging of archived data</span></span>
    
<span data-ttu-id="9c704-108">Les configurations d’archivage incluent la configuration globale et éventuellement une ou plusieurs configurations d’archivage de site ou de pool :</span><span class="sxs-lookup"><span data-stu-id="9c704-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="9c704-109">**Configuration globale** La configuration globale est créée par défaut dans tous les déploiements Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9c704-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="9c704-110">Vous pouvez modifier la configuration globale mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="9c704-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="9c704-111">Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont réinitialisées.</span><span class="sxs-lookup"><span data-stu-id="9c704-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="9c704-112">**Configuration du site (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage de site, que vous pouvez configurer pour contrôler les options d’archivage d’un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="9c704-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="9c704-113">La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage.</span><span class="sxs-lookup"><span data-stu-id="9c704-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="9c704-114">Vous pouvez modifier ou supprimer des configurations de site.</span><span class="sxs-lookup"><span data-stu-id="9c704-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="9c704-115">**Configuration du pool (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage de pool pour contrôler les options d’archivage d’un pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="9c704-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="9c704-116">Une configuration de pool supplante la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool.</span><span class="sxs-lookup"><span data-stu-id="9c704-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="9c704-117">Vous pouvez modifier ou supprimer les configurations de pool.</span><span class="sxs-lookup"><span data-stu-id="9c704-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9c704-118">Les configurations d’archivage s’appliquent aux utilisateurs stockés sur Skype Entreprise Server et, si vous utilisez Exchange pour stocker des données d’archivage dans Microsoft Exchange, aux utilisateurs qui sont stockés sur Exchange 2013, mais sont implémentés légèrement différemment pour les utilisateurs d’Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="9c704-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="9c704-119">Ces différences sont décrites dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="9c704-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="9c704-p105">La page **Configuration d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou de pool) et les options d’archivage activées pour chaque configuration d’archivage. La page **Configuration d’archivage** propose les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c704-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="9c704-123">**Nouveau** Vous pouvez ajouter une ou plusieurs des configurations d’archivage facultatives suivantes.</span><span class="sxs-lookup"><span data-stu-id="9c704-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="9c704-124">Configuration du site</span><span class="sxs-lookup"><span data-stu-id="9c704-124">Site configuration</span></span>
    
  - <span data-ttu-id="9c704-125">Configuration du pool</span><span class="sxs-lookup"><span data-stu-id="9c704-125">Pool configuration</span></span>
    
- <span data-ttu-id="9c704-126">**Modifier** Vous pouvez modifier les options de toutes les configurations d’archivage répertoriées sur la page.</span><span class="sxs-lookup"><span data-stu-id="9c704-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="9c704-127">À l’aide de cette option, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c704-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9c704-128">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’archivage pour la configuration d’archivage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9c704-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="9c704-129">Vous ne pouvez afficher les détails que pour une configuration d’archivage à la fois.</span><span class="sxs-lookup"><span data-stu-id="9c704-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="9c704-130">**Sélectionner tout** Cette option sélectionne toutes les configurations d’archivage de la liste.</span><span class="sxs-lookup"><span data-stu-id="9c704-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="9c704-131">**Supprimer** Cette option supprime toutes les configurations d’archivage sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="9c704-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="9c704-132">**Action** Vous pouvez utiliser cette option pour activer ou désactiver rapidement l’archivage des sessions de messagerie instantanée ou des sessions de conférence web dans n’importe quelle configuration répertoriée sur la page, au lieu de modifier la configuration.</span><span class="sxs-lookup"><span data-stu-id="9c704-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="9c704-133">Les options disponibles sous **Action** dépendent de l’option actuellement spécifiée dans la configuration de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="9c704-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="9c704-134">Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la configuration de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="9c704-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="9c704-135">Les options sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c704-135">Options include the following:</span></span>
    
  - <span data-ttu-id="9c704-136">**Archiver les sessions de messagerie instantanée**</span><span class="sxs-lookup"><span data-stu-id="9c704-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="9c704-137">**Archiver les sessions de messagerie instantanée et de conférence web**</span><span class="sxs-lookup"><span data-stu-id="9c704-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="9c704-138">**Désactiver l’archivage**</span><span class="sxs-lookup"><span data-stu-id="9c704-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="9c704-139">**Actualiser** Vous pouvez actualiser la page **Configuration de l’archivage** pour vérifier l’état des options de toutes les configurations d’archivage.</span><span class="sxs-lookup"><span data-stu-id="9c704-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="9c704-140">Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="9c704-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

