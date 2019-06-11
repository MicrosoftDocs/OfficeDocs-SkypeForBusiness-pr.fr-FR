---
title: 'Tableau Lync Server 2013: PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b9fc0aa03596677cb73641ed46e86ea133f308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Table PurgeSettings dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

La table PurgeSettings contient des informations qui spécifient si les enregistrements de détails des appels obsolètes seront automatiquement supprimés de la base de données CDR. Notez que les informations relatives à la purge peuvent également être obtenues à partir de Microsoft Lync Server 2013 Management Shell en exécutant la commande suivante:

    Get-CsCdrConfiguration

Les administrateurs doivent traiter la table PurgeSettings comme étant en lecture seule: les modifications apportées aux paramètres de purge des détails des appels doivent uniquement être effectuées à l’aide des applets [de nouvelle-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) ou [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

Ce tableau a été présenté dans Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique de la collection de paramètres de purge de CDR.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Lorsque cette propriété est définie sur true (1) Microsoft Lync Server 2013 supprime périodiquement les enregistrements obsolètes de la base de données CDR. La purge doit avoir lieu tous les jours sur le tome indiqué par le paramètre PurgeHour. Si elle a la valeur false (0), les enregistrements ne seront pas automatiquement supprimés de la base de données. La valeur par défaut est « True ».</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Spécifie l’âge des enregistrements CDR (en jours) qui seront supprimés de la base de données: si la suppression définitive est activée, les enregistrements CDR antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Spécifie l’âge des enregistrements de rapport d’erreur (en jours) qui seront supprimés de la base de données: si la purge est activée, les enregistrements de rapport d’erreur antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez seulement spécifier l’heure du jour: une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée. La valeur par défaut est 2 (2:00 AM).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

