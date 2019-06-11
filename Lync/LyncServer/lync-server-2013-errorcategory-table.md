---
title: 'Tableau Lync Server 2013: ErrorCategory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9bd9cebf26a147b00873c17372eca77f0a11f2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="b7ab7-102">Table ErrorCategory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ab7-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7ab7-103">_**Dernière modification de la rubrique:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="b7ab7-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="b7ab7-104">La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7ab7-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="b7ab7-105">Par défaut, Lync Server 2013 utilise les classifications suivantes:</span><span class="sxs-lookup"><span data-stu-id="b7ab7-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="b7ab7-106">0--succès</span><span class="sxs-lookup"><span data-stu-id="b7ab7-106">0 -- Success</span></span>

  - <span data-ttu-id="b7ab7-107">1-échec imprévu</span><span class="sxs-lookup"><span data-stu-id="b7ab7-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="b7ab7-108">2-échec inattendu</span><span class="sxs-lookup"><span data-stu-id="b7ab7-108">2 – Unexpected failure</span></span>

<span data-ttu-id="b7ab7-109">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7ab7-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7ab7-110">Colonne</span><span class="sxs-lookup"><span data-stu-id="b7ab7-110">Column</span></span></th>
<th><span data-ttu-id="b7ab7-111">Type de données</span><span class="sxs-lookup"><span data-stu-id="b7ab7-111">Data Type</span></span></th>
<th><span data-ttu-id="b7ab7-112">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="b7ab7-112">Key/Index</span></span></th>
<th><span data-ttu-id="b7ab7-113">Détails</span><span class="sxs-lookup"><span data-stu-id="b7ab7-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7ab7-114"><strong>RéfCatégorie</strong></span><span class="sxs-lookup"><span data-stu-id="b7ab7-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="b7ab7-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7ab7-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b7ab7-116">Principal</span><span class="sxs-lookup"><span data-stu-id="b7ab7-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b7ab7-117">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="b7ab7-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7ab7-118"><strong>Nom</strong></span><span class="sxs-lookup"><span data-stu-id="b7ab7-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="b7ab7-119">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7ab7-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7ab7-120">Valeur et nom convivial attribués à la classification.</span><span class="sxs-lookup"><span data-stu-id="b7ab7-120">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="b7ab7-121">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="b7ab7-121">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b7ab7-122">0--succès</span><span class="sxs-lookup"><span data-stu-id="b7ab7-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="b7ab7-123">1-échec imprévu</span><span class="sxs-lookup"><span data-stu-id="b7ab7-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="b7ab7-124">2-échec inattendu</span><span class="sxs-lookup"><span data-stu-id="b7ab7-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

