---
title: 'Lync Server 2013 : table DeviceDriver'
description: 'Lync Server 2013 : table DeviceDriver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d81e2e27ff5196112c6057c429f924e5b1c3e4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565970"
---
# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="8e5b1-103">Table DeviceDriver dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e5b1-103">DeviceDriver table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e5b1-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8e5b1-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8e5b1-p101">La table DeviceDriver est une table de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou par un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="8e5b1-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e5b1-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="8e5b1-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8e5b1-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="8e5b1-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8e5b1-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="8e5b1-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8e5b1-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="8e5b1-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e5b1-111"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="8e5b1-111"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8e5b1-112">int</span><span class="sxs-lookup"><span data-stu-id="8e5b1-112">int</span></span></p></td>
<td><p><span data-ttu-id="8e5b1-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="8e5b1-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="8e5b1-114">Numéro unique d’identification de cet enregistrement de pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="8e5b1-114">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e5b1-115"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="8e5b1-115"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="8e5b1-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e5b1-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e5b1-117">exclusive</span><span class="sxs-lookup"><span data-stu-id="8e5b1-117">unique</span></span></p></td>
<td><p><span data-ttu-id="8e5b1-118">Nom du pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="8e5b1-118">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

