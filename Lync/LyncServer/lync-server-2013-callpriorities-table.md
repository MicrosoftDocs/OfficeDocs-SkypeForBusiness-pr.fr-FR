---
title: 'Lync Server 2013 : Table CallPriorities'
TOCTitle: Table CallPrioritiese
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398093(v=OCS.15)
ms:contentKeyID: 49296104
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table CallPriorities dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, par exemple, « très urgent », « urgent » ou « normal ».


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
<td><p><strong>PriorityId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Priority</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valeurs autorisées :</p>
<ul>
<li><p>0 - Inconnu</p></li>
<li><p>1 - Non urgent</p></li>
<li><p>2 - Normal</p></li>
<li><p>3 - Urgent</p></li>
<li><p>4 - Très urgent</p></li>
</ul></td>
</tr>
</tbody>
</table>

