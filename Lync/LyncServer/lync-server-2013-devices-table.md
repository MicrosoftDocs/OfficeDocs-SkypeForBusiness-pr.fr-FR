---
title: 'Lync Server 2013 : table Devices'
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
ms.openlocfilehash: c5fdc4c3b20bdd60d2c8013b79a15bdfd30b56af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536931"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="93825-102">Table Devices dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93825-102">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93825-103">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="93825-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="93825-p101">La table Devices est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="93825-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93825-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="93825-106">Column</span></span></th>
<th><span data-ttu-id="93825-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="93825-107">Data Type</span></span></th>
<th><span data-ttu-id="93825-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="93825-108">Key/Index</span></span></th>
<th><span data-ttu-id="93825-109">Détails</span><span class="sxs-lookup"><span data-stu-id="93825-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93825-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="93825-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="93825-111">int</span><span class="sxs-lookup"><span data-stu-id="93825-111">int</span></span></p></td>
<td><p><span data-ttu-id="93825-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="93825-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="93825-113">Numéro unique identifiant cette version du matériel.</span><span class="sxs-lookup"><span data-stu-id="93825-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93825-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="93825-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="93825-115">int</span><span class="sxs-lookup"><span data-stu-id="93825-115">int</span></span></p></td>
<td><p><span data-ttu-id="93825-116">Etranger</span><span class="sxs-lookup"><span data-stu-id="93825-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="93825-117">Fabricant de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="93825-117">Manufacturer of this device.</span></span> <span data-ttu-id="93825-118">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-manufacturers-table.md">table constructeurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="93825-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93825-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="93825-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="93825-120">int</span><span class="sxs-lookup"><span data-stu-id="93825-120">int</span></span></p></td>
<td><p><span data-ttu-id="93825-121">Etranger</span><span class="sxs-lookup"><span data-stu-id="93825-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="93825-122">Version du matériel de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="93825-122">Hardware version of this device.</span></span> <span data-ttu-id="93825-123">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-hardwareversions-table.md">table table hardwareversions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="93825-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93825-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="93825-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="93825-125">comportant</span><span class="sxs-lookup"><span data-stu-id="93825-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93825-126">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="93825-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

