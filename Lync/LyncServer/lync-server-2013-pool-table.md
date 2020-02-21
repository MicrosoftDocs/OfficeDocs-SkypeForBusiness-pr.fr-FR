---
title: 'Lync Server 2013 : table pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487b73bd7564f6fc3f1064a3154a6fb5e06e6e90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="851a7-102">Table pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="851a7-102">Pool table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="851a7-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="851a7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="851a7-p101">La table Pool est une table de prise en charge qui contient des informations sur les différents pools frontaux. Chaque enregistrement dans la table représente un pool.</span><span class="sxs-lookup"><span data-stu-id="851a7-p101">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="851a7-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="851a7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="851a7-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="851a7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="851a7-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="851a7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="851a7-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="851a7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="851a7-110"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="851a7-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="851a7-111">int</span><span class="sxs-lookup"><span data-stu-id="851a7-111">int</span></span></p></td>
<td><p><span data-ttu-id="851a7-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="851a7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="851a7-113">Numéro unique identifiant ce pool.</span><span class="sxs-lookup"><span data-stu-id="851a7-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="851a7-114"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="851a7-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="851a7-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="851a7-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="851a7-116">Exclusive </span><span class="sxs-lookup"><span data-stu-id="851a7-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="851a7-117">Nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="851a7-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

