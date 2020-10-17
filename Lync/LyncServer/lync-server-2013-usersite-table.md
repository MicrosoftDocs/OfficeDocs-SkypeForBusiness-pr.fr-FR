---
title: 'Lync Server 2013 : table UserSite'
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
ms.openlocfilehash: 656bf8f692617392db02e186fcccebba25a01b0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530001"
---
# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="3dace-102">Table UserSite dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dace-102">UserSite table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dace-103">_**Dernière modification de la rubrique :** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="3dace-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="3dace-p101">La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="3dace-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3dace-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="3dace-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3dace-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="3dace-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3dace-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="3dace-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3dace-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="3dace-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dace-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="3dace-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3dace-111">int</span><span class="sxs-lookup"><span data-stu-id="3dace-111">int</span></span></p></td>
<td><p><span data-ttu-id="3dace-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="3dace-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3dace-113">Numéro unique d’identification de ce site utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3dace-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dace-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="3dace-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="3dace-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="3dace-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="3dace-116">Uniques</span><span class="sxs-lookup"><span data-stu-id="3dace-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="3dace-117">Nom d’utilisateur du site.</span><span class="sxs-lookup"><span data-stu-id="3dace-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dace-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="3dace-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3dace-119">int</span><span class="sxs-lookup"><span data-stu-id="3dace-119">int</span></span></p></td>
<td><p><span data-ttu-id="3dace-120">Etranger</span><span class="sxs-lookup"><span data-stu-id="3dace-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3dace-121">Référencé à partir de la <a href="lync-server-2013-region-table.md">table Region dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3dace-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

