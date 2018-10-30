---
title: 'Lync Server 2013 : tblPrincipalType'
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558633(v=OCS.15)
ms:contentKeyID: 49296801
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalType dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table tblPrincipalType contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal.

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
<td><p>ptypeID</p></td>
<td><p>smallint, non null</p></td>
<td><p>ID de type Principal.</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Description du type.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, non null</p></td>
<td><p>Vrai si le type correspond aux principaux utilisés pour des fonctions internes.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, non null</p></td>
<td><p>Vrai si le type est un type utilisateur.</p></td>
</tr>
</tbody>
</table>


### Clé

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
<td><p>ptypeID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>


### Valeurs principales

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Rôle</th>
<th>Description</th>
<th>Utilisateur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Indifférente</p></td>
<td><p>Principal générique sans type connu. Inutilisé dans la table tblPrincipal.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>Principal générique de type utilisateur. Inutilisé dans table tblPrincipal.</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Principal générique avec sémantique de groupe. Inutilisé dans table tblPrincipal.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>Principal utilisé en interne par le serveur de conversations permanentes.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>Utilisateur</p></td>
<td><p>Utilisateur régulier.</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>DC</p></td>
<td><p>Contrôleur de domaine services de domaine Active Directory.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>Groupe</p></td>
<td><p>Groupe de sécurité Active Directory.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>Folder</p></td>
<td><p>Conteneur ou unité d’organisation Active Directory.</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[tblPrincipal dans Lync Server 2013](lync-server-2013-tblprincipal.md)

