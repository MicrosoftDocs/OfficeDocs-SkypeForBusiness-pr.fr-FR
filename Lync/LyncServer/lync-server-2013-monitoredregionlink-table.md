---
title: 'Lync Server 2013 : Table MonitoredRegionLink'
TOCTitle: Table MonitoredRegionLink
ms:assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398874(v=OCS.15)
ms:contentKeyID: 49298870
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table MonitoredRegionLink dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente une liaison entre deux pays/régions.


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
<td><p><strong>Region1Key</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-region-table.md">Table Region dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Region2Key</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-region-table.md">Table Region dans Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

