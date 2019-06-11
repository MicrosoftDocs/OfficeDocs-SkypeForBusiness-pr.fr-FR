---
title: 'Lync Server 2013 : Table Conference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f57f7baf017507da44677cc475c99d192fe868f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="ccf88-102">Table Conference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccf88-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccf88-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ccf88-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ccf88-104">La table Conference est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="ccf88-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="ccf88-105">Chaque enregistrement représente une conférence ou une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="ccf88-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccf88-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="ccf88-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ccf88-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="ccf88-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ccf88-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="ccf88-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ccf88-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="ccf88-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccf88-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="ccf88-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ccf88-111">int</span><span class="sxs-lookup"><span data-stu-id="ccf88-111">int</span></span></p></td>
<td><p><span data-ttu-id="ccf88-112">Principal</span><span class="sxs-lookup"><span data-stu-id="ccf88-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ccf88-113">Numéro unique identifiant cet enregistrement de conférence.</span><span class="sxs-lookup"><span data-stu-id="ccf88-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccf88-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="ccf88-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="ccf88-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ccf88-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccf88-116">différent</span><span class="sxs-lookup"><span data-stu-id="ccf88-116">unique</span></span></p></td>
<td><p><span data-ttu-id="ccf88-117">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="ccf88-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccf88-118"><strong>1018</strong></span><span class="sxs-lookup"><span data-stu-id="ccf88-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="ccf88-119">int</span><span class="sxs-lookup"><span data-stu-id="ccf88-119">int</span></span></p></td>
<td><p><span data-ttu-id="ccf88-120">index</span><span class="sxs-lookup"><span data-stu-id="ccf88-120">index</span></span></p></td>
<td><p><span data-ttu-id="ccf88-121">Checksum de l’URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="ccf88-121">Checksum of the conference URI.</span></span> <span data-ttu-id="ccf88-122">Cette opération est utilisée en interne.</span><span class="sxs-lookup"><span data-stu-id="ccf88-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccf88-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ccf88-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ccf88-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ccf88-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccf88-125">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="ccf88-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

