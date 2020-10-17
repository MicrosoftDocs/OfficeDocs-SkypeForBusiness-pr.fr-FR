---
title: 'Lync Server 2013 : table Conference'
description: 'Lync Server 2013 : table Conference.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565725b527399cb3be55c649dfd74d8bcb5f13a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550660"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="e03e7-103">Table Conference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e03e7-103">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e03e7-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e03e7-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e03e7-p101">La table Conference est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="e03e7-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e03e7-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="e03e7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e03e7-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="e03e7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e03e7-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="e03e7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e03e7-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e03e7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e03e7-111"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="e03e7-111"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e03e7-112">int</span><span class="sxs-lookup"><span data-stu-id="e03e7-112">int</span></span></p></td>
<td><p><span data-ttu-id="e03e7-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="e03e7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e03e7-114">Numéro unique d’identification de cet enregistrement de conférence.</span><span class="sxs-lookup"><span data-stu-id="e03e7-114">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e03e7-115"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="e03e7-115"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="e03e7-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e03e7-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e03e7-117">exclusive</span><span class="sxs-lookup"><span data-stu-id="e03e7-117">unique</span></span></p></td>
<td><p><span data-ttu-id="e03e7-118">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="e03e7-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e03e7-119"><strong>Somme de contrôle</strong></span><span class="sxs-lookup"><span data-stu-id="e03e7-119"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="e03e7-120">int</span><span class="sxs-lookup"><span data-stu-id="e03e7-120">int</span></span></p></td>
<td><p><span data-ttu-id="e03e7-121">Index</span><span class="sxs-lookup"><span data-stu-id="e03e7-121">index</span></span></p></td>
<td><p><span data-ttu-id="e03e7-p102">Checksum de l’URI de la conférence. À usage interne.</span><span class="sxs-lookup"><span data-stu-id="e03e7-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e03e7-124"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="e03e7-124"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="e03e7-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e03e7-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e03e7-126">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="e03e7-126">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

