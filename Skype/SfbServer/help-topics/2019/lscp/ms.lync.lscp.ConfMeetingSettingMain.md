---
title: Configuration de la réunion
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: Paramètres de configuration de réunion définissent le type de conférences (également calledmeetings) que les utilisateurs peuvent créer et contrôler comment (ou si) les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent rejoindre ces conférences. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.
ms.openlocfilehash: 97583667bbd9dbb0c99b743a2748adf21b4f4afc
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258486"
---
# <a name="meeting-configuration"></a><span data-ttu-id="92cb0-105">Configuration de la réunion</span><span class="sxs-lookup"><span data-stu-id="92cb0-105">Meeting Configuration</span></span>

<span data-ttu-id="92cb0-p102">Les paramètres de configuration de réunion définissent le type de conférence (également appelées « réunions ») que les utilisateurs peuvent créer. Ils contrôlent également la façon dont les utilisateurs anonymes et les utilisateurs de conférences rendez-vous peuvent participer aux conférences et s’ils peuvent y participer. Ces paramètres concernent uniquement les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.</span><span class="sxs-lookup"><span data-stu-id="92cb0-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="92cb0-109">Les configurations de réunion s’appliquent au niveau du site, au niveau du pool ou au niveau global :</span><span class="sxs-lookup"><span data-stu-id="92cb0-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="92cb0-110">**Configuration de réunion globale :** La configuration de réunion globale est créée par défaut.</span><span class="sxs-lookup"><span data-stu-id="92cb0-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="92cb0-111">Vous pouvez modifier la configuration de réunion globale, mais vous ne pouvez pas le supprimer.</span><span class="sxs-lookup"><span data-stu-id="92cb0-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="92cb0-112">Si vous essayez de supprimer la configuration de réunion globale, tous les paramètres sont réinitialisées sur les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="92cb0-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="92cb0-113">**Configuration de réunion de site (facultative) :** Vous pouvez en créer un ou plusieurs sites configurations de réunion, chacun d'entre eux s’applique à un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="92cb0-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="92cb0-114">Configurations de site remplacent la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="92cb0-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="92cb0-115">**Configuration de réunion de pool (facultatif) :** Vous pouvez en créer un ou plusieurs pool configurations de réunion, chacun d'entre eux s’applique à un pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="92cb0-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="92cb0-116">Configurations de pool remplacent la configuration globale et les configurations de site.</span><span class="sxs-lookup"><span data-stu-id="92cb0-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="92cb0-117">La page **Configuration de la réunion** affiche la liste de toutes les configurations de réunion définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="92cb0-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="92cb0-118">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="92cb0-118">Tasks you can perform</span></span>

<span data-ttu-id="92cb0-119">Dans la page **Configuration de la réunion**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="92cb0-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="92cb0-120">Création d’une configuration de réunion de site ou configuration de réunion de pool</span><span class="sxs-lookup"><span data-stu-id="92cb0-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="92cb0-121">Modification de la configuration globale ou d’une configuration de site ou de pool existante</span><span class="sxs-lookup"><span data-stu-id="92cb0-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="92cb0-122">Suppression d’une configuration de site ou de pool</span><span class="sxs-lookup"><span data-stu-id="92cb0-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="92cb0-123">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="92cb0-123">UI Reference</span></span>

<span data-ttu-id="92cb0-124">La liste ci-dessous décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="92cb0-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="92cb0-125">**Nouveau** Démarre une nouvelle configuration de réunion de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="92cb0-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="92cb0-126">**Modifier** Ouvre la configuration de réunion sélectionnée pour le modifier, sélectionne toutes les configurations de réunion dans la liste ou supprime la configuration du site sélectionné ou la configuration du pool.</span><span class="sxs-lookup"><span data-stu-id="92cb0-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="92cb0-127">Pour la configuration de réunion globale, la commande **Supprimer** restaure les valeurs par défaut des paramètres.</span><span class="sxs-lookup"><span data-stu-id="92cb0-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="92cb0-128">**Actualiser** Actualise la liste des configurations de réunion.</span><span class="sxs-lookup"><span data-stu-id="92cb0-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="92cb0-129">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="92cb0-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="92cb0-130">**Nom** Identifie la configuration de la réunion.</span><span class="sxs-lookup"><span data-stu-id="92cb0-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="92cb0-131">**Étendue** Identifie l’étendue de la configuration de réunion : globale, site ou pool.</span><span class="sxs-lookup"><span data-stu-id="92cb0-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="92cb0-132">Pour plus d’informations sur l’utilisation des configurations de réunion, voir [créer un ou modifier une Collection de paramètres de Configuration réunion](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="92cb0-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>


