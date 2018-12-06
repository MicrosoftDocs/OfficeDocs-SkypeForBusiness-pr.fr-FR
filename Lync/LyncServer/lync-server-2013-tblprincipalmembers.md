---
title: 'Lync Server 2013 : tblPrincipalMembers'
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615022(v=OCS.15)
ms:contentKeyID: 49298282
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalMembers dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblPrincipalMembers contient les appartenances des principaux.

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
<td><p>prinID</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal.</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar (384), non null</p></td>
<td><p>Nom unique d’un membre. Il n’est pas obligatoire qu’un membre soit un principal (dans la table tblPrincipal).</p></td>
</tr>
</tbody>
</table>


### Clés

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
<td><p>&lt;prinID, memberADPath&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clé étrangère avec recherche dans tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>

