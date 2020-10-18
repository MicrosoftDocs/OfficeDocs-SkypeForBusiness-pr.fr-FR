---
title: 'Lync Server 2013 : table Device'
description: 'Lync Server 2013 : table Device.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46de64a49eace52d62cbd6384fcae680b5c511b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575640"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="bf349-103">Table Device dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf349-103">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf349-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bf349-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bf349-p101">La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.</span><span class="sxs-lookup"><span data-stu-id="bf349-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf349-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="bf349-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bf349-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="bf349-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bf349-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="bf349-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bf349-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="bf349-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf349-111"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="bf349-111"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bf349-112">int</span><span class="sxs-lookup"><span data-stu-id="bf349-112">int</span></span></p></td>
<td><p><span data-ttu-id="bf349-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="bf349-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="bf349-114">Numéro unique qui identifie ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="bf349-114">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf349-115"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="bf349-115"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="bf349-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bf349-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bf349-117">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="bf349-117">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="bf349-118">Nom du périphérique.</span><span class="sxs-lookup"><span data-stu-id="bf349-118">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf349-119"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="bf349-119"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="bf349-120">légèrement</span><span class="sxs-lookup"><span data-stu-id="bf349-120">bit</span></span></p></td>
<td><p><span data-ttu-id="bf349-121">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="bf349-121">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="bf349-p102">Type de périphérique. 1 correspond à un périphérique de capture, 0 à un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="bf349-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

