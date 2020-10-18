---
title: 'Lync Server 2013 : tableau de points de terminaison'
description: 'Lync Server 2013 : tableau de points de terminaison.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575620"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="77c3a-103">Tableau de points de terminaison dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77c3a-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77c3a-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="77c3a-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="77c3a-105">La table de points de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="77c3a-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="77c3a-106">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="77c3a-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77c3a-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="77c3a-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="77c3a-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="77c3a-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77c3a-111"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="77c3a-112">int</span><span class="sxs-lookup"><span data-stu-id="77c3a-112">int</span></span></p></td>
<td><p><span data-ttu-id="77c3a-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="77c3a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="77c3a-114">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="77c3a-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77c3a-115"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="77c3a-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="77c3a-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77c3a-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="77c3a-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="77c3a-118">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="77c3a-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77c3a-119"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="77c3a-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="77c3a-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77c3a-121">Système d’exploitation (OS) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="77c3a-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77c3a-122"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="77c3a-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="77c3a-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77c3a-124">Nom de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="77c3a-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77c3a-125"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="77c3a-126">type</span><span class="sxs-lookup"><span data-stu-id="77c3a-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77c3a-127">Nombre de cœurs de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="77c3a-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77c3a-128"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="77c3a-129">int</span><span class="sxs-lookup"><span data-stu-id="77c3a-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77c3a-130">Vitesse du processeur de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="77c3a-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77c3a-131"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="77c3a-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="77c3a-132">entier très petit</span><span class="sxs-lookup"><span data-stu-id="77c3a-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77c3a-133">Indicateur binaire qui indique si le système est exécuté dans un environnement virtualisé :</span><span class="sxs-lookup"><span data-stu-id="77c3a-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="77c3a-134">0x0000 – aucune</span><span class="sxs-lookup"><span data-stu-id="77c3a-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="77c3a-135">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="77c3a-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="77c3a-136">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="77c3a-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="77c3a-137">0x0004 – Virtual PC</span><span class="sxs-lookup"><span data-stu-id="77c3a-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="77c3a-138">0x0008 – PC xen</span><span class="sxs-lookup"><span data-stu-id="77c3a-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

