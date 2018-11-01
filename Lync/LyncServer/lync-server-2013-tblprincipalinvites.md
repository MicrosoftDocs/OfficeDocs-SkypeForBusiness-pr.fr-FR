---
title: 'Lync Server 2013 : tblPrincipalInvites'
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558650(v=OCS.15)
ms:contentKeyID: 49297223
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalInvites dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.

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
<td><p>invID</p></td>
<td><p>entier, non null</p></td>
<td><p>Numéro séquentiel unique (par ID principal) généré depuis la table tblLastInviteId.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID de nœud (salle de conversation uniquement).</p></td>
</tr>
<tr class="even">
<td><p>createdOn</p></td>
<td><p>datetime, non null</p></td>
<td><p>Heure de création.</p></td>
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
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal.prinID.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode.nodeID.</p></td>
</tr>
</tbody>
</table>

