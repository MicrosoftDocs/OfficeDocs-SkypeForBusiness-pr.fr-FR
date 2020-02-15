---
title: 'Lync Server 2013 : table IMReportSummary'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 287fc0ceff26a5940d717b4efa1ef2c525acb0f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a>Table IMReportSummary dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-20_

Le IMReportSummaryTable fournit un rapport général sur les sessions de messagerie instantanée organisées dans une organisation. Cette table a été introduite dans Microsoft Lync Server 2013.


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
<th>Clé/index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>StartTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Primaire</p></td>
<td><p>Date et heure de début de la session de messagerie instantanée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Période</strong></p></td>
<td><p>Char(1</p></td>
<td><p>Primaire</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar (257)</p></td>
<td><p>Primaire</p></td>
<td><p>Nom de domaine complet du pool qui héberge la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>AuthType</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Priorité (par exemple, urgent ou non urgent) de l’appel. Les informations sur la priorité sont stockées dans la <a href="lync-server-2013-callpriorities-table.md">table table callpriorities dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionCount</strong></p></td>
<td><p>comportant</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>MsgCount</strong></p></td>
<td><p>comportant</p></td>
<td></td>
<td><p>Nombre total de messages instantanés échangés pendant la session.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

