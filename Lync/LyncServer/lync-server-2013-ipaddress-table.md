---
title: 'Lync Server 2013 : IPAddress table'
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
ms.openlocfilehash: 6d23e9aba844cb03779b220ed8d898a2e7664891
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514171"
---
# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="a0baf-102">IPAddress table dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0baf-102">IPAddress table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0baf-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a0baf-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a0baf-104">La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="a0baf-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a0baf-105">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0baf-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0baf-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="a0baf-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a0baf-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="a0baf-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a0baf-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="a0baf-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a0baf-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="a0baf-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0baf-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="a0baf-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a0baf-111">int</span><span class="sxs-lookup"><span data-stu-id="a0baf-111">int</span></span></p></td>
<td><p><span data-ttu-id="a0baf-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="a0baf-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0baf-113">Identificateur unique pour l’adresse IP spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a0baf-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0baf-114"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a0baf-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a0baf-115">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="a0baf-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="a0baf-116">Uniques</span><span class="sxs-lookup"><span data-stu-id="a0baf-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="a0baf-p102">Adresse IP unique (par exemple, 189.168.1.1) qui est mappée à IpAddressKey. Il peut d’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="a0baf-p102">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

