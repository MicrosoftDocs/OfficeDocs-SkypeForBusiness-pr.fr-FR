---
title: 'Lync Server 2013 : IPAddress table'
description: 'Lync Server 2013 : IPAddress table.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d987281fc310a3a179fa99f2aae51b0764349dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575010"
---
# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="98878-103">IPAddress table dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98878-103">IPAddress table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98878-104">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="98878-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="98878-105">La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="98878-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="98878-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98878-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98878-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="98878-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="98878-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="98878-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="98878-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="98878-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="98878-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="98878-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98878-111"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="98878-111"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="98878-112">int</span><span class="sxs-lookup"><span data-stu-id="98878-112">int</span></span></p></td>
<td><p><span data-ttu-id="98878-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="98878-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="98878-114">Identificateur unique pour l’adresse IP spécifiée.</span><span class="sxs-lookup"><span data-stu-id="98878-114">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98878-115"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="98878-115"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="98878-116">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="98878-116">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="98878-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="98878-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="98878-p102">Adresse IP unique (par exemple, 189.168.1.1) qui est mappée à IpAddressKey. Il peut d’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="98878-p102">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

