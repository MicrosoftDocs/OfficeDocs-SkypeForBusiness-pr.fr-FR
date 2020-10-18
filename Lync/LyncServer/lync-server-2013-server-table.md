---
title: 'Lync Server 2013 : table serveur'
description: 'Lync Server 2013 : table serveur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00990a91aec64063480d96a16380171990913ad4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576520"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="15e73-103">Table serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15e73-103">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15e73-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="15e73-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="15e73-105">Le tableau serveur est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="15e73-105">The Server table is a supporting table.</span></span> <span data-ttu-id="15e73-106">Chaque enregistrement représente un serveur.</span><span class="sxs-lookup"><span data-stu-id="15e73-106">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15e73-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="15e73-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="15e73-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="15e73-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15e73-111"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-111"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="15e73-112">int</span><span class="sxs-lookup"><span data-stu-id="15e73-112">int</span></span></p></td>
<td><p><span data-ttu-id="15e73-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="15e73-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="15e73-114">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="15e73-114">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e73-115"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-115"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="15e73-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15e73-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15e73-117">Index</span><span class="sxs-lookup"><span data-stu-id="15e73-117">index</span></span></p></td>
<td><p><span data-ttu-id="15e73-118">Chaîne d’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="15e73-118">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e73-119"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-119"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="15e73-120">int</span><span class="sxs-lookup"><span data-stu-id="15e73-120">int</span></span></p></td>
<td><p><span data-ttu-id="15e73-121">Etranger</span><span class="sxs-lookup"><span data-stu-id="15e73-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15e73-122">1 : serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="15e73-122">1: Mediation Server</span></span></p>
<p><span data-ttu-id="15e73-123">2 : Conférence a/V Server16394 : service32769 Edge A/V : passerelle</span><span class="sxs-lookup"><span data-stu-id="15e73-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e73-124"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-124"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="15e73-125">nvarchar</span><span class="sxs-lookup"><span data-stu-id="15e73-125">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15e73-126">Pool auquel appartient le serveur.</span><span class="sxs-lookup"><span data-stu-id="15e73-126">Pool the server belongs to.</span></span> <span data-ttu-id="15e73-127">Applicable uniquement au serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="15e73-127">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e73-128"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="15e73-128"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="15e73-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="15e73-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15e73-130">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="15e73-130">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

