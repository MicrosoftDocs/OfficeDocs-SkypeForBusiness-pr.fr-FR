---
title: 'Lync Server 2013 : table NetworkConnectionDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58935c4043246a0c5a6c5d4d9cde19ca27627dcc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="d2424-102">Table NetworkConnectionDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2424-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2424-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d2424-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d2424-104">La table NetworkConnectionDetail mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données Qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="d2424-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d2424-105">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2424-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2424-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="d2424-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d2424-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="d2424-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d2424-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="d2424-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d2424-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d2424-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2424-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="d2424-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d2424-111">entier très petit</span><span class="sxs-lookup"><span data-stu-id="d2424-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d2424-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="d2424-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d2424-113">Identificateur unique du type de connexion réseau.</span><span class="sxs-lookup"><span data-stu-id="d2424-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2424-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="d2424-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="d2424-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d2424-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d2424-116">Uniques</span><span class="sxs-lookup"><span data-stu-id="d2424-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="d2424-p102">Type de connexion réseau correspondant à la valeur NetworkConnectionDetailKey. Les valeurs autorisées sont les suivantes :
</span><span class="sxs-lookup"><span data-stu-id="d2424-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="d2424-119">0 -- Câblé</span><span class="sxs-lookup"><span data-stu-id="d2424-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="d2424-120">1 -- WiFi</span><span class="sxs-lookup"><span data-stu-id="d2424-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="d2424-121">2 -- Ethernet</span><span class="sxs-lookup"><span data-stu-id="d2424-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

