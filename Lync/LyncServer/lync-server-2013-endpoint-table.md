---
title: 'Lync Server 2013 : Table Endpoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cedf4d85cefd8a9fefb9f0ee4608f4a290fdc09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="ef729-102">Table Endpoint dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef729-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef729-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ef729-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ef729-104">La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ef729-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ef729-105">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef729-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef729-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ef729-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ef729-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ef729-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef729-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ef729-111">int</span><span class="sxs-lookup"><span data-stu-id="ef729-111">int</span></span></p></td>
<td><p><span data-ttu-id="ef729-112">Principal</span><span class="sxs-lookup"><span data-stu-id="ef729-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ef729-113">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef729-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef729-114"><strong>Nom</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ef729-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ef729-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef729-116">Différent</span><span class="sxs-lookup"><span data-stu-id="ef729-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="ef729-117">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef729-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef729-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="ef729-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ef729-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ef729-120">Système d’exploitation (se) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef729-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef729-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="ef729-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ef729-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ef729-123">Nom de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef729-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef729-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="ef729-125">type</span><span class="sxs-lookup"><span data-stu-id="ef729-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ef729-126">Nombre de cœurs d’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef729-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef729-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="ef729-128">int</span><span class="sxs-lookup"><span data-stu-id="ef729-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ef729-129">Vitesse de processeur de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef729-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef729-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ef729-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ef729-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="ef729-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ef729-132">Indicateur binaire indiquant si le système s’exécute dans un environnement virtualisé:</span><span class="sxs-lookup"><span data-stu-id="ef729-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="ef729-133">0x0000 – aucun</span><span class="sxs-lookup"><span data-stu-id="ef729-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="ef729-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="ef729-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="ef729-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="ef729-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="ef729-136">0x0004 – PC virtuel</span><span class="sxs-lookup"><span data-stu-id="ef729-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="ef729-137">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="ef729-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

