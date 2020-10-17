---
title: 'Lync Server 2013 : table ConferenceJoinTimeThresholds'
description: 'Lync Server 2013 : table ConferenceJoinTimeThresholds.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561670"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="609a5-103">Table ConferenceJoinTimeThresholds dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="609a5-103">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="609a5-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="609a5-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="609a5-p101">La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse du temps de connexion à la conférence. Ce rapport récapitule le temps nécessaire aux utilisateurs pour se joindre à une conférence. Ces valeurs de temps représentent à la fois une moyenne et l’une des catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="609a5-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="609a5-107">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="609a5-107">Less than 2 seconds.</span></span>

  - <span data-ttu-id="609a5-108">Entre 2 et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="609a5-108">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="609a5-109">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="609a5-109">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="609a5-110">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="609a5-110">More than 10 seconds.</span></span>

<span data-ttu-id="609a5-111">La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="609a5-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="609a5-112">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="609a5-112">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="609a5-113">Colonne</span><span class="sxs-lookup"><span data-stu-id="609a5-113">Column</span></span></th>
<th><span data-ttu-id="609a5-114">Type de données</span><span class="sxs-lookup"><span data-stu-id="609a5-114">Data Type</span></span></th>
<th><span data-ttu-id="609a5-115">Clé/index</span><span class="sxs-lookup"><span data-stu-id="609a5-115">Key/Index</span></span></th>
<th><span data-ttu-id="609a5-116">Détails</span><span class="sxs-lookup"><span data-stu-id="609a5-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="609a5-117"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="609a5-117"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="609a5-118">int</span><span class="sxs-lookup"><span data-stu-id="609a5-118">int</span></span></p></td>
<td><p><span data-ttu-id="609a5-119">Primaire</span><span class="sxs-lookup"><span data-stu-id="609a5-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="609a5-120">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="609a5-120">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="609a5-121"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="609a5-121"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="609a5-122">int</span><span class="sxs-lookup"><span data-stu-id="609a5-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="609a5-p102">Limite supérieure de la classification. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="609a5-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="609a5-125">n°2</span><span class="sxs-lookup"><span data-stu-id="609a5-125">2</span></span></p></li>
<li><p><span data-ttu-id="609a5-126">5 </span><span class="sxs-lookup"><span data-stu-id="609a5-126">5</span></span></p></li>
<li><p><span data-ttu-id="609a5-127">10 </span><span class="sxs-lookup"><span data-stu-id="609a5-127">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

