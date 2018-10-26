---
title: 'Lync Server 2013 : tblPrincipalAffiliations'
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558642(v=OCS.15)
ms:contentKeyID: 49297078
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalAffiliations dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblPrincipalAffiliations contient les affiliations principales qui décrivent l’appartenance dans les emplacements incluant les groupes de sécurité des services de domaine Active Directory, dans les conteneurs Active Directory et dans les domaines.

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
<td><p>principalID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du principal affilié.</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du principal représentant l’affiliation. Chaque principal (sauf system-user-types) possède également une auto-affiliation.</p></td>
</tr>
<tr class="odd">
<td><p>index</p></td>
<td><p>entier, non null</p></td>
<td><p>Index. La valeur utilisée pour les auto-affiliations est -1 ; pour les autres affiliations, elle augmente de manière séquentielle à partir de 1 dans chaque paquet &lt;principalID, affiliationId&gt;.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>entier, non null</p></td>
<td><p>Principal qui a effectué la mise à jour la plus récente. Il s’agit généralement de 1, ce qui signifie Active Directory Sync.</p></td>
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
<th>Colonnes</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID, index, affiliationID&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal.prinID.</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>

