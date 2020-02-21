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
ms.openlocfilehash: 8906519253445ea67f3fa674a9a1315f8f6cf18b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="d9c72-102">Table Devices dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9c72-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9c72-103">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="d9c72-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="d9c72-p101">La table Devices est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="d9c72-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9c72-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="d9c72-106">Column</span></span></th>
<th><span data-ttu-id="d9c72-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="d9c72-107">Data Type</span></span></th>
<th><span data-ttu-id="d9c72-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="d9c72-108">Key/Index</span></span></th>
<th><span data-ttu-id="d9c72-109">Détails</span><span class="sxs-lookup"><span data-stu-id="d9c72-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9c72-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="d9c72-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9c72-111">int</span><span class="sxs-lookup"><span data-stu-id="d9c72-111">int</span></span></p></td>
<td><p><span data-ttu-id="d9c72-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="d9c72-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d9c72-113">Numéro unique identifiant cette version du matériel.</span><span class="sxs-lookup"><span data-stu-id="d9c72-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9c72-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="d9c72-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9c72-115">int</span><span class="sxs-lookup"><span data-stu-id="d9c72-115">int</span></span></p></td>
<td><p><span data-ttu-id="d9c72-116">Etranger</span><span class="sxs-lookup"><span data-stu-id="d9c72-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d9c72-117">Fabricant de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="d9c72-117">Manufacturer of this device.</span></span> <span data-ttu-id="d9c72-118">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-manufacturers-table.md">table constructeurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9c72-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9c72-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="d9c72-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9c72-120">int</span><span class="sxs-lookup"><span data-stu-id="d9c72-120">int</span></span></p></td>
<td><p><span data-ttu-id="d9c72-121">Etranger</span><span class="sxs-lookup"><span data-stu-id="d9c72-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d9c72-122">Version du matériel de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="d9c72-122">Hardware version of this device.</span></span> <span data-ttu-id="d9c72-123">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-hardwareversions-table.md">table table hardwareversions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9c72-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9c72-124"><strong>Mac</strong></span><span class="sxs-lookup"><span data-stu-id="d9c72-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="d9c72-125">comportant</span><span class="sxs-lookup"><span data-stu-id="d9c72-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d9c72-126">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="d9c72-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

