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
ms.openlocfilehash: 19c52c923a1180b475afea764717b0af85a90985
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="5da48-102">Table de sous-réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5da48-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5da48-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5da48-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5da48-p101">La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="5da48-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5da48-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="5da48-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5da48-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="5da48-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5da48-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="5da48-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5da48-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="5da48-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5da48-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="5da48-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="5da48-111">int</span><span class="sxs-lookup"><span data-stu-id="5da48-111">int</span></span></p></td>
<td><p><span data-ttu-id="5da48-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="5da48-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5da48-113">Représentation sous forme d’entier de l’adresse IP de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="5da48-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da48-114"><strong>Masque</strong></span><span class="sxs-lookup"><span data-stu-id="5da48-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="5da48-115">int</span><span class="sxs-lookup"><span data-stu-id="5da48-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5da48-116">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="5da48-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da48-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="5da48-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5da48-118">int</span><span class="sxs-lookup"><span data-stu-id="5da48-118">int</span></span></p></td>
<td><p><span data-ttu-id="5da48-119">Etranger</span><span class="sxs-lookup"><span data-stu-id="5da48-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5da48-120">Référencé à partir de la <a href="lync-server-2013-usersite-table.md">table UserSite dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5da48-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da48-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5da48-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5da48-122">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5da48-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5da48-123">Description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="5da48-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

