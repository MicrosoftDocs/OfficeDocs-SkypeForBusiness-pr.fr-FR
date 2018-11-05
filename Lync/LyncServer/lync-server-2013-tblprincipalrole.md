---
title: 'Lync Server 2013 : tblPrincipalRole'
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615039(v=OCS.15)
ms:contentKeyID: 49299072
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalRole dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.

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
<td><p>prinRoleNodeID</p></td>
<td><p>int, non null</p></td>
<td><p>ID du nœud auquel le rôle s’applique.</p></td>
</tr>
<tr class="even">
<td><p>prinRolePrinID</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal.</p></td>
</tr>
<tr class="odd">
<td><p>prinRoleTypeID</p></td>
<td><p>int, non null</p></td>
<td><p>ID du type de rôle (d’après tblRoleType).</p></td>
</tr>
<tr class="even">
<td><p>prinRoleUpdatedBy</p></td>
<td><p>int, non null</p></td>
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
<td><p>&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>prinRoleNodeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>prinRolePrinID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal.prinID.</p></td>
</tr>
<tr class="even">
<td><p>prinRoleTypeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblRoleType.rtypeID.</p></td>
</tr>
</tbody>
</table>

