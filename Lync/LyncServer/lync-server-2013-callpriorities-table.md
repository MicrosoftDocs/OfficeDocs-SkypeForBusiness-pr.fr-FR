---
title: 'Lync Server 2013 : table table callpriorities'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b44b48cbe23ae004211e4ca6f29b1afc434af1e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514831"
---
# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="5a56f-102">Table table callpriorities dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a56f-102">CallPriorities table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a56f-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5a56f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5a56f-104">La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, par exemple « très urgent », « urgent » ou « normal ».</span><span class="sxs-lookup"><span data-stu-id="5a56f-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a56f-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="5a56f-105">Column</span></span></th>
<th><span data-ttu-id="5a56f-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="5a56f-106">Data Type</span></span></th>
<th><span data-ttu-id="5a56f-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="5a56f-107">Key/Index</span></span></th>
<th><span data-ttu-id="5a56f-108">Détails</span><span class="sxs-lookup"><span data-stu-id="5a56f-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a56f-109"><strong>PriorityId</strong></span><span class="sxs-lookup"><span data-stu-id="5a56f-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="5a56f-110">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5a56f-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5a56f-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="5a56f-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a56f-112"><strong>Priorité</strong></span><span class="sxs-lookup"><span data-stu-id="5a56f-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="5a56f-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5a56f-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a56f-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="5a56f-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a56f-115">0 - Inconnu</span><span class="sxs-lookup"><span data-stu-id="5a56f-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="5a56f-116">1 – Non urgent</span><span class="sxs-lookup"><span data-stu-id="5a56f-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="5a56f-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="5a56f-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="5a56f-118">3 - Urgent</span><span class="sxs-lookup"><span data-stu-id="5a56f-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="5a56f-119">4 - Très urgent</span><span class="sxs-lookup"><span data-stu-id="5a56f-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

