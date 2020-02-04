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

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>PurgeSettings table (QoE) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

La table PurgeSettings contient des informations qui spécifient si (et quand) les enregistrements de qualité d’expérimentation obsolètes seront automatiquement supprimés de la base de données QoE. Notez que les informations relatives à la purge peuvent également être obtenues à partir de Microsoft Lync Server 2013 Management Shell en exécutant la commande suivante :

    Get-CsQoEConfiguration

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
<th><strong>Colonne</strong></th>
<th><strong>Type de données</strong></th>
<th><strong>Clé/Index</strong></th>
<th><strong>Détails</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique de la collection de paramètres de purge QoE.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Lorsque cette propriété est définie sur true (1) Microsoft Lync Server 2013 supprime périodiquement les enregistrements obsolètes de la base de données QoE. La purge doit avoir lieu tous les jours sur le tome indiqué par le paramètre PurgeHour. Si elle a la valeur false (0), les enregistrements ne seront pas automatiquement supprimés de la base de données. La valeur par défaut est « True ».</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Spécifie l’âge des enregistrements QoE (en jours) qui seront supprimés de la base de données : si la purge est activée, les enregistrements QoE antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez seulement spécifier l’heure du jour : une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM). Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez seulement spécifier l’heure du jour : une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

