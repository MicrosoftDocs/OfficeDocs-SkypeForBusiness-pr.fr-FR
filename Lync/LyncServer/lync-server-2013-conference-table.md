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
ms.openlocfilehash: a6f51e05c9721ca789724dcd015c62c2a71d8731
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520622"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="c7f2c-102">Table Conference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7f2c-102">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7f2c-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c7f2c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c7f2c-p101">La table Conference est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="c7f2c-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7f2c-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="c7f2c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c7f2c-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="c7f2c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c7f2c-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="c7f2c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c7f2c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c7f2c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7f2c-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="c7f2c-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c7f2c-111">int</span><span class="sxs-lookup"><span data-stu-id="c7f2c-111">int</span></span></p></td>
<td><p><span data-ttu-id="c7f2c-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="c7f2c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c7f2c-113">Numéro unique d’identification de cet enregistrement de conférence.</span><span class="sxs-lookup"><span data-stu-id="c7f2c-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7f2c-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="c7f2c-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="c7f2c-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c7f2c-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c7f2c-116">exclusive</span><span class="sxs-lookup"><span data-stu-id="c7f2c-116">unique</span></span></p></td>
<td><p><span data-ttu-id="c7f2c-117">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="c7f2c-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7f2c-118"><strong>Somme de contrôle</strong></span><span class="sxs-lookup"><span data-stu-id="c7f2c-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="c7f2c-119">int</span><span class="sxs-lookup"><span data-stu-id="c7f2c-119">int</span></span></p></td>
<td><p><span data-ttu-id="c7f2c-120">Index</span><span class="sxs-lookup"><span data-stu-id="c7f2c-120">index</span></span></p></td>
<td><p><span data-ttu-id="c7f2c-p102">Checksum de l’URI de la conférence. À usage interne.</span><span class="sxs-lookup"><span data-stu-id="c7f2c-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7f2c-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="c7f2c-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="c7f2c-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c7f2c-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7f2c-125">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="c7f2c-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

