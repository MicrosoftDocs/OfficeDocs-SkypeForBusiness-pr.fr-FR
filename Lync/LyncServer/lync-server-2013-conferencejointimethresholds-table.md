---
title: 'Lync Server 2013 : table ConferenceJoinTimeThresholds'
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
ms.openlocfilehash: 6d6ce43adee4c00a945325cf31c4194816e7ee14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="78392-102">Table ConferenceJoinTimeThresholds dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78392-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78392-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="78392-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="78392-p101">La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse du temps de connexion à la conférence. Ce rapport récapitule le temps nécessaire aux utilisateurs pour se joindre à une conférence. Ces valeurs de temps représentent à la fois une moyenne et l’une des catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="78392-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="78392-106">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="78392-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="78392-107">Entre 2 et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="78392-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="78392-108">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="78392-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="78392-109">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="78392-109">More than 10 seconds.</span></span>

<span data-ttu-id="78392-110">La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="78392-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="78392-111">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78392-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78392-112">Colonne</span><span class="sxs-lookup"><span data-stu-id="78392-112">Column</span></span></th>
<th><span data-ttu-id="78392-113">Type de données</span><span class="sxs-lookup"><span data-stu-id="78392-113">Data Type</span></span></th>
<th><span data-ttu-id="78392-114">Clé/index</span><span class="sxs-lookup"><span data-stu-id="78392-114">Key/Index</span></span></th>
<th><span data-ttu-id="78392-115">Détails</span><span class="sxs-lookup"><span data-stu-id="78392-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78392-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="78392-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="78392-117">int</span><span class="sxs-lookup"><span data-stu-id="78392-117">int</span></span></p></td>
<td><p><span data-ttu-id="78392-118">Primaire</span><span class="sxs-lookup"><span data-stu-id="78392-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="78392-119">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="78392-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78392-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="78392-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="78392-121">int</span><span class="sxs-lookup"><span data-stu-id="78392-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78392-p102">Limite supérieure de la classification. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="78392-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="78392-124">n°2</span><span class="sxs-lookup"><span data-stu-id="78392-124">2</span></span></p></li>
<li><p><span data-ttu-id="78392-125">disque</span><span class="sxs-lookup"><span data-stu-id="78392-125">5</span></span></p></li>
<li><p><span data-ttu-id="78392-126">10 </span><span class="sxs-lookup"><span data-stu-id="78392-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

