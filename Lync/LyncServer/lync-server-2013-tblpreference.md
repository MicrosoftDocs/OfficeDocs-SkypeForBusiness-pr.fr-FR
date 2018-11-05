---
title: 'Lync Server 2013 : tblPreference'
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615052(v=OCS.15)
ms:contentKeyID: 49299415
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPreference dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table tblPreference contient les préférences des utilisateurs pour les clients. Elle est généralement utilisée par les clients avant Lync 2013.

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
<td><p>prefLabel</p></td>
<td><p>nvarchar (255), non null</p></td>
<td><p>Étiquette dont le format est le suivant : &lt;uri sip utilisateur&gt;|nom utilisateur.&lt;préférence définie&gt;.</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int, non null</p></td>
<td><p>Numéro séquentiel (par étiquette) à des fins de contrôle de version.</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Contenu codé.</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal qui à mis à jour la préférence.</p></td>
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
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>

