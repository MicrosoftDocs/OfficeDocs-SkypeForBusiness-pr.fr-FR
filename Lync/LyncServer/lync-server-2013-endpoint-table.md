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
ms.openlocfilehash: 3a71e59b6cf9b4143a5b984cc7b169279aa2cb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533321"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="7c42c-102">Tableau de points de terminaison dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c42c-102">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c42c-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7c42c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7c42c-104">La table de points de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="7c42c-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="7c42c-105">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7c42c-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c42c-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7c42c-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7c42c-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7c42c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c42c-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7c42c-111">int</span><span class="sxs-lookup"><span data-stu-id="7c42c-111">int</span></span></p></td>
<td><p><span data-ttu-id="7c42c-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="7c42c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7c42c-113">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7c42c-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c42c-114"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="7c42c-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7c42c-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7c42c-116">Uniques</span><span class="sxs-lookup"><span data-stu-id="7c42c-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="7c42c-117">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7c42c-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c42c-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="7c42c-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="7c42c-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7c42c-120">Système d’exploitation (OS) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7c42c-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c42c-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="7c42c-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="7c42c-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c42c-123">Nom de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7c42c-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c42c-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="7c42c-125">type</span><span class="sxs-lookup"><span data-stu-id="7c42c-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c42c-126">Nombre de cœurs de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7c42c-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c42c-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="7c42c-128">int</span><span class="sxs-lookup"><span data-stu-id="7c42c-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c42c-129">Vitesse du processeur de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7c42c-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c42c-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7c42c-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7c42c-131">entier très petit</span><span class="sxs-lookup"><span data-stu-id="7c42c-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c42c-132">Indicateur binaire qui indique si le système est exécuté dans un environnement virtualisé :</span><span class="sxs-lookup"><span data-stu-id="7c42c-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c42c-133">0x0000 – aucune</span><span class="sxs-lookup"><span data-stu-id="7c42c-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="7c42c-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="7c42c-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="7c42c-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="7c42c-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="7c42c-136">0x0004 – Virtual PC</span><span class="sxs-lookup"><span data-stu-id="7c42c-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="7c42c-137">0x0008 – PC xen</span><span class="sxs-lookup"><span data-stu-id="7c42c-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

