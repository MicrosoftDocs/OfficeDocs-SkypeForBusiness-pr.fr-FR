---
title: 'Tableau Lync Server 2013 : IPAddress'
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
ms.openlocfilehash: 6344319fbdf581a5e51a1f61e141833910e9e29f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="9f420-102">Table IPAddress dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f420-102">IPAddress table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f420-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="9f420-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="9f420-104">La table IPAddress mappe les adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="9f420-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="9f420-105">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f420-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f420-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="9f420-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9f420-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="9f420-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9f420-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="9f420-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9f420-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="9f420-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f420-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="9f420-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9f420-111">int</span><span class="sxs-lookup"><span data-stu-id="9f420-111">int</span></span></p></td>
<td><p><span data-ttu-id="9f420-112">Principal</span><span class="sxs-lookup"><span data-stu-id="9f420-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9f420-113">Identificateur unique de l’adresse IP spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9f420-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f420-114"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="9f420-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9f420-115">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="9f420-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="9f420-116">Différent</span><span class="sxs-lookup"><span data-stu-id="9f420-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="9f420-117">Une adresse IP unique (par exemple, 189.168.1.1) qui correspond à IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="9f420-117">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="9f420-118">Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="9f420-118">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

