---
title: 'Lync Server 2013 : Table Devices'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="b9617-102">Table Devices dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9617-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9617-103">_**Dernière modification de la rubrique:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="b9617-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="b9617-104">Le tableau appareils est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="b9617-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="b9617-105">Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="b9617-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9617-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="b9617-106">Column</span></span></th>
<th><span data-ttu-id="b9617-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="b9617-107">Data Type</span></span></th>
<th><span data-ttu-id="b9617-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="b9617-108">Key/Index</span></span></th>
<th><span data-ttu-id="b9617-109">Détails</span><span class="sxs-lookup"><span data-stu-id="b9617-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9617-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="b9617-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9617-111">int</span><span class="sxs-lookup"><span data-stu-id="b9617-111">int</span></span></p></td>
<td><p><span data-ttu-id="b9617-112">Principal</span><span class="sxs-lookup"><span data-stu-id="b9617-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b9617-113">Numéro unique identifiant cette version matérielle.</span><span class="sxs-lookup"><span data-stu-id="b9617-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9617-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="b9617-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9617-115">int</span><span class="sxs-lookup"><span data-stu-id="b9617-115">int</span></span></p></td>
<td><p><span data-ttu-id="b9617-116">Externes</span><span class="sxs-lookup"><span data-stu-id="b9617-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9617-117">Fabricant de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="b9617-117">Manufacturer of this device.</span></span> <span data-ttu-id="b9617-118">Pour plus d’informations, reportez-vous <a href="lync-server-2013-manufacturers-table.md">à la table fabricants dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b9617-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9617-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="b9617-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9617-120">int</span><span class="sxs-lookup"><span data-stu-id="b9617-120">int</span></span></p></td>
<td><p><span data-ttu-id="b9617-121">Externes</span><span class="sxs-lookup"><span data-stu-id="b9617-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9617-122">Version matérielle de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="b9617-122">Hardware version of this device.</span></span> <span data-ttu-id="b9617-123">Pour plus d’informations, voir la <a href="lync-server-2013-hardwareversions-table.md">table HardwareVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b9617-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9617-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="b9617-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="b9617-125">bigint</span><span class="sxs-lookup"><span data-stu-id="b9617-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9617-126">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="b9617-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

