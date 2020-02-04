---
title: 'Lync Server 2013 : Configuration d’un itinéraire de basculement'
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
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="e902c-102">Configuration d’un itinéraire de basculement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e902c-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e902c-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e902c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e902c-p101">L’exemple suivant montre comment un administrateur peut définir un itinéraire de basculement à utiliser en cas de maintenance ou d’indisponibilité de Dallas-GW1. Les tableaux suivants illustrent la modification de configuration requise.</span><span class="sxs-lookup"><span data-stu-id="e902c-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="e902c-p102">Tableau 1. Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="e902c-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e902c-108">Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="e902c-108">User policy</span></span></th>
<th><span data-ttu-id="e902c-109">Utilisation téléphonique</span><span class="sxs-lookup"><span data-stu-id="e902c-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e902c-110">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="e902c-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="e902c-111">Local</span><span class="sxs-lookup"><span data-stu-id="e902c-111">Local</span></span></p>
<p><span data-ttu-id="e902c-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="e902c-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e902c-113">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="e902c-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="e902c-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="e902c-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e902c-115">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="e902c-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="e902c-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="e902c-116">DallasUsers</span></span></p>
<p><span data-ttu-id="e902c-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="e902c-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="e902c-p103">Tableau 2. Itinéraires</span><span class="sxs-lookup"><span data-stu-id="e902c-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="e902c-120">Nom de l’itinéraire</span><span class="sxs-lookup"><span data-stu-id="e902c-120">Route name</span></span></th>
<th><span data-ttu-id="e902c-121">Type de numéro</span><span class="sxs-lookup"><span data-stu-id="e902c-121">Number pattern</span></span></th>
<th><span data-ttu-id="e902c-122">Utilisation téléphonique</span><span class="sxs-lookup"><span data-stu-id="e902c-122">Phone usage</span></span></th>
<th><span data-ttu-id="e902c-123">Jonction</span><span class="sxs-lookup"><span data-stu-id="e902c-123">Trunk</span></span></th>
<th><span data-ttu-id="e902c-124">Passerelle</span><span class="sxs-lookup"><span data-stu-id="e902c-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e902c-125">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="e902c-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="e902c-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e902c-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="e902c-127">Local</span><span class="sxs-lookup"><span data-stu-id="e902c-127">Local</span></span></p>
<p><span data-ttu-id="e902c-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="e902c-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="e902c-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="e902c-129">Trunk1</span></span></p>
<p><span data-ttu-id="e902c-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="e902c-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="e902c-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="e902c-131">Red-GW1</span></span></p>
<p><span data-ttu-id="e902c-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="e902c-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e902c-133">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="e902c-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="e902c-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e902c-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="e902c-135">Local</span><span class="sxs-lookup"><span data-stu-id="e902c-135">Local</span></span></p></td>
<td><p><span data-ttu-id="e902c-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="e902c-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="e902c-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="e902c-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e902c-138">Universal Route</span><span class="sxs-lookup"><span data-stu-id="e902c-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="e902c-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="e902c-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="e902c-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="e902c-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="e902c-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="e902c-141">Trunk1</span></span></p>
<p><span data-ttu-id="e902c-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="e902c-142">Trunk2</span></span></p>
<p><span data-ttu-id="e902c-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="e902c-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="e902c-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="e902c-144">Red-GW1</span></span></p>
<p><span data-ttu-id="e902c-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="e902c-145">Red-GW2</span></span></p>
<p><span data-ttu-id="e902c-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="e902c-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e902c-147">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="e902c-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="e902c-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="e902c-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="e902c-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="e902c-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="e902c-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="e902c-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="e902c-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="e902c-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e902c-p104">Dans le tableau 1, une utilisation téléphonique GlobalPSTNHopoff est ajoutée après l’utilisation téléphonique DallasUsers dans la stratégie Dallas Calling Policy. Cela permet aux appels dotés de la stratégie Dallas Calling Policy d’utiliser des itinéraires configurés pour l’utilisation téléphonique GlobalPSTNHopoff, lorsqu’aucun itinéraire n’est disponible pour l’utilisation téléphonique DallasUsers.</span><span class="sxs-lookup"><span data-stu-id="e902c-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

