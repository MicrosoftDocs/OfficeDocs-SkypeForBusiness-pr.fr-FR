---
title: 'Lync Server 2013 : tblEnumValue'
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615025(v=OCS.15)
ms:contentKeyID: 49298387
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblEnumValue dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.

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
<td><p>valueID</p></td>
<td><p>smallint, non null</p></td>
<td><p>ID de la valeur</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, non null</p></td>
<td><p>ID de l’attribut</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Nom de la valeur.</p></td>
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
<td><p>valueID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</p></td>
</tr>
</tbody>
</table>


### Valeurs de la table

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
<td><p>privé</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>étendue</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>2</p></td>
<td><p>normal</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>2</p></td>
<td><p>auditorium</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>1</p></td>
<td><p>ouvert</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[tblNode dans Lync Server 2013](lync-server-2013-tblnode.md)

