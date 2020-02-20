---
title: 'Lync Server 2013 : table de sous-réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cdf1ded3a63d790db78476b91a458d07921200a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="2d7f8-102">Table de sous-réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d7f8-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d7f8-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2d7f8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2d7f8-p101">La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="2d7f8-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d7f8-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="2d7f8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2d7f8-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="2d7f8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2d7f8-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="2d7f8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2d7f8-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="2d7f8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d7f8-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="2d7f8-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="2d7f8-111">int</span><span class="sxs-lookup"><span data-stu-id="2d7f8-111">int</span></span></p></td>
<td><p><span data-ttu-id="2d7f8-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2d7f8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2d7f8-113">Représentation sous forme d’entier de l’adresse IP de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="2d7f8-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d7f8-114"><strong>Masque</strong></span><span class="sxs-lookup"><span data-stu-id="2d7f8-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="2d7f8-115">int</span><span class="sxs-lookup"><span data-stu-id="2d7f8-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d7f8-116">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="2d7f8-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d7f8-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="2d7f8-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2d7f8-118">int</span><span class="sxs-lookup"><span data-stu-id="2d7f8-118">int</span></span></p></td>
<td><p><span data-ttu-id="2d7f8-119">Etranger</span><span class="sxs-lookup"><span data-stu-id="2d7f8-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2d7f8-120">Référencé à partir de la <a href="lync-server-2013-usersite-table.md">table UserSite dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2d7f8-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d7f8-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="2d7f8-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="2d7f8-122">nvarchar</span><span class="sxs-lookup"><span data-stu-id="2d7f8-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d7f8-123">Description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="2d7f8-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

