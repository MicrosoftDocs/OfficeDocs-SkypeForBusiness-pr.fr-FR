---
title: 'Lync Server 2013 : PurgeSettings table (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46516be447fa3099afe492e5edc4f4008ea5a079
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="c2d4a-102">PurgeSettings table (QoE) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2d4a-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2d4a-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c2d4a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c2d4a-104">La table PurgeSettings contient des informations qui spécifient si (et quand) les enregistrements de qualité d’expérimentation obsolètes seront automatiquement supprimés de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="c2d4a-105">Notez que les informations relatives à la purge peuvent également être obtenues à partir de Microsoft Lync Server 2013 Management Shell en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c2d4a-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="c2d4a-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2d4a-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="c2d4a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c2d4a-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="c2d4a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c2d4a-109"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="c2d4a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c2d4a-110"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="c2d4a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2d4a-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="c2d4a-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d4a-112">int</span><span class="sxs-lookup"><span data-stu-id="c2d4a-112">int</span></span></p></td>
<td><p><span data-ttu-id="c2d4a-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c2d4a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c2d4a-114">Identificateur unique de la collection de paramètres de purge QoE.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d4a-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="c2d4a-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d4a-116">bit</span><span class="sxs-lookup"><span data-stu-id="c2d4a-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2d4a-117">Lorsque cette propriété est définie sur true (1) Microsoft Lync Server 2013 supprime périodiquement les enregistrements obsolètes de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="c2d4a-118">La purge doit avoir lieu tous les jours sur le tome indiqué par le paramètre PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="c2d4a-119">Si elle a la valeur false (0), les enregistrements ne seront pas automatiquement supprimés de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="c2d4a-120">La valeur par défaut est « True ».</span><span class="sxs-lookup"><span data-stu-id="c2d4a-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d4a-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="c2d4a-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d4a-122">int</span><span class="sxs-lookup"><span data-stu-id="c2d4a-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2d4a-123">Spécifie l’âge des enregistrements QoE (en jours) qui seront supprimés de la base de données : si la purge est activée, les enregistrements QoE antérieurs à cette valeur seront supprimés de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-123">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="c2d4a-124">La valeur par défaut est 60 jours.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-124">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d4a-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="c2d4a-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d4a-126">int</span><span class="sxs-lookup"><span data-stu-id="c2d4a-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2d4a-127">Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-127">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="c2d4a-128">L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-128">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="c2d4a-129">Notez que vous pouvez seulement spécifier l’heure du jour : une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-129">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="c2d4a-130">La valeur par défaut est 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="c2d4a-130">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="c2d4a-131">Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-131">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="c2d4a-132">L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-132">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="c2d4a-133">Notez que vous pouvez seulement spécifier l’heure du jour : une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="c2d4a-133">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="c2d4a-134">La valeur par défaut est 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="c2d4a-134">The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

