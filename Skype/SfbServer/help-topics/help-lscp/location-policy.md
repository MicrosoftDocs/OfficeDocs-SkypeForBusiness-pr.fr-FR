---
title: Stratégie d’emplacement
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: fa1ca0907d3316066e2ca6e1fcf8a1d09a9c315a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy"></a><span data-ttu-id="867c3-103">Stratégie d’emplacement</span><span class="sxs-lookup"><span data-stu-id="867c3-103">Location Policy</span></span>
 
<span data-ttu-id="867c3-104">Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.</span><span class="sxs-lookup"><span data-stu-id="867c3-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span> 
  
<span data-ttu-id="867c3-105">Les stratégies d’emplacement incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :</span><span class="sxs-lookup"><span data-stu-id="867c3-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="867c3-106">**Stratégie globale :** La stratégie globale est créée par défaut.</span><span class="sxs-lookup"><span data-stu-id="867c3-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="867c3-107">Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas le supprimer.</span><span class="sxs-lookup"><span data-stu-id="867c3-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="867c3-108">Si vous essayez de supprimer la stratégie globale, tous les paramètres sont réinitialisés aux valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="867c3-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="867c3-109">**Site de stratégies (facultatifs) :** Vous pouvez créer des stratégies d’emplacement site un ou plusieurs, chacun d’eux s’applique à un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="867c3-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="867c3-110">Les stratégies de site remplacent la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="867c3-110">Site policies override the global policy.</span></span>
    
- <span data-ttu-id="867c3-111">**Des stratégies d’utilisateur (facultatifs) :** Vous pouvez créer des stratégies d’emplacement utilisateur un ou plusieurs, chacun d’eux s’applique à un utilisateur spécifique ou un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="867c3-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="867c3-112">Les stratégies utilisateur remplacent la stratégie globale et les stratégies de site.</span><span class="sxs-lookup"><span data-stu-id="867c3-112">User policies override the global policy and site policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="867c3-113">Vous pouvez également attribuer des stratégies d’emplacement à des sites réseau, qui sont des groupes de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="867c3-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="867c3-114">Les stratégies d’emplacement attribuées aux sites réseau prévalent sur toutes les autres stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="867c3-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="867c3-115">Pour plus d’informations sur l’affectation des stratégies d’emplacement pour les sites de réseau à l’aide des applets de commande, voir [Ajouter une stratégie d’emplacement pour un site de RESEAU dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="867c3-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="867c3-116">Pour plus d’informations sur l’utilisation de Skype pour Business Server du Panneau de configuration pour affecter une stratégie d’emplacement sur un site de réseau, consultez [Configuration des Sites de réseau](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="867c3-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span> 
  
<span data-ttu-id="867c3-117">La page **Stratégie d’emplacement** affiche la liste de toutes les stratégies d’emplacement définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="867c3-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="867c3-118">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="867c3-118">Tasks you can perform</span></span>

<span data-ttu-id="867c3-119">Dans la page **Stratégie d’emplacement**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="867c3-119">You can perform the following tasks from the **Location Policy** page:</span></span>
  
- <span data-ttu-id="867c3-120">Création d’une stratégie d’emplacement de site ou d’une stratégie d’emplacement utilisateur</span><span class="sxs-lookup"><span data-stu-id="867c3-120">Create a new site location policy or user location policy</span></span>
    
- <span data-ttu-id="867c3-121">Modification de la stratégie globale, d’une stratégie de site ou d’une stratégie utilisateur existante</span><span class="sxs-lookup"><span data-stu-id="867c3-121">Change the global policy or an existing site policy or user policy</span></span>
    
- <span data-ttu-id="867c3-122">Suppression d’une stratégie de site ou d’une stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="867c3-122">Delete a site policy or user policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="867c3-123">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="867c3-123">UI Reference</span></span>

<span data-ttu-id="867c3-124">La liste ci-dessous décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="867c3-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="867c3-125">**Nouveau** Démarre une nouvelle stratégie d’emplacement de site ou emplacement utilisateur.</span><span class="sxs-lookup"><span data-stu-id="867c3-125">**New** Starts a new site location policy or user location policy.</span></span>
    
- <span data-ttu-id="867c3-126">**Modifier** Ouvre la stratégie de l’emplacement sélectionné pour le modifier, sélectionne toutes les stratégies d’emplacement dans la liste ou supprimer la stratégie du site sélectionné ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="867c3-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="867c3-127">Pour la stratégie globale, l’option **Supprimer** restaure les valeurs par défaut des paramètres.</span><span class="sxs-lookup"><span data-stu-id="867c3-127">For the global policy, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="867c3-128">**Actualiser** Actualise la liste des stratégies d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="867c3-128">**Refresh** Refreshes the list of location policies.</span></span>
    
<span data-ttu-id="867c3-129">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="867c3-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="867c3-130">**Nom** Identifie l’emplacement de stratégie.</span><span class="sxs-lookup"><span data-stu-id="867c3-130">**Name** Identifies the location policy.</span></span>
    
- <span data-ttu-id="867c3-131">**Champ d’application** Identifie l’étendue de la stratégie d’emplacement : global, site ou à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="867c3-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>
    
- <span data-ttu-id="867c3-132">**E9-1-1** Vérifiez si les utilisateurs affectés à cette stratégie d’emplacement sont activés pour E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="867c3-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>
    
- <span data-ttu-id="867c3-133">**Emplacement** Spécifie si les utilisateurs sont invités à entrer des informations d’emplacement lors de leur client inscrit avec Skype pour Business Server à un nouvel emplacement, et si elles voient une décharge de responsabilité si elles ignorer l’invite sans entrer les informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="867c3-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>
    
- <span data-ttu-id="867c3-134">**Utilisation de TLS** Spécifie l’utilisation du réseau (RTPC) public commuté qui est utilisée pour déterminer l’itinéraire de la voix utilisée pour acheminer les appels d’urgence à partir des clients à l’aide de ce profil.</span><span class="sxs-lookup"><span data-stu-id="867c3-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>
    
- <span data-ttu-id="867c3-135">**Nombre de E9-1-1** Spécifie le numéro qui est composé pour accéder à des services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="867c3-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>
    
- <span data-ttu-id="867c3-136">**Masque de E9-1-1** Spécifie un utilisateur compose un numéro qui est ensuite converti dans le nombre d’accès à distance en cas d’urgence.</span><span class="sxs-lookup"><span data-stu-id="867c3-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>
    
<span data-ttu-id="867c3-137">Pour plus d’informations sur les fonctionnalités de service d’urgence de Voix Entreprise de, consultez [vue d’ensemble de E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="867c3-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="867c3-138">Pour plus d’informations sur l’utilisation de stratégies d’emplacement, reportez-vous à la section [Configuration de la stratégie emplacement](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="867c3-138">For details about working with location policies, see [Configuring Location Policy](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>
  

