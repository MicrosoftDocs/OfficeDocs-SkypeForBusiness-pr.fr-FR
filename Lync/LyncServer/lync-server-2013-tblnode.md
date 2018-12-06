---
title: 'Lync Server 2013 : tblNode'
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615024(v=OCS.15)
ms:contentKeyID: 49298384
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblNode dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblNode contient l’arbre d’objets (avec les nœuds de catégorie ou de salle de conversation) telle qu’il est géré dans le Panneau de configuration Lync Server 2013 et dans les applets de commande administratives.

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
<td><p>int, non null</p></td>
<td><p>ID de nœud (numéro unique).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID de nœud.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>Int</p></td>
<td><p>ID de nœud du parent. Le nœud racine (avec l’ID 1) s’inclut lui-même comme parent.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, non null</p></td>
<td><p>True si le nœud est une catégorie.</p>
<p>False si le nœud est une salle de conversation.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Nom du nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Description du nœud.</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>bit</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si les invitations sont activées.</p></li>
<li><p>False si les invitations sont désactivées.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>False si les invitations sont désactivées (remplace la catégorie parente).</p></li>
<li><p>Null si le paramètre d’invitation est hérité de la catégorie parente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>logged</p></td>
<td><p>bit</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si l’historique des conversations est activé.</p></li>
<li><p>False si l’historique des conversations est désactivé.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>Null.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si les téléchargements de fichiers sont autorisés.</p></li>
<li><p>False si les téléchargements de fichiers sont interdits.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>Null.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>disabled</p></td>
<td><p>bit, non null</p></td>
<td><p>True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (False pour les catégories.)</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>smallint, non null</p></td>
<td><p>Comportement (tiré de la table EnumValue) :</p>
<ul>
<li><p>4 : normal (salles de conversation normales).</p></li>
<li><p>5 : auditorium (salles de conversation de type auditorium, seuls les présentateurs peuvent contribuer).</p></li>
</ul>
<p>S’applique uniquement aux salles de conversation.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint, non null</p></td>
<td><p>Visibilité (tirée de la table EnumValue) :</p>
<ul>
<li><p>2 : privée</p></li>
<li><p>3 : limitée par une étendue</p></li>
<li><p>6 : ouvert</p></li>
</ul>
<p>S’applique uniquement aux salles de conversation.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>GUID de complément si un complément est associé à cette salle de conversation. (Les catégories n’ont pas de complément.)</p>
<p>Les informations relatives aux compléments sont recherchées dans la table SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal ayant créé ce nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage de la création de nœud.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal ayant effectué la dernière mise à jour de ce nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage de la dernière mise à jour de ce nœud.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>Heure de la dernière opération de vidage (suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) ayant affecté ce nœud. Utilisé uniquement par le mécanisme de mise à jour du cache interne du service de conversation.</p></td>
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
<td><p>nodeID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>Clé étrangère avec recherche dans la table tblEnumValue.valueID.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>Clé étrangère avec recherche dans la table tblEnumValue.valueID.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblSiopWhiteList.siopId.</p></td>
</tr>
</tbody>
</table>

