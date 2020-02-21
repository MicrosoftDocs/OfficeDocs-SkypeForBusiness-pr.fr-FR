---
title: 'Lync Server 2013 : table ErrorCategory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3052aa95aa6cd846717aa98c5778531aeee6f7e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="f3d6f-102">Table ErrorCategory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3d6f-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3d6f-103">_**Dernière modification de la rubrique :** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="f3d6f-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="f3d6f-104">La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3d6f-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="f3d6f-105">Par défaut, Lync Server 2013 utilise les classifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="f3d6f-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="f3d6f-106">0 : réussite</span><span class="sxs-lookup"><span data-stu-id="f3d6f-106">0 -- Success</span></span>

  - <span data-ttu-id="f3d6f-107">1-échec ATTENDU</span><span class="sxs-lookup"><span data-stu-id="f3d6f-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="f3d6f-108">2 : échec inattendu</span><span class="sxs-lookup"><span data-stu-id="f3d6f-108">2 – Unexpected failure</span></span>

<span data-ttu-id="f3d6f-109">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3d6f-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3d6f-110">Colonne</span><span class="sxs-lookup"><span data-stu-id="f3d6f-110">Column</span></span></th>
<th><span data-ttu-id="f3d6f-111">Type de données</span><span class="sxs-lookup"><span data-stu-id="f3d6f-111">Data Type</span></span></th>
<th><span data-ttu-id="f3d6f-112">Clé/index</span><span class="sxs-lookup"><span data-stu-id="f3d6f-112">Key/Index</span></span></th>
<th><span data-ttu-id="f3d6f-113">Détails</span><span class="sxs-lookup"><span data-stu-id="f3d6f-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3d6f-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="f3d6f-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3d6f-115">entier très petit</span><span class="sxs-lookup"><span data-stu-id="f3d6f-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f3d6f-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="f3d6f-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3d6f-117">Identificateur unique pour la classification.</span><span class="sxs-lookup"><span data-stu-id="f3d6f-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d6f-118"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="f3d6f-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="f3d6f-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3d6f-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f3d6f-p102">Valeur et nom convivial attribués à la classification. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="f3d6f-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f3d6f-122">0 : réussite</span><span class="sxs-lookup"><span data-stu-id="f3d6f-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="f3d6f-123">1-échec ATTENDU</span><span class="sxs-lookup"><span data-stu-id="f3d6f-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="f3d6f-124">2 : échec inattendu</span><span class="sxs-lookup"><span data-stu-id="f3d6f-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

