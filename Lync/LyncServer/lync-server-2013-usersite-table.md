---
title: 'Lync Server 2013 : table UserSite'
description: 'Lync Server 2013 : table UserSite.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e0fb3149b9378bbfd3f14da8176eed226e4f57f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548620"
---
# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="ac3a3-103">Table UserSite dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac3a3-103">UserSite table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac3a3-104">_**Dernière modification de la rubrique :** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="ac3a3-104">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="ac3a3-p101">La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="ac3a3-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac3a3-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="ac3a3-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ac3a3-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="ac3a3-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ac3a3-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="ac3a3-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ac3a3-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ac3a3-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac3a3-111"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="ac3a3-111"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ac3a3-112">int</span><span class="sxs-lookup"><span data-stu-id="ac3a3-112">int</span></span></p></td>
<td><p><span data-ttu-id="ac3a3-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="ac3a3-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ac3a3-114">Numéro unique d’identification de ce site utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ac3a3-114">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac3a3-115"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="ac3a3-115"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="ac3a3-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac3a3-116">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac3a3-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="ac3a3-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="ac3a3-118">Nom d’utilisateur du site.</span><span class="sxs-lookup"><span data-stu-id="ac3a3-118">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac3a3-119"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="ac3a3-119"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ac3a3-120">int</span><span class="sxs-lookup"><span data-stu-id="ac3a3-120">int</span></span></p></td>
<td><p><span data-ttu-id="ac3a3-121">Etranger</span><span class="sxs-lookup"><span data-stu-id="ac3a3-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac3a3-122">Référencé à partir de la <a href="lync-server-2013-region-table.md">table Region dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ac3a3-122">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

