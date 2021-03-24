---
title: Configuration de la réunion
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: Les paramètres de configuration de réunion définissent le type de conférences (également appelées « événements de réunion » ) que les utilisateurs peuvent créer, et contrôlent comment (ou si) les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent participer à ces conférences. Ces paramètres s’appliquent uniquement aux réunions planifiées. Elles ne s’appliquent pas aux réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans le client.
ms.openlocfilehash: 053378ef694a66413f11760be5f449cd21e6b764
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095968"
---
# <a name="meeting-configuration"></a><span data-ttu-id="12987-105">Configuration de la réunion</span><span class="sxs-lookup"><span data-stu-id="12987-105">Meeting Configuration</span></span>

<span data-ttu-id="12987-106">Les paramètres de configuration de réunion définissent le type de conférences (également appelées « réunions ») que les utilisateurs peuvent créer et contrôlent comment (ou si) les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent participer à ces conférences.</span><span class="sxs-lookup"><span data-stu-id="12987-106">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences.</span></span> <span data-ttu-id="12987-107">Ces paramètres s’appliquent uniquement aux réunions planifiées.</span><span class="sxs-lookup"><span data-stu-id="12987-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="12987-108">Elles ne s’appliquent pas aux réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans le client.</span><span class="sxs-lookup"><span data-stu-id="12987-108">They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="12987-109">Les configurations de réunion s’appliquent au niveau du site, au niveau du pool ou au niveau global :</span><span class="sxs-lookup"><span data-stu-id="12987-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="12987-110">**Configuration de réunion globale :** La configuration de réunion globale est créée par défaut.</span><span class="sxs-lookup"><span data-stu-id="12987-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="12987-111">Vous pouvez la modifier mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="12987-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="12987-112">Si vous essayez de la supprimer, toutes les valeurs par défaut des paramètres sont rétablies.</span><span class="sxs-lookup"><span data-stu-id="12987-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="12987-113">**Configuration de réunion de site (facultative) :** Vous pouvez créer une ou plusieurs configurations de réunion de site, chacune s’applique à un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="12987-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="12987-114">Les configurations de site supplantent la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="12987-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="12987-115">**Configuration de réunion de pool (facultative) :** Vous pouvez créer une ou plusieurs configurations de réunion de pool, chacune s’applique à un pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="12987-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="12987-116">Les configurations de pool supplantent la configuration globale et les configurations de site.</span><span class="sxs-lookup"><span data-stu-id="12987-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="12987-117">La page **Configuration de la réunion** affiche la liste de toutes les configurations de réunion définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="12987-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="12987-118">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="12987-118">Tasks you can perform</span></span>

<span data-ttu-id="12987-119">Vous pouvez effectuer les tâches suivantes dans la page **Configuration de la réunion** :</span><span class="sxs-lookup"><span data-stu-id="12987-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="12987-120">Créer une nouvelle configuration de réunion de site ou configuration de réunion de pool</span><span class="sxs-lookup"><span data-stu-id="12987-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="12987-121">Modifier la configuration globale ou une configuration de site ou de pool existante</span><span class="sxs-lookup"><span data-stu-id="12987-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="12987-122">Supprimer une configuration de site ou de pool</span><span class="sxs-lookup"><span data-stu-id="12987-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="12987-123">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="12987-123">UI Reference</span></span>

<span data-ttu-id="12987-124">La liste suivante décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="12987-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="12987-125">**Nouveau** Démarre une nouvelle configuration de réunion de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="12987-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="12987-126">**Modifier** Ouvre la configuration de réunion sélectionnée pour la modifier, sélectionne toutes les configurations de réunion dans la liste ou supprime la configuration de site ou de pool sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="12987-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="12987-127">Pour la configuration de réunion globale, la commande **Supprimer** rétablit les valeurs par défaut des paramètres.</span><span class="sxs-lookup"><span data-stu-id="12987-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="12987-128">**Actualiser** Actualise la liste des configurations de réunion.</span><span class="sxs-lookup"><span data-stu-id="12987-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="12987-129">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="12987-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="12987-130">**Nom** Identifie la configuration de la réunion.</span><span class="sxs-lookup"><span data-stu-id="12987-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="12987-131">**Étendue** Identifie l’étendue de la configuration de réunion : globale, de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="12987-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="12987-132">Pour plus d’informations sur l’utilisation des configurations de réunion, voir [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="12987-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span>