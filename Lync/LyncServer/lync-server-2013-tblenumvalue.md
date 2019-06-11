---
title: 'Lync Server 2013 : tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="a650a-102">tblEnumValue dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a650a-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a650a-103">_**Dernière modification de la rubrique:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="a650a-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="a650a-104">tblEnumValue est une table codée en dur qui contient les valeurs de visibilité et de comportement des attributs qui sont utilisés dans la table de nœud.</span><span class="sxs-lookup"><span data-stu-id="a650a-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="a650a-105">Celles</span><span class="sxs-lookup"><span data-stu-id="a650a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a650a-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="a650a-106">Column</span></span></th>
<th><span data-ttu-id="a650a-107">Type</span><span class="sxs-lookup"><span data-stu-id="a650a-107">Type</span></span></th>
<th><span data-ttu-id="a650a-108">Description</span><span class="sxs-lookup"><span data-stu-id="a650a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a650a-109">valueID</span><span class="sxs-lookup"><span data-stu-id="a650a-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="a650a-110">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="a650a-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a650a-111">ID de la valeur.</span><span class="sxs-lookup"><span data-stu-id="a650a-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a650a-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="a650a-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="a650a-113">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="a650a-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a650a-114">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="a650a-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a650a-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="a650a-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="a650a-116">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="a650a-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a650a-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="a650a-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a650a-118">Permettent</span><span class="sxs-lookup"><span data-stu-id="a650a-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a650a-119">Colonne</span><span class="sxs-lookup"><span data-stu-id="a650a-119">Column</span></span></th>
<th><span data-ttu-id="a650a-120">Description</span><span class="sxs-lookup"><span data-stu-id="a650a-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a650a-121">valueID</span><span class="sxs-lookup"><span data-stu-id="a650a-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="a650a-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a650a-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a650a-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="a650a-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="a650a-124">Clé étrangère avec recherche dans la table tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="a650a-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="a650a-125">Valeurs de table</span><span class="sxs-lookup"><span data-stu-id="a650a-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a650a-126">valueID</span><span class="sxs-lookup"><span data-stu-id="a650a-126">valueID</span></span></th>
<th><span data-ttu-id="a650a-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="a650a-127">attributeID</span></span></th>
<th><span data-ttu-id="a650a-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="a650a-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a650a-129">2</span><span class="sxs-lookup"><span data-stu-id="a650a-129">2</span></span></p></td>
<td><p><span data-ttu-id="a650a-130">1</span><span class="sxs-lookup"><span data-stu-id="a650a-130">1</span></span></p></td>
<td><p><span data-ttu-id="a650a-131">privé</span><span class="sxs-lookup"><span data-stu-id="a650a-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a650a-132">3</span><span class="sxs-lookup"><span data-stu-id="a650a-132">3</span></span></p></td>
<td><p><span data-ttu-id="a650a-133">1</span><span class="sxs-lookup"><span data-stu-id="a650a-133">1</span></span></p></td>
<td><p><span data-ttu-id="a650a-134">hors</span><span class="sxs-lookup"><span data-stu-id="a650a-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a650a-135">4</span><span class="sxs-lookup"><span data-stu-id="a650a-135">4</span></span></p></td>
<td><p><span data-ttu-id="a650a-136">2</span><span class="sxs-lookup"><span data-stu-id="a650a-136">2</span></span></p></td>
<td><p><span data-ttu-id="a650a-137">normalement</span><span class="sxs-lookup"><span data-stu-id="a650a-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a650a-138">5</span><span class="sxs-lookup"><span data-stu-id="a650a-138">5</span></span></p></td>
<td><p><span data-ttu-id="a650a-139">2</span><span class="sxs-lookup"><span data-stu-id="a650a-139">2</span></span></p></td>
<td><p><span data-ttu-id="a650a-140">Conférence</span><span class="sxs-lookup"><span data-stu-id="a650a-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a650a-141">6</span><span class="sxs-lookup"><span data-stu-id="a650a-141">6</span></span></p></td>
<td><p><span data-ttu-id="a650a-142">1</span><span class="sxs-lookup"><span data-stu-id="a650a-142">1</span></span></p></td>
<td><p><span data-ttu-id="a650a-143">ouvre</span><span class="sxs-lookup"><span data-stu-id="a650a-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a650a-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a650a-144">See Also</span></span>


[<span data-ttu-id="a650a-145">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a650a-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

