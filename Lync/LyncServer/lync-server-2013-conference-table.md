---
title: 'Lync Server 2013 : table Conference'
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
ms.openlocfilehash: 27984e3f39821dd68f18f980550a2c571d27b9b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="87ce2-102">Table Conference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87ce2-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87ce2-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="87ce2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="87ce2-p101">La table Conference est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="87ce2-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87ce2-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="87ce2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="87ce2-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="87ce2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="87ce2-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="87ce2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="87ce2-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="87ce2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87ce2-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="87ce2-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="87ce2-111">int</span><span class="sxs-lookup"><span data-stu-id="87ce2-111">int</span></span></p></td>
<td><p><span data-ttu-id="87ce2-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="87ce2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="87ce2-113">Numéro unique d’identification de cet enregistrement de conférence.</span><span class="sxs-lookup"><span data-stu-id="87ce2-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87ce2-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="87ce2-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="87ce2-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="87ce2-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="87ce2-116">exclusive</span><span class="sxs-lookup"><span data-stu-id="87ce2-116">unique</span></span></p></td>
<td><p><span data-ttu-id="87ce2-117">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="87ce2-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87ce2-118"><strong>Somme de contrôle</strong></span><span class="sxs-lookup"><span data-stu-id="87ce2-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="87ce2-119">int</span><span class="sxs-lookup"><span data-stu-id="87ce2-119">int</span></span></p></td>
<td><p><span data-ttu-id="87ce2-120">Index</span><span class="sxs-lookup"><span data-stu-id="87ce2-120">index</span></span></p></td>
<td><p><span data-ttu-id="87ce2-p102">Checksum de l’URI de la conférence. À usage interne.</span><span class="sxs-lookup"><span data-stu-id="87ce2-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87ce2-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="87ce2-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="87ce2-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="87ce2-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87ce2-125">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="87ce2-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

