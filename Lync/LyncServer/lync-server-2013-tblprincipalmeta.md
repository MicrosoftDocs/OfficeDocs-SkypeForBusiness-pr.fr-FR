---
title: 'Lync Server 2013 : tblPrincipalMeta'
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615009(v=OCS.15)
ms:contentKeyID: 49297892
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalMeta dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory.

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
<td><p>prinAffiliationsDirty</p></td>
<td><p>bit, non null</p></td>
<td><p>True si les affiliations de principaux doivent être actualisées.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>bit, non null</p></td>
<td><p>True si les attributs de principaux doivent être actualisés.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, non null</p></td>
<td><p>True si le principal doit être supprimé.</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>Int</p></td>
<td><p>Nombre de tentatives d’actualisation à partir des services AD DS ayant eu lieu jusqu’à maintenant.</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>DateHeure</p></td>
<td><p>Horodatage de la dernière tentative d’actualisation du principal. Peut être null si aucune actualisation n’a encore été tentée.</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>DateHeure</p></td>
<td><p>Horodatage de la prochaine actualisation planifiée. Peut être null si aucune actualisation supplémentaire n’a été planifiée.</p></td>
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

