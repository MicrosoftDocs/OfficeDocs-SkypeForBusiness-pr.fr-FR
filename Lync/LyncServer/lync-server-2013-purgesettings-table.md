---
title: 'Lync Server 2013 : table PurgeSettings'
description: 'Lync Server 2013 : table PurgeSettings.'
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
ms.openlocfilehash: 1ec2d1508d8362988bddbab2fe7303a23a8ee2d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559180"
---
# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="63378-103">Table PurgeSettings dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63378-103">PurgeSettings table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63378-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="63378-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="63378-105">La table PurgeSettings contient des informations qui indiquent si (et quand) les enregistrements des détails des appels obsolètes sont supprimés automatiquement de la base de données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="63378-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="63378-106">Notez que les informations relatives à la purge peuvent également être obtenues à partir de Microsoft Lync Server 2013 Management Shell en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="63378-106">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="63378-107">Les administrateurs doivent traiter la table PurgeSettings comme étant en lecture seule : les modifications apportées aux paramètres de purge des détails de l’appel doivent être effectuées uniquement à l’aide des cmdlets [New-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) ou [Set-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="63378-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="63378-108">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63378-108">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63378-109">Colonne</span><span class="sxs-lookup"><span data-stu-id="63378-109">Column</span></span></th>
<th><span data-ttu-id="63378-110">Type de données</span><span class="sxs-lookup"><span data-stu-id="63378-110">Data Type</span></span></th>
<th><span data-ttu-id="63378-111">Clé/index</span><span class="sxs-lookup"><span data-stu-id="63378-111">Key/Index</span></span></th>
<th><span data-ttu-id="63378-112">Détails</span><span class="sxs-lookup"><span data-stu-id="63378-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63378-113"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="63378-113"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="63378-114">int</span><span class="sxs-lookup"><span data-stu-id="63378-114">int</span></span></p></td>
<td><p><span data-ttu-id="63378-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="63378-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="63378-116">Identificateur unique de la collection des paramètres de suppression des enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="63378-116">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63378-117"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="63378-117"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="63378-118">légèrement</span><span class="sxs-lookup"><span data-stu-id="63378-118">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63378-119">Lorsque ce paramètre est défini sur true (1), Microsoft Lync Server 2013 purge régulièrement les enregistrements obsolètes de la base de données CDR.</span><span class="sxs-lookup"><span data-stu-id="63378-119">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="63378-120">LA suppression a lieu tous les jours à l’heure indiquée par le paramètre PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="63378-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="63378-121">Si la valeur est False (0), les enregistrements ne sont pas supprimés automatiquement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="63378-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="63378-122">La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="63378-122">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63378-123"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="63378-123"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="63378-124">int</span><span class="sxs-lookup"><span data-stu-id="63378-124">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63378-p103">Indique l’âge des enregistrements des détails des appels (en jours) qui seront supprimés de la base de données : si la suppression est activée, les enregistrements des détails des appels dont l’antériorité est supérieure à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</span><span class="sxs-lookup"><span data-stu-id="63378-p103">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63378-127"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="63378-127"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="63378-128">int</span><span class="sxs-lookup"><span data-stu-id="63378-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63378-p104">Indique l’âge des enregistrements de rapport d’erreurs (en jours) qui seront supprimés de la base de données : si la suppression est activée, les enregistrements de rapport d’erreurs dont l’antériorité est supérieure à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</span><span class="sxs-lookup"><span data-stu-id="63378-p104">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63378-131"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="63378-131"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="63378-132">int</span><span class="sxs-lookup"><span data-stu-id="63378-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63378-p105">Indique l’heure locale de la journée à laquelle la suppression de la base de données a lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (00h00) et 23 qui représente 23h00. Notez que vous ne pouvez spécifier que l’heure de la journée : la valeur 10 (indiquant 10h00) est autorisée, mais la valeur 10,5 (indiquant 10h30) est interdite. La valeur par défaut est 2 (02h00).</span><span class="sxs-lookup"><span data-stu-id="63378-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

