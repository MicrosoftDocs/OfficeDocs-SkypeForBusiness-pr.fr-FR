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
description: Lorsqu’un appel est paré, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu’à ce que quelqu’un le récupère ou qu’il n’sorte pas. Vous devez configurer une table avec les plages de numéros de poste que vous réservez pour les appels par parcage. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est assigné). Chaque pool qui exécute l’application de parcage d’appel peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.
ms.openlocfilehash: b7926c10424fd5902fdc43e6c0fccadb45e61f79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097070"
---
# <a name="call-park"></a><span data-ttu-id="3efd4-106">Parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="3efd4-106">Call Park</span></span>

<span data-ttu-id="3efd4-107">Lorsqu’un appel est paré, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu’à ce que quelqu’un le récupère ou qu’il n’sorte pas. Vous devez configurer une table avec les plages de numéros de poste que vous réservez pour les appels par parcage.</span><span class="sxs-lookup"><span data-stu-id="3efd4-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="3efd4-108">Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est assigné).</span><span class="sxs-lookup"><span data-stu-id="3efd4-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="3efd4-109">Chaque pool qui exécute l’application de parcage d’appel peut avoir une ou plusieurs plages d’extensions.</span><span class="sxs-lookup"><span data-stu-id="3efd4-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="3efd4-110">Ces plages doivent être globalement uniques dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="3efd4-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="3efd4-111">La page **Parcer** des appels affiche la liste de toutes les plages de numéro de parc d’appel définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3efd4-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3efd4-112">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="3efd4-112">Tasks you can perform</span></span>

<span data-ttu-id="3efd4-113">Vous pouvez effectuer les tâches suivantes dans la page **Parcage d’appel** :</span><span class="sxs-lookup"><span data-stu-id="3efd4-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="3efd4-114">Créer une nouvelle plage de numéros</span><span class="sxs-lookup"><span data-stu-id="3efd4-114">Create a new number range</span></span>

- <span data-ttu-id="3efd4-115">Modifier une plage de numéros existante</span><span class="sxs-lookup"><span data-stu-id="3efd4-115">Change an existing number range</span></span>

- <span data-ttu-id="3efd4-116">Supprimer une plage de numéros</span><span class="sxs-lookup"><span data-stu-id="3efd4-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3efd4-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="3efd4-117">UI Reference</span></span>

<span data-ttu-id="3efd4-118">La liste suivante décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="3efd4-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="3efd4-119">**Nouveau** Démarre une nouvelle plage de numéro de parcier d’appel.</span><span class="sxs-lookup"><span data-stu-id="3efd4-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="3efd4-120">**Modifier** Ouvre la plage de nombres sélectionnée pour modification, sélectionne toutes les plages de numéro dans la liste ou supprime la plage de nombres sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3efd4-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="3efd4-121">**Actualiser** Actualise la liste des plages de nombres.</span><span class="sxs-lookup"><span data-stu-id="3efd4-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="3efd4-122">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="3efd4-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="3efd4-123">**Nom** Nom unique qui identifie la plage de nombres.</span><span class="sxs-lookup"><span data-stu-id="3efd4-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="3efd4-124">**Plage de début** Numéro de début de la plage.</span><span class="sxs-lookup"><span data-stu-id="3efd4-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="3efd4-125">**Plage de fin** Numéro de fin de la plage.</span><span class="sxs-lookup"><span data-stu-id="3efd4-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="3efd4-126">**Destination** Nom de domaine complet (FQDN) ou ID de service du service d’application qui héberge l’application de parcage d’appel pour la plage de numéro.</span><span class="sxs-lookup"><span data-stu-id="3efd4-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="3efd4-127">Pour plus d’informations sur les fonctionnalités et fonctionnalités de parcier d’appel, voir [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="3efd4-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="3efd4-128">Pour plus d’informations sur l’working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span><span class="sxs-lookup"><span data-stu-id="3efd4-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>