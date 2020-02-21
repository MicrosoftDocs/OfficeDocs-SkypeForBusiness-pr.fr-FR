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
ms.openlocfilehash: 5cb0a0770136fa5b9d61f80825e49d319f872f32
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="ce823-102">PurgeSettings table (QoE) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce823-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce823-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ce823-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ce823-104">La table PurgeSettings contient des informations indiquant si (et quand) les enregistrements de qualité de l’expérience obsolètes doivent être automatiquement supprimés de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="ce823-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="ce823-105">Notez que les informations relatives à la purge peuvent également être obtenues à partir de Microsoft Lync Server 2013 Management Shell en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ce823-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="ce823-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce823-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce823-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="ce823-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ce823-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="ce823-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ce823-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="ce823-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ce823-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ce823-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce823-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="ce823-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ce823-112">int</span><span class="sxs-lookup"><span data-stu-id="ce823-112">int</span></span></p></td>
<td><p><span data-ttu-id="ce823-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="ce823-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ce823-114">Identificateur unique pour la collecte des paramètres de vidage QoE.</span><span class="sxs-lookup"><span data-stu-id="ce823-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce823-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="ce823-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="ce823-116">légèrement</span><span class="sxs-lookup"><span data-stu-id="ce823-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce823-117">Lorsque ce paramètre est défini sur true (1), Microsoft Lync Server 2013 purge régulièrement les enregistrements obsolètes de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="ce823-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="ce823-118">LA suppression a lieu tous les jours à l’heure indiquée par le paramètre PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="ce823-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="ce823-119">Si la valeur est False (0), les enregistrements ne sont pas supprimés automatiquement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ce823-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="ce823-120">La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="ce823-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce823-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="ce823-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="ce823-122">int</span><span class="sxs-lookup"><span data-stu-id="ce823-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce823-p103">Spécifie l’âge des enregistrements QoE (en jours) qui seront supprimés de la base de données : si le vidage est activé, les enregistrements QoE antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</span><span class="sxs-lookup"><span data-stu-id="ce823-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce823-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="ce823-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="ce823-126">int</span><span class="sxs-lookup"><span data-stu-id="ce823-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce823-p104">Spécifie l’heure locale du jour auquel le vidage a lieu. L’heure du jour est indiquée au format 24 heures, 0 représentant minuit (12:00 AM) et 23 représentant 11:00 PM. Notez que vous ne pouvez spécifier que des  heures : la valeur 10 (10:00 AM) est autorisée, mais la valeur 10,5 (10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM). Spécifie l’heure locale du jour auquel le vidage a lieu. L’heure du jour est indiquée au format 24 heures, 0 représentant minuit (12:00 AM) et 23 représentant 11:00 PM. Notez que vous ne pouvez spécifier que des  heures : la valeur 10 (10:00 AM) est autorisée, mais la valeur 10,5 (10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="ce823-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

