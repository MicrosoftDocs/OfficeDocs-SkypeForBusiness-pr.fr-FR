---
title: Configuration de l’archivage
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous utilisez des configurations d’archivage au contrôle options d’archivage pour votre Skype pour le déploiement de serveur d’entreprise, y compris l’activation et désactivation des options suivantes :'
ms.openlocfilehash: 3537ec152965f3245ca11358bab736814baada8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891179"
---
# <a name="archiving-configuration"></a><span data-ttu-id="306c6-103">Configuration de l’archivage</span><span class="sxs-lookup"><span data-stu-id="306c6-103">Archiving Configuration</span></span>
 
<span data-ttu-id="306c6-104">Vous utilisez des configurations d’archivage au contrôle options d’archivage pour votre Skype pour le déploiement de serveur d’entreprise, y compris l’activation et désactivation des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="306c6-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="306c6-105">Blocage des sessions de messagerie instantanée ou de conférence en cas d’échec de l’archivage</span><span class="sxs-lookup"><span data-stu-id="306c6-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="306c6-106">Intégration avec le stockage Exchange, pour les utilisateurs hébergés sur Exchange</span><span class="sxs-lookup"><span data-stu-id="306c6-106">Integration with Exchange storage, for users homed on Exchange</span></span>
    
- <span data-ttu-id="306c6-107">Purge des données archivées</span><span class="sxs-lookup"><span data-stu-id="306c6-107">Purging of archived data</span></span>
    
<span data-ttu-id="306c6-108">Les configurations d’archivage incluent la configuration globale, ainsi, éventuellement, qu’une ou plusieurs configurations d’archivage de site ou de pool :</span><span class="sxs-lookup"><span data-stu-id="306c6-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="306c6-109">**Configuration globale** La configuration globale créée par défaut dans tous les Skype pour les déploiements de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="306c6-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="306c6-110">Vous pouvez modifier la configuration globale, mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="306c6-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="306c6-111">Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="306c6-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="306c6-112">**Configuration du site (facultative)** Vous pouvez spécifier une ou plusieurs sites d’archivage configurations, que chacun d'entre eux vous pouvez configurer pour contrôler l’archivage des options pour un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="306c6-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="306c6-113">La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage.</span><span class="sxs-lookup"><span data-stu-id="306c6-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="306c6-114">Vous pouvez modifier ou supprimer les configurations de site.</span><span class="sxs-lookup"><span data-stu-id="306c6-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="306c6-115">**Configuration du pool (facultative)** Vous pouvez spécifier un ou plusieurs pool configuration d’archivage, au contrôle options d’archivage d’un pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="306c6-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="306c6-116">Une configuration de pool remplace la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool.</span><span class="sxs-lookup"><span data-stu-id="306c6-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="306c6-117">Vous pouvez modifier ou supprimer les configurations de pool.</span><span class="sxs-lookup"><span data-stu-id="306c6-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="306c6-118">Les configurations d’archivage s’appliquent aux utilisateurs hébergés sur Skype pour Business Server et que, si vous utilisez Exchange pour stocker les données d’archivage dans Microsoft Exchange, les utilisateurs hébergés sur Exchange mais sont implémentées différemment pour les utilisateurs hébergés sur Exchange.</span><span class="sxs-lookup"><span data-stu-id="306c6-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange but are implemented slightly differently for users homed on Exchange.</span></span> <span data-ttu-id="306c6-119">Ces différences sont décrites dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="306c6-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="306c6-p105">La page **Configuration d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou de pool) et les options d’archivage activées pour chaque configuration d’archivage. La page **Configuration d’archivage** propose les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="306c6-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="306c6-123">**Nouveau** Vous pouvez ajouter une ou plusieurs de chacune des configurations d’archivage facultatives suivantes.</span><span class="sxs-lookup"><span data-stu-id="306c6-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="306c6-124">Configuration du site</span><span class="sxs-lookup"><span data-stu-id="306c6-124">Site configuration</span></span>
    
  - <span data-ttu-id="306c6-125">Configuration du pool</span><span class="sxs-lookup"><span data-stu-id="306c6-125">Pool configuration</span></span>
    
- <span data-ttu-id="306c6-126">**Modifier** Vous pouvez modifier les options d’une des configurations d’archivage répertoriées dans la page.</span><span class="sxs-lookup"><span data-stu-id="306c6-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="306c6-127">Utilisez cette option, vous pouvez procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="306c6-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="306c6-128">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’archivage pour la configuration d’archivage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="306c6-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="306c6-129">Vous pouvez uniquement afficher les détails pour une configuration d’archivage à la fois.</span><span class="sxs-lookup"><span data-stu-id="306c6-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="306c6-130">**Sélectionner tout** Cette option sélectionne toutes les configurations d’archivage dans la liste.</span><span class="sxs-lookup"><span data-stu-id="306c6-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="306c6-131">**Supprimer** Cette option supprime toutes les configurations d’archivage sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="306c6-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="306c6-132">**Action** Vous pouvez utiliser cette option pour activer ou désactiver l’archivage des sessions de messagerie instantanée ou des sessions de conférence web dans n’importe quelle configuration répertoriés dans la page, plutôt qu’une modification de la configuration de rapidement.</span><span class="sxs-lookup"><span data-stu-id="306c6-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="306c6-133">Les options disponibles sous **Action** dépendent de l’option est actuellement spécifiée dans la configuration d’archivage.</span><span class="sxs-lookup"><span data-stu-id="306c6-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="306c6-134">Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la configuration d’archivage.</span><span class="sxs-lookup"><span data-stu-id="306c6-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="306c6-135">Les options sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="306c6-135">Options include the following:</span></span>
    
  - <span data-ttu-id="306c6-136">**Archiver les sessions de messagerie instantanée**</span><span class="sxs-lookup"><span data-stu-id="306c6-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="306c6-137">**Archiver les sessions de messagerie instantanée et de conférence web**</span><span class="sxs-lookup"><span data-stu-id="306c6-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="306c6-138">**Désactiver l’archivage**</span><span class="sxs-lookup"><span data-stu-id="306c6-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="306c6-139">**Actualiser** Vous pouvez actualiser la page **Configuration de l’archivage** pour vérifier le statut des options de toutes les configurations d’archivage.</span><span class="sxs-lookup"><span data-stu-id="306c6-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="306c6-140">Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [planifier l’archivage dans Skype pour Business Server](../../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour les entreprises Serveur](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="306c6-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

