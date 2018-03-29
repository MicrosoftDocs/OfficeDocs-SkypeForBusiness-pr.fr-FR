---
title: Configuration de la réunion
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Meeting configuration settings define the type of conferences (also calledmeetings) that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. Ces paramètres ne concernent que les réunions planifiées. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.
ms.openlocfilehash: 1318f2eee75809e736ce04af01eb2f2563b86f0f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="meeting-configuration"></a><span data-ttu-id="bde6b-105">Configuration de la réunion</span><span class="sxs-lookup"><span data-stu-id="bde6b-105">Meeting Configuration</span></span>
 
<span data-ttu-id="bde6b-p102">Les paramètres de configuration de réunion définissent le type de conférence (également appelées « réunions ») que les utilisateurs peuvent créer. Ils contrôlent également la façon dont les utilisateurs anonymes et les utilisateurs de conférences rendez-vous peuvent participer aux conférences et s’ils peuvent y participer. Ces paramètres concernent uniquement les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.</span><span class="sxs-lookup"><span data-stu-id="bde6b-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span> 
  
<span data-ttu-id="bde6b-109">Les configurations de réunion s’appliquent au niveau du site, au niveau du pool ou au niveau global :</span><span class="sxs-lookup"><span data-stu-id="bde6b-109">Meeting configurations apply on the global, site, or pool level:</span></span>
  
- <span data-ttu-id="bde6b-110">**Global meeting configuration:** The global meeting configuration is created by default.</span><span class="sxs-lookup"><span data-stu-id="bde6b-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="bde6b-111">You can edit the global meeting configuration, but you cannot delete it.</span><span class="sxs-lookup"><span data-stu-id="bde6b-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="bde6b-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span><span class="sxs-lookup"><span data-stu-id="bde6b-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="bde6b-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span><span class="sxs-lookup"><span data-stu-id="bde6b-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="bde6b-114">Site configurations override the global configuration.</span><span class="sxs-lookup"><span data-stu-id="bde6b-114">Site configurations override the global configuration.</span></span>
    
- <span data-ttu-id="bde6b-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span><span class="sxs-lookup"><span data-stu-id="bde6b-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="bde6b-116">Pool configurations override the global configuration and site configurations.</span><span class="sxs-lookup"><span data-stu-id="bde6b-116">Pool configurations override the global configuration and site configurations.</span></span>
    
<span data-ttu-id="bde6b-117">La page **Configuration de la réunion** affiche la liste de toutes les configurations de réunion définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="bde6b-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="bde6b-118">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="bde6b-118">Tasks you can perform</span></span>

<span data-ttu-id="bde6b-119">Dans la page **Configuration de la réunion**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="bde6b-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>
  
- <span data-ttu-id="bde6b-120">Création d’une configuration de réunion de site ou configuration de réunion de pool</span><span class="sxs-lookup"><span data-stu-id="bde6b-120">Create a new site meeting configuration or pool meeting configuration</span></span>
    
- <span data-ttu-id="bde6b-121">Modification de la configuration globale ou d’une configuration de site ou de pool existante</span><span class="sxs-lookup"><span data-stu-id="bde6b-121">Change the global configuration or an existing site configuration or pool configuration</span></span>
    
- <span data-ttu-id="bde6b-122">Suppression d’une configuration de site ou de pool</span><span class="sxs-lookup"><span data-stu-id="bde6b-122">Delete a site configuration or pool configuration</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="bde6b-123">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="bde6b-123">UI Reference</span></span>

<span data-ttu-id="bde6b-124">La liste ci-dessous décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="bde6b-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="bde6b-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span><span class="sxs-lookup"><span data-stu-id="bde6b-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>
    
- <span data-ttu-id="bde6b-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span><span class="sxs-lookup"><span data-stu-id="bde6b-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bde6b-127">Pour la configuration de réunion globale, la commande **Supprimer** restaure les valeurs par défaut des paramètres.</span><span class="sxs-lookup"><span data-stu-id="bde6b-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="bde6b-128">**Refresh** Refreshes the list of meeting configurations.</span><span class="sxs-lookup"><span data-stu-id="bde6b-128">**Refresh** Refreshes the list of meeting configurations.</span></span>
    
<span data-ttu-id="bde6b-129">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="bde6b-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="bde6b-130">**Name** Identifies the meeting configuration.</span><span class="sxs-lookup"><span data-stu-id="bde6b-130">**Name** Identifies the meeting configuration.</span></span>
    
- <span data-ttu-id="bde6b-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span><span class="sxs-lookup"><span data-stu-id="bde6b-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>
    
<span data-ttu-id="bde6b-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="bde6b-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>
  

