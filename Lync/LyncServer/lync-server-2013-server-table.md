---
title: 'Lync Server 2013 : Table Server'
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
ms.openlocfilehash: c1d0cdb5733e6fc6e21d1dcda1fff6214332de6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="24f7d-102">Table Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24f7d-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24f7d-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="24f7d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="24f7d-104">La table serveur est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="24f7d-104">The Server table is a supporting table.</span></span> <span data-ttu-id="24f7d-105">Chaque enregistrement représente un serveur.</span><span class="sxs-lookup"><span data-stu-id="24f7d-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24f7d-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="24f7d-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="24f7d-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="24f7d-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24f7d-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="24f7d-111">int</span><span class="sxs-lookup"><span data-stu-id="24f7d-111">int</span></span></p></td>
<td><p><span data-ttu-id="24f7d-112">Principal</span><span class="sxs-lookup"><span data-stu-id="24f7d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="24f7d-113">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="24f7d-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24f7d-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="24f7d-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="24f7d-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="24f7d-116">index</span><span class="sxs-lookup"><span data-stu-id="24f7d-116">index</span></span></p></td>
<td><p><span data-ttu-id="24f7d-117">Chaîne d’adresses MAC.</span><span class="sxs-lookup"><span data-stu-id="24f7d-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24f7d-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="24f7d-119">int</span><span class="sxs-lookup"><span data-stu-id="24f7d-119">int</span></span></p></td>
<td><p><span data-ttu-id="24f7d-120">Externes</span><span class="sxs-lookup"><span data-stu-id="24f7d-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="24f7d-121">1 : serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="24f7d-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="24f7d-122">2 : service de conférence a/V Server16394 : service32769 Edge A/V : passerelle</span><span class="sxs-lookup"><span data-stu-id="24f7d-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24f7d-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="24f7d-124">nvarchar</span><span class="sxs-lookup"><span data-stu-id="24f7d-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="24f7d-125">Regroupement auquel appartient le serveur.</span><span class="sxs-lookup"><span data-stu-id="24f7d-125">Pool the server belongs to.</span></span> <span data-ttu-id="24f7d-126">Applicable uniquement au serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="24f7d-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24f7d-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="24f7d-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="24f7d-128">DateHeure</span><span class="sxs-lookup"><span data-stu-id="24f7d-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="24f7d-129">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="24f7d-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

