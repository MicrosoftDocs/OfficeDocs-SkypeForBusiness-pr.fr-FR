---
title: 'Lync Server 2013 : tblEnumAttribute'
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558617(v=OCS.15)
ms:contentKeyID: 49296383
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblEnumAttribute dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblEnumAttribute est une table codée en dur qui contient les attributs Visibility et Behavior utilisés dans la table Node.

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
<td><p>attributeID</p></td>
<td><p>smallint, non null</p></td>
<td><p>ID de l’attribut</p></td>
</tr>
<tr class="even">
<td><p>attributeName</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Nom de l’attribut.</p></td>
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
<td><p>attributeID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>


### Valeurs de la table

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>attributeID</th>
<th>attributeName</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Visibilité.</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Comportement.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[tblNode dans Lync Server 2013](lync-server-2013-tblnode.md)

