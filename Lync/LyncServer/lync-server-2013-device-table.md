---
title: 'Lync Server 2013 : table Device'
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
ms.openlocfilehash: 1040642874d2963292744eb2543c9ee265440fd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="d980a-102">Table Device dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d980a-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d980a-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d980a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d980a-p101">La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.</span><span class="sxs-lookup"><span data-stu-id="d980a-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d980a-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="d980a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d980a-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="d980a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d980a-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="d980a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d980a-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d980a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d980a-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="d980a-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d980a-111">int</span><span class="sxs-lookup"><span data-stu-id="d980a-111">int</span></span></p></td>
<td><p><span data-ttu-id="d980a-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="d980a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d980a-113">Numéro unique qui identifie ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="d980a-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d980a-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="d980a-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="d980a-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d980a-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d980a-116">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="d980a-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="d980a-117">Nom du périphérique.</span><span class="sxs-lookup"><span data-stu-id="d980a-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d980a-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="d980a-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="d980a-119">légèrement</span><span class="sxs-lookup"><span data-stu-id="d980a-119">bit</span></span></p></td>
<td><p><span data-ttu-id="d980a-120">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="d980a-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="d980a-p102">Type de périphérique. 1 correspond à un périphérique de capture, 0 à un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="d980a-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

