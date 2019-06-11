---
title: 'Lync Server 2013 : Table Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08f878b9eefef86fba0fed4dd039b9a60b6f035d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="b021f-102">Table Pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b021f-102">Pool table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b021f-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b021f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b021f-104">Le tableau de réserve est une table de prise en charge qui stocke des informations sur les divers pools de front-end.</span><span class="sxs-lookup"><span data-stu-id="b021f-104">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="b021f-105">Chaque enregistrement de la table représente un pool.</span><span class="sxs-lookup"><span data-stu-id="b021f-105">Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b021f-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="b021f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b021f-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="b021f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b021f-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="b021f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b021f-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="b021f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b021f-110"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="b021f-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b021f-111">int</span><span class="sxs-lookup"><span data-stu-id="b021f-111">int</span></span></p></td>
<td><p><span data-ttu-id="b021f-112">Principal</span><span class="sxs-lookup"><span data-stu-id="b021f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b021f-113">Numéro unique identifiant ce pool.</span><span class="sxs-lookup"><span data-stu-id="b021f-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b021f-114"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="b021f-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="b021f-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b021f-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b021f-116">Différent </span><span class="sxs-lookup"><span data-stu-id="b021f-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="b021f-117">Nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="b021f-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

