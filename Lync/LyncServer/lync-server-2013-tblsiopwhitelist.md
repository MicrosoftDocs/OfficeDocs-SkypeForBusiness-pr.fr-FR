---
title: 'Lync Server 2013 : tblSiopWhiteList'
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558607(v=OCS.15)
ms:contentKeyID: 49296132
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblSiopWhiteList dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblSiopWhiteList représente la liste des compléments inscrits qui peuvent être associés à des nœuds.

### Colonnes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID du complément.</p></td>
</tr>
<tr class="even">
<td><p>siopName</p></td>
<td><p>nvarchar (50), non null</p></td>
<td><p>Nom d’affichage du complément.</p></td>
</tr>
<tr class="odd">
<td><p>siopUrl</p></td>
<td><p>nvarchar (255), non null</p></td>
<td><p>URL du complément.</p></td>
</tr>
</tbody>
</table>


### Clé

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>

