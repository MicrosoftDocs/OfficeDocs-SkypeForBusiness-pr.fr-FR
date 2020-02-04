---
title: 'Lync Server 2013 : Table Devices'
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
ms.openlocfilehash: 381b03fc5680276a64fc327f423f74c6773c2ed3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="42b48-102">Table Devices dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b48-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42b48-103">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="42b48-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="42b48-104">Le tableau appareils est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="42b48-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="42b48-105">Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="42b48-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42b48-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="42b48-106">Column</span></span></th>
<th><span data-ttu-id="42b48-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="42b48-107">Data Type</span></span></th>
<th><span data-ttu-id="42b48-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="42b48-108">Key/Index</span></span></th>
<th><span data-ttu-id="42b48-109">Détails</span><span class="sxs-lookup"><span data-stu-id="42b48-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42b48-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="42b48-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="42b48-111">int</span><span class="sxs-lookup"><span data-stu-id="42b48-111">int</span></span></p></td>
<td><p><span data-ttu-id="42b48-112">Principal</span><span class="sxs-lookup"><span data-stu-id="42b48-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="42b48-113">Numéro unique identifiant cette version matérielle.</span><span class="sxs-lookup"><span data-stu-id="42b48-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b48-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="42b48-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42b48-115">int</span><span class="sxs-lookup"><span data-stu-id="42b48-115">int</span></span></p></td>
<td><p><span data-ttu-id="42b48-116">Externes</span><span class="sxs-lookup"><span data-stu-id="42b48-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42b48-117">Fabricant de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="42b48-117">Manufacturer of this device.</span></span> <span data-ttu-id="42b48-118">Pour plus d’informations, reportez-vous <a href="lync-server-2013-manufacturers-table.md">à la table fabricants dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42b48-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b48-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="42b48-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="42b48-120">int</span><span class="sxs-lookup"><span data-stu-id="42b48-120">int</span></span></p></td>
<td><p><span data-ttu-id="42b48-121">Externes</span><span class="sxs-lookup"><span data-stu-id="42b48-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42b48-122">Version matérielle de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="42b48-122">Hardware version of this device.</span></span> <span data-ttu-id="42b48-123">Pour plus d’informations, voir la <a href="lync-server-2013-hardwareversions-table.md">table HardwareVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42b48-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b48-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="42b48-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="42b48-125">bigint</span><span class="sxs-lookup"><span data-stu-id="42b48-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42b48-126">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="42b48-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

