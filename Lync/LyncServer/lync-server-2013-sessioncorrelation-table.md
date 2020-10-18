---
title: 'Lync Server 2013 : table table sessioncorrelation'
description: 'Lync Server 2013 : table table sessioncorrelation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814b7e8539d89f87e7df60ceb03e70800553fb55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579660"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="8c41c-103">Table table sessioncorrelation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c41c-103">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c41c-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8c41c-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8c41c-105">La table table sessioncorrelation est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="8c41c-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="8c41c-106">Chaque enregistrement représente une corrélation qui est utilisée pour corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="8c41c-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c41c-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="8c41c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8c41c-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="8c41c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8c41c-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="8c41c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8c41c-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="8c41c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c41c-111"><strong>Somme de contrôle</strong></span><span class="sxs-lookup"><span data-stu-id="8c41c-111"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="8c41c-112">int</span><span class="sxs-lookup"><span data-stu-id="8c41c-112">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c41c-113"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="8c41c-113"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8c41c-114">int</span><span class="sxs-lookup"><span data-stu-id="8c41c-114">int</span></span></p></td>
<td><p><span data-ttu-id="8c41c-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="8c41c-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="8c41c-116">Numéro unique identifiant ce serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="8c41c-116">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c41c-117"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="8c41c-117"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="8c41c-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8c41c-118">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8c41c-119">Uniques</span><span class="sxs-lookup"><span data-stu-id="8c41c-119">Unique</span></span></p></td>
<td><p><span data-ttu-id="8c41c-120">Les sessions corrélées auront le même ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="8c41c-120">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c41c-121"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="8c41c-121"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="8c41c-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8c41c-122">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8c41c-123">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="8c41c-123">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

