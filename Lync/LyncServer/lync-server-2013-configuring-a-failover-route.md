---
title: 'Lync Server 2013 : Configuration d’un itinéraire de basculement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="f6da1-102">Configuration d’un itinéraire de basculement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6da1-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6da1-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f6da1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f6da1-p101">L’exemple suivant montre comment un administrateur peut définir un itinéraire de basculement à utiliser en cas de maintenance ou d’indisponibilité de Dallas-GW1. Les tableaux suivants illustrent la modification de configuration requise.</span><span class="sxs-lookup"><span data-stu-id="f6da1-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="f6da1-p102">Tableau 1. Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="f6da1-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6da1-108">Stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="f6da1-108">User policy</span></span></th>
<th><span data-ttu-id="f6da1-109">Utilisation téléphonique</span><span class="sxs-lookup"><span data-stu-id="f6da1-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6da1-110">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="f6da1-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="f6da1-111">Local</span><span class="sxs-lookup"><span data-stu-id="f6da1-111">Local</span></span></p>
<p><span data-ttu-id="f6da1-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="f6da1-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6da1-113">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="f6da1-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="f6da1-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="f6da1-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6da1-115">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="f6da1-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="f6da1-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="f6da1-116">DallasUsers</span></span></p>
<p><span data-ttu-id="f6da1-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="f6da1-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="f6da1-p103">Tableau 2. Itinéraires</span><span class="sxs-lookup"><span data-stu-id="f6da1-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="f6da1-120">Nom de l’itinéraire</span><span class="sxs-lookup"><span data-stu-id="f6da1-120">Route name</span></span></th>
<th><span data-ttu-id="f6da1-121">Type de numéro</span><span class="sxs-lookup"><span data-stu-id="f6da1-121">Number pattern</span></span></th>
<th><span data-ttu-id="f6da1-122">Utilisation téléphonique</span><span class="sxs-lookup"><span data-stu-id="f6da1-122">Phone usage</span></span></th>
<th><span data-ttu-id="f6da1-123">Jonction</span><span class="sxs-lookup"><span data-stu-id="f6da1-123">Trunk</span></span></th>
<th><span data-ttu-id="f6da1-124">Passerelle</span><span class="sxs-lookup"><span data-stu-id="f6da1-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6da1-125">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="f6da1-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="f6da1-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="f6da1-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="f6da1-127">Local</span><span class="sxs-lookup"><span data-stu-id="f6da1-127">Local</span></span></p>
<p><span data-ttu-id="f6da1-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="f6da1-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="f6da1-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="f6da1-129">Trunk1</span></span></p>
<p><span data-ttu-id="f6da1-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="f6da1-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="f6da1-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="f6da1-131">Red-GW1</span></span></p>
<p><span data-ttu-id="f6da1-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="f6da1-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6da1-133">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="f6da1-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="f6da1-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="f6da1-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="f6da1-135">Local</span><span class="sxs-lookup"><span data-stu-id="f6da1-135">Local</span></span></p></td>
<td><p><span data-ttu-id="f6da1-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="f6da1-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="f6da1-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="f6da1-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6da1-138">Universal Route</span><span class="sxs-lookup"><span data-stu-id="f6da1-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="f6da1-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="f6da1-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="f6da1-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="f6da1-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="f6da1-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="f6da1-141">Trunk1</span></span></p>
<p><span data-ttu-id="f6da1-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="f6da1-142">Trunk2</span></span></p>
<p><span data-ttu-id="f6da1-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="f6da1-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="f6da1-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="f6da1-144">Red-GW1</span></span></p>
<p><span data-ttu-id="f6da1-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="f6da1-145">Red-GW2</span></span></p>
<p><span data-ttu-id="f6da1-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="f6da1-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6da1-147">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="f6da1-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="f6da1-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="f6da1-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="f6da1-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="f6da1-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="f6da1-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="f6da1-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="f6da1-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="f6da1-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6da1-p104">Dans le tableau 1, une utilisation téléphonique GlobalPSTNHopoff est ajoutée après l’utilisation téléphonique DallasUsers dans la stratégie Dallas Calling Policy. Cela permet aux appels dotés de la stratégie Dallas Calling Policy d’utiliser des itinéraires configurés pour l’utilisation téléphonique GlobalPSTNHopoff, lorsqu’aucun itinéraire n’est disponible pour l’utilisation téléphonique DallasUsers.</span><span class="sxs-lookup"><span data-stu-id="f6da1-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

