---
title: Stratégie d’emplacement
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: bb7a63e63864b3d342d37fd62b26f806434644b7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824784"
---
# <a name="location-policy"></a><span data-ttu-id="89d57-103">Stratégie d’emplacement</span><span class="sxs-lookup"><span data-stu-id="89d57-103">Location Policy</span></span>

<span data-ttu-id="89d57-104">Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.</span><span class="sxs-lookup"><span data-stu-id="89d57-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="89d57-105">Les stratégies d’emplacement incluent la stratégie globale et, éventuellement, une ou plusieurs stratégies de site et d’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="89d57-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="89d57-106">**Stratégie globale :** La stratégie globale est créée par défaut.</span><span class="sxs-lookup"><span data-stu-id="89d57-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="89d57-107">Vous pouvez modifier la stratégie globale mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="89d57-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="89d57-108">Si vous essayez de supprimer la stratégie globale, toutes les valeurs par défaut des paramètres sont réinitialisées.</span><span class="sxs-lookup"><span data-stu-id="89d57-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="89d57-109">**Stratégies de site (facultatives) :** Vous pouvez créer une ou plusieurs stratégies d’emplacement de site, chacune s’applique à un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="89d57-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="89d57-110">Les stratégies de site remplacent la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="89d57-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="89d57-111">**Stratégies utilisateur (facultatives) :** Vous pouvez créer une ou plusieurs stratégies d’emplacement utilisateur, chacune s’applique à un utilisateur ou à un groupe d’utilisateurs spécifique.</span><span class="sxs-lookup"><span data-stu-id="89d57-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="89d57-112">Les stratégies utilisateur remplacent la stratégie globale et les stratégies de site.</span><span class="sxs-lookup"><span data-stu-id="89d57-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="89d57-113">Vous pouvez également affecter des stratégies d’emplacement à des sites réseau, qui sont des groupes de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="89d57-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="89d57-114">Les stratégies d’emplacement attribuées aux sites réseau prévalent sur toutes les autres stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="89d57-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="89d57-115">Pour plus d’informations sur l’attribution de stratégies d’emplacement à des sites réseau à l’aide d’cmdlets, voir Ajouter une stratégie d’emplacement à un site réseau [dans Skype Entreprise Server.](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)</span><span class="sxs-lookup"><span data-stu-id="89d57-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="89d57-116">Pour plus d’informations sur l’utilisation du Panneau de configuration de Skype Entreprise Server pour affecter une stratégie d’emplacement à un site réseau, voir [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="89d57-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="89d57-117">La page **Stratégie d’emplacement** affiche la liste de toutes les stratégies d’emplacement définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="89d57-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="89d57-118">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="89d57-118">Tasks you can perform</span></span>

<span data-ttu-id="89d57-119">Vous pouvez effectuer les tâches suivantes à partir de la page **Stratégie d’emplacement** :</span><span class="sxs-lookup"><span data-stu-id="89d57-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="89d57-120">Créer une stratégie d’emplacement de site ou une stratégie d’emplacement utilisateur</span><span class="sxs-lookup"><span data-stu-id="89d57-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="89d57-121">Modifier la stratégie globale ou une stratégie de site ou stratégie utilisateur existante</span><span class="sxs-lookup"><span data-stu-id="89d57-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="89d57-122">Supprimer une stratégie de site ou une stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="89d57-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="89d57-123">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="89d57-123">UI Reference</span></span>

<span data-ttu-id="89d57-124">La liste suivante décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="89d57-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="89d57-125">**Nouveau** Démarre une nouvelle stratégie d’emplacement de site ou une nouvelle stratégie d’emplacement utilisateur.</span><span class="sxs-lookup"><span data-stu-id="89d57-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="89d57-126">**Modifier** Ouvre la stratégie d’emplacement sélectionnée pour la modifier, sélectionne toutes les stratégies d’emplacement dans la liste ou supprime la stratégie de site ou la stratégie utilisateur sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89d57-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="89d57-127">Pour la stratégie globale, **Supprimer** rétablit les valeurs par défaut des paramètres.</span><span class="sxs-lookup"><span data-stu-id="89d57-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="89d57-128">**Actualiser** Actualisation de la liste des stratégies d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="89d57-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="89d57-129">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="89d57-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="89d57-130">**Nom** Identifie la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="89d57-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="89d57-131">**Étendue** Identifie l’étendue de la stratégie d’emplacement : globale, de site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="89d57-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="89d57-132">**E9-1-1** Vérifié si les utilisateurs affectés à cette stratégie d’emplacement sont activés pour E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="89d57-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="89d57-133">**Emplacement** Spécifie si les utilisateurs sont invités à entrer des informations d’emplacement lorsque leur client s’inscrit auprès de Skype Entreprise Server à un nouvel emplacement, et s’ils voient une clause d’exclusion de responsabilité s’ils font disparaître l’invite sans entrer d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="89d57-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="89d57-134">**Utilisation PSTN** Spécifie l’utilisation du réseau téléphonique commuté (PSTN) utilisée pour déterminer l’itinéraire des communications vocales utilisé pour router les appels d’urgence des clients à l’aide de ce profil.</span><span class="sxs-lookup"><span data-stu-id="89d57-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="89d57-135">**Numéro E9-1-1** Spécifie le numéro composé pour joindre les services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="89d57-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="89d57-136">**Masque E9-1-1** Spécifie un numéro qu’un utilisateur compose puis converti en numéro de numéro d’urgence.</span><span class="sxs-lookup"><span data-stu-id="89d57-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="89d57-137">Pour plus d’informations Voix Entreprise fonctionnalités des services d’urgence, voir Vue d’ensemble du [service E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="89d57-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="89d57-138">Pour plus d’informations sur l’utilisation des stratégies d’emplacement, voir [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="89d57-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


