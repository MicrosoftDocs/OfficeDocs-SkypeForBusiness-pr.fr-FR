---
title: 'Lync Server 2013 : tableau de points de terminaison'
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
ms.openlocfilehash: 33b2f42f1cd122f9f19cfbf04a1c255894ce6e97
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="617a6-102">Tableau de points de terminaison dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="617a6-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="617a6-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="617a6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="617a6-104">La table de points de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="617a6-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="617a6-105">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="617a6-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="617a6-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="617a6-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="617a6-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="617a6-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="617a6-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="617a6-111">int</span><span class="sxs-lookup"><span data-stu-id="617a6-111">int</span></span></p></td>
<td><p><span data-ttu-id="617a6-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="617a6-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="617a6-113">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="617a6-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="617a6-114"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="617a6-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="617a6-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="617a6-116">Uniques</span><span class="sxs-lookup"><span data-stu-id="617a6-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="617a6-117">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="617a6-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="617a6-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="617a6-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="617a6-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="617a6-120">Système d’exploitation (OS) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="617a6-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="617a6-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="617a6-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="617a6-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="617a6-123">Nom de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="617a6-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="617a6-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="617a6-125">type</span><span class="sxs-lookup"><span data-stu-id="617a6-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="617a6-126">Nombre de cœurs de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="617a6-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="617a6-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="617a6-128">int</span><span class="sxs-lookup"><span data-stu-id="617a6-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="617a6-129">Vitesse du processeur de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="617a6-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="617a6-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="617a6-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="617a6-131">entier très petit</span><span class="sxs-lookup"><span data-stu-id="617a6-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="617a6-132">Indicateur binaire qui indique si le système est exécuté dans un environnement virtualisé :</span><span class="sxs-lookup"><span data-stu-id="617a6-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="617a6-133">0x0000 – aucune</span><span class="sxs-lookup"><span data-stu-id="617a6-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="617a6-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="617a6-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="617a6-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="617a6-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="617a6-136">0x0004 – Virtual PC</span><span class="sxs-lookup"><span data-stu-id="617a6-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="617a6-137">0x0008 – PC xen</span><span class="sxs-lookup"><span data-stu-id="617a6-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

