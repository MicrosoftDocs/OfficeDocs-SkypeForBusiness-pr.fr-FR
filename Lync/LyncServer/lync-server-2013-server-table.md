---
title: 'Lync Server 2013 : table serveur'
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
ms.openlocfilehash: d95ca6af9a3e762a39142fcaf754d810050d83d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="fe446-102">Table serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe446-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe446-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fe446-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fe446-104">Le tableau serveur est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="fe446-104">The Server table is a supporting table.</span></span> <span data-ttu-id="fe446-105">Chaque enregistrement représente un serveur.</span><span class="sxs-lookup"><span data-stu-id="fe446-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe446-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fe446-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fe446-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fe446-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe446-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fe446-111">int</span><span class="sxs-lookup"><span data-stu-id="fe446-111">int</span></span></p></td>
<td><p><span data-ttu-id="fe446-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="fe446-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe446-113">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="fe446-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe446-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="fe446-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe446-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe446-116">Index</span><span class="sxs-lookup"><span data-stu-id="fe446-116">index</span></span></p></td>
<td><p><span data-ttu-id="fe446-117">Chaîne d’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="fe446-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe446-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe446-119">int</span><span class="sxs-lookup"><span data-stu-id="fe446-119">int</span></span></p></td>
<td><p><span data-ttu-id="fe446-120">Etranger</span><span class="sxs-lookup"><span data-stu-id="fe446-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe446-121">1 : serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="fe446-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="fe446-122">2 : Conférence a/V Server16394 : service32769 Edge A/V : passerelle</span><span class="sxs-lookup"><span data-stu-id="fe446-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe446-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="fe446-124">nvarchar</span><span class="sxs-lookup"><span data-stu-id="fe446-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe446-125">Pool auquel appartient le serveur.</span><span class="sxs-lookup"><span data-stu-id="fe446-125">Pool the server belongs to.</span></span> <span data-ttu-id="fe446-126">Applicable uniquement au serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="fe446-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe446-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="fe446-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="fe446-128">DateHeure</span><span class="sxs-lookup"><span data-stu-id="fe446-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe446-129">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="fe446-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

