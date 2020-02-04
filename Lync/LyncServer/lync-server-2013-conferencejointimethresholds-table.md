---
title: 'Tableau Lync Server 2013 : ConferenceJoinTimeThresholds'
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
ms.openlocfilehash: baf29af4b9d1f2b026271b84cb54436e8f4b233f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="3a96c-102">Table ConferenceJoinTimeThresholds dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a96c-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a96c-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3a96c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3a96c-104">La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="3a96c-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="3a96c-105">Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence ; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a96c-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="3a96c-106">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="3a96c-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="3a96c-107">Entre 2 secondes et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="3a96c-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="3a96c-108">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="3a96c-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="3a96c-109">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="3a96c-109">More than 10 seconds.</span></span>

<span data-ttu-id="3a96c-110">La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="3a96c-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="3a96c-111">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a96c-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a96c-112">Colonne</span><span class="sxs-lookup"><span data-stu-id="3a96c-112">Column</span></span></th>
<th><span data-ttu-id="3a96c-113">Type de données</span><span class="sxs-lookup"><span data-stu-id="3a96c-113">Data Type</span></span></th>
<th><span data-ttu-id="3a96c-114">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="3a96c-114">Key/Index</span></span></th>
<th><span data-ttu-id="3a96c-115">Détails</span><span class="sxs-lookup"><span data-stu-id="3a96c-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a96c-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="3a96c-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="3a96c-117">int</span><span class="sxs-lookup"><span data-stu-id="3a96c-117">int</span></span></p></td>
<td><p><span data-ttu-id="3a96c-118">Principal</span><span class="sxs-lookup"><span data-stu-id="3a96c-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a96c-119">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="3a96c-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a96c-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="3a96c-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="3a96c-121">int</span><span class="sxs-lookup"><span data-stu-id="3a96c-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a96c-122">Limite supérieure de la classification.</span><span class="sxs-lookup"><span data-stu-id="3a96c-122">Upper limit for the classification.</span></span> <span data-ttu-id="3a96c-123">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a96c-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="3a96c-124">deuxième</span><span class="sxs-lookup"><span data-stu-id="3a96c-124">2</span></span></p></li>
<li><p><span data-ttu-id="3a96c-125">5</span><span class="sxs-lookup"><span data-stu-id="3a96c-125">5</span></span></p></li>
<li><p><span data-ttu-id="3a96c-126">0,10</span><span class="sxs-lookup"><span data-stu-id="3a96c-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

