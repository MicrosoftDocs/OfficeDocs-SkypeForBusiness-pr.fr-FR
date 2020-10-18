---
title: 'Lync Server 2013 : table Devices'
description: 'Lync Server 2013 : table Devices.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763e1788e2874f9f9831c089ffe8fa077621b030
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576240"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="ff945-103">Table Devices dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff945-103">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff945-104">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="ff945-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="ff945-p101">La table Devices est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="ff945-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff945-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="ff945-107">Column</span></span></th>
<th><span data-ttu-id="ff945-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="ff945-108">Data Type</span></span></th>
<th><span data-ttu-id="ff945-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="ff945-109">Key/Index</span></span></th>
<th><span data-ttu-id="ff945-110">Détails</span><span class="sxs-lookup"><span data-stu-id="ff945-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff945-111"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="ff945-111"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff945-112">int</span><span class="sxs-lookup"><span data-stu-id="ff945-112">int</span></span></p></td>
<td><p><span data-ttu-id="ff945-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="ff945-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff945-114">Numéro unique identifiant cette version du matériel.</span><span class="sxs-lookup"><span data-stu-id="ff945-114">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff945-115"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="ff945-115"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff945-116">int</span><span class="sxs-lookup"><span data-stu-id="ff945-116">int</span></span></p></td>
<td><p><span data-ttu-id="ff945-117">Etranger</span><span class="sxs-lookup"><span data-stu-id="ff945-117">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff945-118">Fabricant de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="ff945-118">Manufacturer of this device.</span></span> <span data-ttu-id="ff945-119">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-manufacturers-table.md">table constructeurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ff945-119">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff945-120"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ff945-120"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff945-121">int</span><span class="sxs-lookup"><span data-stu-id="ff945-121">int</span></span></p></td>
<td><p><span data-ttu-id="ff945-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="ff945-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff945-123">Version du matériel de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="ff945-123">Hardware version of this device.</span></span> <span data-ttu-id="ff945-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-hardwareversions-table.md">table table hardwareversions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ff945-124">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff945-125"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="ff945-125"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="ff945-126">comportant</span><span class="sxs-lookup"><span data-stu-id="ff945-126">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff945-127">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="ff945-127">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

