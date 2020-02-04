---
title: 'Lync Server 2013 : Table Endpoint'
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
ms.openlocfilehash: 11da225da1a8120f5de7ac21b3beb318326601f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="6a50b-102">Table Endpoint dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a50b-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a50b-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6a50b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6a50b-104">La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6a50b-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="6a50b-105">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6a50b-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a50b-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6a50b-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6a50b-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6a50b-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a50b-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6a50b-111">int</span><span class="sxs-lookup"><span data-stu-id="6a50b-111">int</span></span></p></td>
<td><p><span data-ttu-id="6a50b-112">Principal</span><span class="sxs-lookup"><span data-stu-id="6a50b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6a50b-113">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6a50b-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a50b-114"><strong>Nom</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="6a50b-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6a50b-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6a50b-116">Différent</span><span class="sxs-lookup"><span data-stu-id="6a50b-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="6a50b-117">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6a50b-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a50b-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="6a50b-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6a50b-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6a50b-120">Système d’exploitation (se) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6a50b-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a50b-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="6a50b-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6a50b-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6a50b-123">Nom de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6a50b-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a50b-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="6a50b-125">type</span><span class="sxs-lookup"><span data-stu-id="6a50b-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6a50b-126">Nombre de cœurs d’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6a50b-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a50b-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="6a50b-128">int</span><span class="sxs-lookup"><span data-stu-id="6a50b-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6a50b-129">Vitesse de processeur de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6a50b-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a50b-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="6a50b-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="6a50b-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="6a50b-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6a50b-132">Indicateur binaire indiquant si le système s’exécute dans un environnement virtualisé :</span><span class="sxs-lookup"><span data-stu-id="6a50b-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="6a50b-133">0x0000 – aucun</span><span class="sxs-lookup"><span data-stu-id="6a50b-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="6a50b-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="6a50b-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="6a50b-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="6a50b-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="6a50b-136">0x0004 – PC virtuel</span><span class="sxs-lookup"><span data-stu-id="6a50b-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="6a50b-137">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="6a50b-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

