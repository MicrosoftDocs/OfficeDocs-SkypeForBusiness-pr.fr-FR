---
title: 'Lync Server 2013 : Table Subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20318d0ed2f487efccda81936b113044f75e2618
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="9c833-102">Table Subnet dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c833-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c833-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9c833-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9c833-104">La table de sous-réseau est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9c833-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="9c833-105">Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="9c833-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c833-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="9c833-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9c833-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="9c833-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9c833-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="9c833-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9c833-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="9c833-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c833-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="9c833-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="9c833-111">int</span><span class="sxs-lookup"><span data-stu-id="9c833-111">int</span></span></p></td>
<td><p><span data-ttu-id="9c833-112">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="9c833-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9c833-113">Représentation entière de l’adresse IP du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="9c833-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c833-114"><strong>Masque_sous_réseau</strong></span><span class="sxs-lookup"><span data-stu-id="9c833-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="9c833-115">int</span><span class="sxs-lookup"><span data-stu-id="9c833-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9c833-116">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="9c833-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c833-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="9c833-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9c833-118">int</span><span class="sxs-lookup"><span data-stu-id="9c833-118">int</span></span></p></td>
<td><p><span data-ttu-id="9c833-119">Externes</span><span class="sxs-lookup"><span data-stu-id="9c833-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9c833-120">Fait référence à partir de la <a href="lync-server-2013-usersite-table.md">table UserSite dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9c833-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c833-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="9c833-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="9c833-122">nvarchar</span><span class="sxs-lookup"><span data-stu-id="9c833-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9c833-123">Description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="9c833-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

