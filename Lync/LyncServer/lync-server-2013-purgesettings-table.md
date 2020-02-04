---
title: 'Tableau Lync Server 2013 : PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="51cdf-102">Table PurgeSettings dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51cdf-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51cdf-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="51cdf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="51cdf-104">La table PurgeSettings contient des informations qui spécifient si les enregistrements de détails des appels obsolètes seront automatiquement supprimés de la base de données CDR.</span><span class="sxs-lookup"><span data-stu-id="51cdf-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="51cdf-105">Notez que les informations relatives à la purge peuvent également être obtenues à partir de Microsoft Lync Server 2013 Management Shell en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="51cdf-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="51cdf-106">Les administrateurs doivent traiter la table PurgeSettings comme étant en lecture seule : les modifications apportées aux paramètres de purge des détails des appels doivent uniquement être effectuées à l’aide des applets [de nouvelle-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) ou [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="51cdf-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="51cdf-107">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51cdf-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51cdf-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="51cdf-108">Column</span></span></th>
<th><span data-ttu-id="51cdf-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="51cdf-109">Data Type</span></span></th>
<th><span data-ttu-id="51cdf-110">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="51cdf-110">Key/Index</span></span></th>
<th><span data-ttu-id="51cdf-111">Détails</span><span class="sxs-lookup"><span data-stu-id="51cdf-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51cdf-112"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="51cdf-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="51cdf-113">int</span><span class="sxs-lookup"><span data-stu-id="51cdf-113">int</span></span></p></td>
<td><p><span data-ttu-id="51cdf-114">Principal</span><span class="sxs-lookup"><span data-stu-id="51cdf-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="51cdf-115">Identificateur unique de la collection de paramètres de purge de CDR.</span><span class="sxs-lookup"><span data-stu-id="51cdf-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51cdf-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="51cdf-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="51cdf-117">bit</span><span class="sxs-lookup"><span data-stu-id="51cdf-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="51cdf-118">Lorsque cette propriété est définie sur true (1) Microsoft Lync Server 2013 supprime périodiquement les enregistrements obsolètes de la base de données CDR.</span><span class="sxs-lookup"><span data-stu-id="51cdf-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="51cdf-119">La purge doit avoir lieu tous les jours sur le tome indiqué par le paramètre PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="51cdf-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="51cdf-120">Si elle a la valeur false (0), les enregistrements ne seront pas automatiquement supprimés de la base de données.</span><span class="sxs-lookup"><span data-stu-id="51cdf-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="51cdf-121">La valeur par défaut est « True ».</span><span class="sxs-lookup"><span data-stu-id="51cdf-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51cdf-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="51cdf-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="51cdf-123">int</span><span class="sxs-lookup"><span data-stu-id="51cdf-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="51cdf-124">Spécifie l’âge des enregistrements CDR (en jours) qui seront supprimés de la base de données : si la suppression définitive est activée, les enregistrements CDR antérieurs à cette valeur seront supprimés de la base de données.</span><span class="sxs-lookup"><span data-stu-id="51cdf-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="51cdf-125">La valeur par défaut est 60 jours.</span><span class="sxs-lookup"><span data-stu-id="51cdf-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51cdf-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="51cdf-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="51cdf-127">int</span><span class="sxs-lookup"><span data-stu-id="51cdf-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="51cdf-128">Spécifie l’âge des enregistrements de rapport d’erreur (en jours) qui seront supprimés de la base de données : si la purge est activée, les enregistrements de rapport d’erreur antérieurs à cette valeur seront supprimés de la base de données.</span><span class="sxs-lookup"><span data-stu-id="51cdf-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="51cdf-129">La valeur par défaut est 60 jours.</span><span class="sxs-lookup"><span data-stu-id="51cdf-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51cdf-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="51cdf-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="51cdf-131">int</span><span class="sxs-lookup"><span data-stu-id="51cdf-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="51cdf-132">Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="51cdf-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="51cdf-133">L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h.</span><span class="sxs-lookup"><span data-stu-id="51cdf-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="51cdf-134">Notez que vous pouvez seulement spécifier l’heure du jour : une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="51cdf-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="51cdf-135">La valeur par défaut est 2 (2:00 AM).</span><span class="sxs-lookup"><span data-stu-id="51cdf-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

