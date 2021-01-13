---
title: Parcage d’appel
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Lorsqu’un appel est paré, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu’à ce que quelqu’un le récupère ou qu’il n’sorte pas. Vous devez configurer un tableau avec les plages de numéros de poste que vous réservez pour les appels par parcés. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est assigné). Chaque pool qui exécute l’application de parcage d’appel peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.
ms.openlocfilehash: 679e13cdeb6ef6cf614f5703f5711e86fa1c8c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812164"
---
# <a name="call-park"></a><span data-ttu-id="4612a-106">Parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="4612a-106">Call Park</span></span>

<span data-ttu-id="4612a-107">Lorsqu’un appel est paré, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu’à ce que quelqu’un le récupère ou qu’il n’sorte pas. Vous devez configurer un tableau avec les plages de numéros de poste que vous réservez pour les appels par parcés.</span><span class="sxs-lookup"><span data-stu-id="4612a-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="4612a-108">Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est assigné).</span><span class="sxs-lookup"><span data-stu-id="4612a-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="4612a-109">Chaque pool qui exécute l’application de parcage d’appel peut avoir une ou plusieurs plages d’extensions.</span><span class="sxs-lookup"><span data-stu-id="4612a-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="4612a-110">Ces plages doivent être globalement uniques dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="4612a-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="4612a-111">La page **Parcer** des appels affiche la liste de toutes les plages de numéro de parc d’appel définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4612a-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4612a-112">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="4612a-112">Tasks you can perform</span></span>

<span data-ttu-id="4612a-113">Vous pouvez effectuer les tâches suivantes dans la page **Parcage d’appel** :</span><span class="sxs-lookup"><span data-stu-id="4612a-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="4612a-114">Créer une nouvelle plage de numéros</span><span class="sxs-lookup"><span data-stu-id="4612a-114">Create a new number range</span></span>

- <span data-ttu-id="4612a-115">Modifier une plage de numéros existante</span><span class="sxs-lookup"><span data-stu-id="4612a-115">Change an existing number range</span></span>

- <span data-ttu-id="4612a-116">Supprimer une plage de numéros</span><span class="sxs-lookup"><span data-stu-id="4612a-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4612a-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="4612a-117">UI Reference</span></span>

<span data-ttu-id="4612a-118">La liste suivante décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="4612a-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="4612a-119">**Nouveau** Démarre une nouvelle plage de numéro de parcier d’appel.</span><span class="sxs-lookup"><span data-stu-id="4612a-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="4612a-120">**Modifier** Ouvre la plage de nombres sélectionnée pour modification, sélectionne toutes les plages de numéro dans la liste ou supprime la plage de nombres sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4612a-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="4612a-121">**Actualiser** Actualise la liste des plages de nombres.</span><span class="sxs-lookup"><span data-stu-id="4612a-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="4612a-122">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="4612a-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="4612a-123">**Nom** Nom unique qui identifie la plage de nombres.</span><span class="sxs-lookup"><span data-stu-id="4612a-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="4612a-124">**Plage de début** Numéro de début de la plage.</span><span class="sxs-lookup"><span data-stu-id="4612a-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="4612a-125">**Plage de fin** Numéro de fin de la plage.</span><span class="sxs-lookup"><span data-stu-id="4612a-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="4612a-126">**Destination** Nom de domaine complet (FQDN) ou ID de service du service d’application qui héberge l’application de parcage d’appel pour la plage de numéro.</span><span class="sxs-lookup"><span data-stu-id="4612a-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="4612a-127">Pour plus d’informations sur les fonctionnalités et fonctionnalités de parcier d’appel, voir [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="4612a-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="4612a-128">Pour plus d’informations sur l’working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="4612a-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


