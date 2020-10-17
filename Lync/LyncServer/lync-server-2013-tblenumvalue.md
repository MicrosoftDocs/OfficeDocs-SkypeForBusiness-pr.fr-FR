---
title: 'Lync Server 2013 : tblEnumValue'
description: 'Lync Server 2013 : tblEnumValue.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571370"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="0361c-103">tblEnumValue dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0361c-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0361c-104">_**Dernière modification de la rubrique :** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="0361c-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="0361c-105">tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="0361c-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="0361c-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="0361c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0361c-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="0361c-107">Column</span></span></th>
<th><span data-ttu-id="0361c-108">Type</span><span class="sxs-lookup"><span data-stu-id="0361c-108">Type</span></span></th>
<th><span data-ttu-id="0361c-109">Description</span><span class="sxs-lookup"><span data-stu-id="0361c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0361c-110">valueID</span><span class="sxs-lookup"><span data-stu-id="0361c-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="0361c-111">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="0361c-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0361c-112">ID de la valeur</span><span class="sxs-lookup"><span data-stu-id="0361c-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0361c-113">attributeID</span><span class="sxs-lookup"><span data-stu-id="0361c-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="0361c-114">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="0361c-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0361c-115">ID de l’attribut</span><span class="sxs-lookup"><span data-stu-id="0361c-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0361c-116">attributeValue</span><span class="sxs-lookup"><span data-stu-id="0361c-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="0361c-117">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="0361c-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0361c-118">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="0361c-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="0361c-119">Keys</span><span class="sxs-lookup"><span data-stu-id="0361c-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0361c-120">Colonne</span><span class="sxs-lookup"><span data-stu-id="0361c-120">Column</span></span></th>
<th><span data-ttu-id="0361c-121">Description</span><span class="sxs-lookup"><span data-stu-id="0361c-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0361c-122">valueID</span><span class="sxs-lookup"><span data-stu-id="0361c-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="0361c-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0361c-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0361c-124">attributeID</span><span class="sxs-lookup"><span data-stu-id="0361c-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="0361c-125">Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="0361c-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="0361c-126">Valeurs de la table</span><span class="sxs-lookup"><span data-stu-id="0361c-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0361c-127">valueID</span><span class="sxs-lookup"><span data-stu-id="0361c-127">valueID</span></span></th>
<th><span data-ttu-id="0361c-128">attributeID</span><span class="sxs-lookup"><span data-stu-id="0361c-128">attributeID</span></span></th>
<th><span data-ttu-id="0361c-129">attributeValue</span><span class="sxs-lookup"><span data-stu-id="0361c-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0361c-130">n°2</span><span class="sxs-lookup"><span data-stu-id="0361c-130">2</span></span></p></td>
<td><p><span data-ttu-id="0361c-131">0,1</span><span class="sxs-lookup"><span data-stu-id="0361c-131">1</span></span></p></td>
<td><p><span data-ttu-id="0361c-132">privé</span><span class="sxs-lookup"><span data-stu-id="0361c-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0361c-133">3</span><span class="sxs-lookup"><span data-stu-id="0361c-133">3</span></span></p></td>
<td><p><span data-ttu-id="0361c-134">0,1</span><span class="sxs-lookup"><span data-stu-id="0361c-134">1</span></span></p></td>
<td><p><span data-ttu-id="0361c-135">portée</span><span class="sxs-lookup"><span data-stu-id="0361c-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0361c-136">4 </span><span class="sxs-lookup"><span data-stu-id="0361c-136">4</span></span></p></td>
<td><p><span data-ttu-id="0361c-137">n°2</span><span class="sxs-lookup"><span data-stu-id="0361c-137">2</span></span></p></td>
<td><p><span data-ttu-id="0361c-138">anormal</span><span class="sxs-lookup"><span data-stu-id="0361c-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0361c-139">5 </span><span class="sxs-lookup"><span data-stu-id="0361c-139">5</span></span></p></td>
<td><p><span data-ttu-id="0361c-140">n°2</span><span class="sxs-lookup"><span data-stu-id="0361c-140">2</span></span></p></td>
<td><p><span data-ttu-id="0361c-141">Auditorium</span><span class="sxs-lookup"><span data-stu-id="0361c-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0361c-142">6 </span><span class="sxs-lookup"><span data-stu-id="0361c-142">6</span></span></p></td>
<td><p><span data-ttu-id="0361c-143">0,1</span><span class="sxs-lookup"><span data-stu-id="0361c-143">1</span></span></p></td>
<td><p><span data-ttu-id="0361c-144">libre</span><span class="sxs-lookup"><span data-stu-id="0361c-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0361c-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0361c-145">See Also</span></span>


[<span data-ttu-id="0361c-146">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0361c-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

