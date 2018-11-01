---
title: 'Lync Server 2013 : tblLastChatId'
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558616(v=OCS.15)
ms:contentKeyID: 49296378
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblLastChatId dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.

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
<td><p>nodeID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID de nœud (type de salle de conversation seulement).</p></td>
</tr>
<tr class="even">
<td><p>lastChatID</p></td>
<td><p>bigint, non null</p></td>
<td><p>ID de conversation le plus récemment utilisé.</p></td>
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
<td><p>&lt;nodeID, lastChatID&gt;</p></td>
<td><p>Clé principale (nodeID est suffisant pour le traitement).</p></td>
</tr>
<tr class="even">
<td><p>nodeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode.nodeID.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[tblChat dans Lync Server 2013](lync-server-2013-tblchat.md)

