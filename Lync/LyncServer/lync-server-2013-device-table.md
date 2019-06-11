---
title: 'Lync Server 2013 : Table Device'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974898f6c3fa96dd9356a0a9eed1e3fab09d288b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="50ee0-102">Table Device dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50ee0-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50ee0-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="50ee0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="50ee0-104">La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu.</span><span class="sxs-lookup"><span data-stu-id="50ee0-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="50ee0-105">Chaque enregistrement de la table représente un appareil.</span><span class="sxs-lookup"><span data-stu-id="50ee0-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50ee0-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="50ee0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="50ee0-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="50ee0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="50ee0-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="50ee0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="50ee0-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="50ee0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50ee0-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="50ee0-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="50ee0-111">int</span><span class="sxs-lookup"><span data-stu-id="50ee0-111">int</span></span></p></td>
<td><p><span data-ttu-id="50ee0-112">Principal</span><span class="sxs-lookup"><span data-stu-id="50ee0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="50ee0-113">Numéro unique identifiant cet appareil.</span><span class="sxs-lookup"><span data-stu-id="50ee0-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50ee0-114"><strong>Périphérique</strong></span><span class="sxs-lookup"><span data-stu-id="50ee0-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="50ee0-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="50ee0-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="50ee0-116">Nom_unité + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="50ee0-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="50ee0-117">Nom de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="50ee0-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50ee0-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="50ee0-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="50ee0-119">bit</span><span class="sxs-lookup"><span data-stu-id="50ee0-119">bit</span></span></p></td>
<td><p><span data-ttu-id="50ee0-120">Nom_unité + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="50ee0-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="50ee0-121">Type d’appareil.</span><span class="sxs-lookup"><span data-stu-id="50ee0-121">Device type.</span></span> <span data-ttu-id="50ee0-122">1 est un appareil de capture; 0 est un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="50ee0-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

