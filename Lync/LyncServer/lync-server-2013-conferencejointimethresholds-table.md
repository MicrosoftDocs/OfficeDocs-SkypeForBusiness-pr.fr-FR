---
title: 'Tableau Lync Server 2013: ConferenceJoinTimeThresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="8f917-102">Table ConferenceJoinTimeThresholds dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f917-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f917-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8f917-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8f917-104">La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8f917-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="8f917-105">Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes:</span><span class="sxs-lookup"><span data-stu-id="8f917-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="8f917-106">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="8f917-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="8f917-107">Entre 2 secondes et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="8f917-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="8f917-108">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="8f917-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="8f917-109">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="8f917-109">More than 10 seconds.</span></span>

<span data-ttu-id="8f917-110">La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="8f917-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="8f917-111">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f917-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f917-112">Colonne</span><span class="sxs-lookup"><span data-stu-id="8f917-112">Column</span></span></th>
<th><span data-ttu-id="8f917-113">Type de données</span><span class="sxs-lookup"><span data-stu-id="8f917-113">Data Type</span></span></th>
<th><span data-ttu-id="8f917-114">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="8f917-114">Key/Index</span></span></th>
<th><span data-ttu-id="8f917-115">Détails</span><span class="sxs-lookup"><span data-stu-id="8f917-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f917-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="8f917-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f917-117">int</span><span class="sxs-lookup"><span data-stu-id="8f917-117">int</span></span></p></td>
<td><p><span data-ttu-id="8f917-118">Principal</span><span class="sxs-lookup"><span data-stu-id="8f917-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="8f917-119">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="8f917-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f917-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="8f917-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="8f917-121">int</span><span class="sxs-lookup"><span data-stu-id="8f917-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f917-122">Limite supérieure de la classification.</span><span class="sxs-lookup"><span data-stu-id="8f917-122">Upper limit for the classification.</span></span> <span data-ttu-id="8f917-123">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="8f917-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="8f917-124">2</span><span class="sxs-lookup"><span data-stu-id="8f917-124">2</span></span></p></li>
<li><p><span data-ttu-id="8f917-125">5</span><span class="sxs-lookup"><span data-stu-id="8f917-125">5</span></span></p></li>
<li><p><span data-ttu-id="8f917-126">0,10</span><span class="sxs-lookup"><span data-stu-id="8f917-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

