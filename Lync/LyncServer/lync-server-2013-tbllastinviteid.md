---
title: 'Lync Server 2013 : tblLastInviteId'
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558625(v=OCS.15)
ms:contentKeyID: 49296490
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblLastInviteId dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.

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
<td><p>entier, non null</p></td>
<td><p>ID du principal.</p></td>
</tr>
<tr class="even">
<td><p>lastInviteID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID d’invitation le plus récemment utilisé.</p></td>
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
<td><p>prinID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[tblPrincipalInvites dans Lync Server 2013](lync-server-2013-tblprincipalinvites.md)

