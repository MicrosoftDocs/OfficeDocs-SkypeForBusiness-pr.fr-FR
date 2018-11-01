---
title: 'Lync Server 2013 : tblADUpdates'
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615033(v=OCS.15)
ms:contentKeyID: 49298665
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblADUpdates dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les dernières étapes de la synchronisation Active Directory.

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
<td><p>prinGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID de principal de l’objet qui a changé.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384), non null</p></td>
<td><p>Nom unique de l’objet.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit, non null</p></td>
<td><p>True si au moins un attribut de l’objet a changé.</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit, non null</p></td>
<td><p>True si l’appartenance a changé.</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit, non null</p></td>
<td><p>Inutilisé.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, non null</p></td>
<td><p>True si l’objet a été supprimé.</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime, non null</p></td>
<td><p>Horodatage de l’insertion de la ligne.</p></td>
</tr>
</tbody>
</table>

