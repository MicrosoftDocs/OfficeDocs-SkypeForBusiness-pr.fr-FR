---
title: 'Lync Server 2013 : tblSkippedAffiliations'
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558611(v=OCS.15)
ms:contentKeyID: 49296205
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblSkippedAffiliations dans Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues pour une raison quelconque (généralement des erreurs d’accès aux services de domaine Active Directory).

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
<td><p>affDescription</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Chaîne identifiant l’affiliation.</p>
<p>Le format est : guid: <em>{0}</em> uri: <em>{1}</em> &gt; id: <em>{2}</em></p></td>
</tr>
<tr class="odd">
<td><p>updatedBy</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal qui a mis à jour cette ligne. Il s’agit toujours d’1 (utilisateur système) car la synchronisation Active Directory est la seule source pour ces entrées.</p></td>
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
<th>Colonne(s)</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, affDescription&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>

