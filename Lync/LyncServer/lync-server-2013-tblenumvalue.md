---
title: 'Lync Server 2013 : tblEnumValue'
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
ms.openlocfilehash: 4166e25375c7ddd631b1ee7944ac703f21c9ba80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="62a52-102">tblEnumValue dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a52-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62a52-103">_**Dernière modification de la rubrique :** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="62a52-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="62a52-104">tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="62a52-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="62a52-105">Columns</span><span class="sxs-lookup"><span data-stu-id="62a52-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62a52-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="62a52-106">Column</span></span></th>
<th><span data-ttu-id="62a52-107">Type</span><span class="sxs-lookup"><span data-stu-id="62a52-107">Type</span></span></th>
<th><span data-ttu-id="62a52-108">Description</span><span class="sxs-lookup"><span data-stu-id="62a52-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62a52-109">valueID</span><span class="sxs-lookup"><span data-stu-id="62a52-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="62a52-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="62a52-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="62a52-111">ID de la valeur</span><span class="sxs-lookup"><span data-stu-id="62a52-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62a52-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="62a52-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="62a52-113">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="62a52-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="62a52-114">ID de l’attribut</span><span class="sxs-lookup"><span data-stu-id="62a52-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62a52-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="62a52-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="62a52-116">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="62a52-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="62a52-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="62a52-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="62a52-118">Keys</span><span class="sxs-lookup"><span data-stu-id="62a52-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62a52-119">Colonne</span><span class="sxs-lookup"><span data-stu-id="62a52-119">Column</span></span></th>
<th><span data-ttu-id="62a52-120">Description</span><span class="sxs-lookup"><span data-stu-id="62a52-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62a52-121">valueID</span><span class="sxs-lookup"><span data-stu-id="62a52-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="62a52-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="62a52-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62a52-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="62a52-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="62a52-124">Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="62a52-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="62a52-125">Valeurs de la table</span><span class="sxs-lookup"><span data-stu-id="62a52-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62a52-126">valueID</span><span class="sxs-lookup"><span data-stu-id="62a52-126">valueID</span></span></th>
<th><span data-ttu-id="62a52-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="62a52-127">attributeID</span></span></th>
<th><span data-ttu-id="62a52-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="62a52-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62a52-129">n°2</span><span class="sxs-lookup"><span data-stu-id="62a52-129">2</span></span></p></td>
<td><p><span data-ttu-id="62a52-130">0,1</span><span class="sxs-lookup"><span data-stu-id="62a52-130">1</span></span></p></td>
<td><p><span data-ttu-id="62a52-131">privé</span><span class="sxs-lookup"><span data-stu-id="62a52-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62a52-132">3</span><span class="sxs-lookup"><span data-stu-id="62a52-132">3</span></span></p></td>
<td><p><span data-ttu-id="62a52-133">0,1</span><span class="sxs-lookup"><span data-stu-id="62a52-133">1</span></span></p></td>
<td><p><span data-ttu-id="62a52-134">portée</span><span class="sxs-lookup"><span data-stu-id="62a52-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62a52-135">4</span><span class="sxs-lookup"><span data-stu-id="62a52-135">4</span></span></p></td>
<td><p><span data-ttu-id="62a52-136">n°2</span><span class="sxs-lookup"><span data-stu-id="62a52-136">2</span></span></p></td>
<td><p><span data-ttu-id="62a52-137">anormal</span><span class="sxs-lookup"><span data-stu-id="62a52-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62a52-138">disque</span><span class="sxs-lookup"><span data-stu-id="62a52-138">5</span></span></p></td>
<td><p><span data-ttu-id="62a52-139">n°2</span><span class="sxs-lookup"><span data-stu-id="62a52-139">2</span></span></p></td>
<td><p><span data-ttu-id="62a52-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="62a52-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62a52-141">6 </span><span class="sxs-lookup"><span data-stu-id="62a52-141">6</span></span></p></td>
<td><p><span data-ttu-id="62a52-142">0,1</span><span class="sxs-lookup"><span data-stu-id="62a52-142">1</span></span></p></td>
<td><p><span data-ttu-id="62a52-143">libre</span><span class="sxs-lookup"><span data-stu-id="62a52-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="62a52-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62a52-144">See Also</span></span>


[<span data-ttu-id="62a52-145">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a52-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

