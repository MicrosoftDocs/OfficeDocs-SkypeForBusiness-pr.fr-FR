---
title: 'Lync Server 2013 : Table Roles'
TOCTitle: Table Roles
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399043(v=OCS.15)
ms:contentKeyID: 49299193
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Roles dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.


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
<td><p><strong>RoleId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Rôle</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valeurs autorisées :</p>
<ul>
<li><p>0 - Inconnu</p></li>
<li><p>1 - Présentateur</p></li>
<li><p>2 - Participant</p></li>
</ul></td>
</tr>
</tbody>
</table>

