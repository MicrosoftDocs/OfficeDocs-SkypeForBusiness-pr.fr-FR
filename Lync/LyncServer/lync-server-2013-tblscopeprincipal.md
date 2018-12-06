---
title: 'Lync Server 2013 : tblScopePrincipal'
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558639(v=OCS.15)
ms:contentKeyID: 49297027
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblScopePrincipal dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblScopePrincipal contient les étendues affectées aux nœuds.

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
<td><p>scopeNodeID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du nœud auquel s’applique l’étendue.</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du principal.</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, non null</p></td>
<td><p>Valeur True si le type d’étendue est Refuser ; False pour Autoriser.</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du principal qui a mis à jour cette entrée en dernier.</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>

