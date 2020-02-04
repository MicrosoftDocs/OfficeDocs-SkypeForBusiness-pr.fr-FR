---
title: 'Lync Server 2013 : Table Conference'
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
ms.openlocfilehash: 4941dc3ef59630cd77cfb0f8a51407d15ca628f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="c5a7e-102">Table Conference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a7e-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5a7e-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c5a7e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c5a7e-104">La table Conference est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c5a7e-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="c5a7e-105">Chaque enregistrement représente une conférence ou une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="c5a7e-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a7e-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="c5a7e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c5a7e-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="c5a7e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c5a7e-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="c5a7e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c5a7e-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="c5a7e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a7e-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="c5a7e-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c5a7e-111">int</span><span class="sxs-lookup"><span data-stu-id="c5a7e-111">int</span></span></p></td>
<td><p><span data-ttu-id="c5a7e-112">Principal</span><span class="sxs-lookup"><span data-stu-id="c5a7e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c5a7e-113">Numéro unique identifiant cet enregistrement de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5a7e-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a7e-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="c5a7e-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="c5a7e-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5a7e-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5a7e-116">différent</span><span class="sxs-lookup"><span data-stu-id="c5a7e-116">unique</span></span></p></td>
<td><p><span data-ttu-id="c5a7e-117">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="c5a7e-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a7e-118"><strong>1018</strong></span><span class="sxs-lookup"><span data-stu-id="c5a7e-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="c5a7e-119">int</span><span class="sxs-lookup"><span data-stu-id="c5a7e-119">int</span></span></p></td>
<td><p><span data-ttu-id="c5a7e-120">index</span><span class="sxs-lookup"><span data-stu-id="c5a7e-120">index</span></span></p></td>
<td><p><span data-ttu-id="c5a7e-121">Checksum de l’URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5a7e-121">Checksum of the conference URI.</span></span> <span data-ttu-id="c5a7e-122">Cette opération est utilisée en interne.</span><span class="sxs-lookup"><span data-stu-id="c5a7e-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a7e-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="c5a7e-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="c5a7e-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c5a7e-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c5a7e-125">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="c5a7e-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

