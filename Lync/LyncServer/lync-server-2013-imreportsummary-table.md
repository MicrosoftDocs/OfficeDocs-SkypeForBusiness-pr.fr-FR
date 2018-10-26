---
title: Table IMReportSummary dans Lync Server 2013
TOCTitle: Table IMReportSummary dans Lync Server 2013
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204753(v=OCS.15)
ms:contentKeyID: 49296688
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table IMReportSummary dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table IMReportSummaryTable fournit un rapport général sur les sessions de messagerie instantanée qui ont lieu dans une organisation. Cette table est une nouveauté de Microsoft Lync Server 2013.


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
<td><p><strong>StartTime</strong></p></td>
<td><p>Date/heure</p></td>
<td><p>Principal</p></td>
<td><p>Date et heure de début de la session de messagerie instantanée.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimePeriod</strong></p></td>
<td><p>char(1)</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar(257)</p></td>
<td><p>Principal</p></td>
<td><p>Nom de domaine complet du pool hébergeant la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>AuthType</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Priorité (par exemple, urgent ou non urgent) de l’appel. Les informations de priorité sont stockées dans la <a href="lync-server-2013-callpriorities-table.md">Table CallPriorities dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MsgCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>Nombre total de messages instantanés échangés au cours de la session.</p></td>
</tr>
</tbody>
</table>

