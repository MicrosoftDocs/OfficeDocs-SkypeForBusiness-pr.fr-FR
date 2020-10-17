---
title: 'Lync Server 2013 : configuration d’un itinéraire de basculement'
description: 'Lync Server 2013 : configuration d’un itinéraire de basculement.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560490"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="6649d-103">Configuration d’un itinéraire de basculement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6649d-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6649d-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6649d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6649d-p101">L’exemple suivant montre comment un administrateur peut définir un itinéraire de basculement à utiliser en cas de maintenance ou d’indisponibilité de Dallas-GW1. Les tableaux suivants illustrent la modification de configuration requise.</span><span class="sxs-lookup"><span data-stu-id="6649d-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="6649d-p102">Tableau 1. Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="6649d-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6649d-109">Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="6649d-109">User policy</span></span></th>
<th><span data-ttu-id="6649d-110">Utilisation téléphonique</span><span class="sxs-lookup"><span data-stu-id="6649d-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6649d-111">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="6649d-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="6649d-112">Local</span><span class="sxs-lookup"><span data-stu-id="6649d-112">Local</span></span></p>
<p><span data-ttu-id="6649d-113">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="6649d-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6649d-114">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="6649d-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="6649d-115">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="6649d-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6649d-116">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="6649d-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="6649d-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="6649d-117">DallasUsers</span></span></p>
<p><span data-ttu-id="6649d-118">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="6649d-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="6649d-p103">Tableau 2. Itinéraires</span><span class="sxs-lookup"><span data-stu-id="6649d-p103">Table 2. Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6649d-121">Nom de l’itinéraire</span><span class="sxs-lookup"><span data-stu-id="6649d-121">Route name</span></span></th>
<th><span data-ttu-id="6649d-122">Modèle de numéro</span><span class="sxs-lookup"><span data-stu-id="6649d-122">Number pattern</span></span></th>
<th><span data-ttu-id="6649d-123">Utilisation téléphonique</span><span class="sxs-lookup"><span data-stu-id="6649d-123">Phone usage</span></span></th>
<th><span data-ttu-id="6649d-124">Urbain</span><span class="sxs-lookup"><span data-stu-id="6649d-124">Trunk</span></span></th>
<th><span data-ttu-id="6649d-125">Passerelle</span><span class="sxs-lookup"><span data-stu-id="6649d-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6649d-126">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="6649d-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="6649d-127">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="6649d-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="6649d-128">Local</span><span class="sxs-lookup"><span data-stu-id="6649d-128">Local</span></span></p>
<p><span data-ttu-id="6649d-129">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="6649d-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="6649d-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="6649d-130">Trunk1</span></span></p>
<p><span data-ttu-id="6649d-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="6649d-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="6649d-132">Rouge-GW1</span><span class="sxs-lookup"><span data-stu-id="6649d-132">Red-GW1</span></span></p>
<p><span data-ttu-id="6649d-133">Rouge-GW2</span><span class="sxs-lookup"><span data-stu-id="6649d-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6649d-134">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="6649d-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="6649d-135">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="6649d-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="6649d-136">Local</span><span class="sxs-lookup"><span data-stu-id="6649d-136">Local</span></span></p></td>
<td><p><span data-ttu-id="6649d-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6649d-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6649d-138">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="6649d-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6649d-139">Universal Route</span><span class="sxs-lookup"><span data-stu-id="6649d-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="6649d-140">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="6649d-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="6649d-141">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="6649d-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="6649d-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="6649d-142">Trunk1</span></span></p>
<p><span data-ttu-id="6649d-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="6649d-143">Trunk2</span></span></p>
<p><span data-ttu-id="6649d-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6649d-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6649d-145">Rouge-GW1</span><span class="sxs-lookup"><span data-stu-id="6649d-145">Red-GW1</span></span></p>
<p><span data-ttu-id="6649d-146">Rouge-GW2</span><span class="sxs-lookup"><span data-stu-id="6649d-146">Red-GW2</span></span></p>
<p><span data-ttu-id="6649d-147">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="6649d-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6649d-148">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="6649d-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="6649d-149">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="6649d-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="6649d-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="6649d-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="6649d-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6649d-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6649d-152">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="6649d-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6649d-p104">Dans le tableau 1, une utilisation téléphonique GlobalPSTNHopoff est ajoutée après l’utilisation téléphonique DallasUsers dans la stratégie Dallas Calling Policy. Cela permet aux appels dotés de la stratégie Dallas Calling Policy d’utiliser des itinéraires configurés pour l’utilisation téléphonique GlobalPSTNHopoff, lorsqu’aucun itinéraire n’est disponible pour l’utilisation téléphonique DallasUsers.</span><span class="sxs-lookup"><span data-stu-id="6649d-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

