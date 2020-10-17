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
ms.openlocfilehash: ebfc08cd5a27527d5afebdae8b2fea8335f93dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510231"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="63b80-102">Table serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63b80-102">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63b80-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="63b80-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="63b80-104">Le tableau serveur est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="63b80-104">The Server table is a supporting table.</span></span> <span data-ttu-id="63b80-105">Chaque enregistrement représente un serveur.</span><span class="sxs-lookup"><span data-stu-id="63b80-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b80-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="63b80-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="63b80-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="63b80-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b80-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="63b80-111">int</span><span class="sxs-lookup"><span data-stu-id="63b80-111">int</span></span></p></td>
<td><p><span data-ttu-id="63b80-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="63b80-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="63b80-113">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="63b80-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b80-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="63b80-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63b80-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63b80-116">Index</span><span class="sxs-lookup"><span data-stu-id="63b80-116">index</span></span></p></td>
<td><p><span data-ttu-id="63b80-117">Chaîne d’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="63b80-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b80-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="63b80-119">int</span><span class="sxs-lookup"><span data-stu-id="63b80-119">int</span></span></p></td>
<td><p><span data-ttu-id="63b80-120">Etranger</span><span class="sxs-lookup"><span data-stu-id="63b80-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="63b80-121">1 : serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="63b80-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="63b80-122">2 : Conférence a/V Server16394 : service32769 Edge A/V : passerelle</span><span class="sxs-lookup"><span data-stu-id="63b80-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b80-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="63b80-124">nvarchar</span><span class="sxs-lookup"><span data-stu-id="63b80-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63b80-125">Pool auquel appartient le serveur.</span><span class="sxs-lookup"><span data-stu-id="63b80-125">Pool the server belongs to.</span></span> <span data-ttu-id="63b80-126">Applicable uniquement au serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="63b80-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b80-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="63b80-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="63b80-128">DateHeure</span><span class="sxs-lookup"><span data-stu-id="63b80-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63b80-129">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="63b80-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

