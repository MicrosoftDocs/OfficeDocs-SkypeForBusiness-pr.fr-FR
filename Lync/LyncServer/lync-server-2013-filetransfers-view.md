---
title: Vue FileTransfers
TOCTitle: Vue FileTransfers
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49891582
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue FileTransfers

 

_**Dernière rubrique modifiée :** 2015-03-09_

La vue Transfert de fichier stocke des informations concernant les sessions de transfert de fichier entre homologues. Cette vue a été présentée dans Microsoft Lync Server 2013.

> [!NOTE]  
> La vue Transfert de fichier contient toutes les colonnes de la <a href="lync-server-2013-sessiondetails-view.md">Vue SessionDetails</a>, en plus des colonnes énumérées ci-dessous.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du fichier transféré.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>bit</p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>bit</p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>bit</p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.</p></td>
</tr>
</tbody>
</table>

