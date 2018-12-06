---
title: Vue ClientVersions
TOCTitle: Vue ClientVersions
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49891543
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue ClientVersions

 

_**Dernière rubrique modifiée :** 2015-03-09_

La vue ClientVersions stocke les informations relatives aux divers types et versions de client qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la vue représente une version de client. Cette vue a été introduite dans Microsoft Lync Server 2013.

> [!NOTE]  
> Plusieurs enregistrements peuvent exister pour certaines colonnes.


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
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro unique identifiant le type et la version de ce client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Représente l’agent utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Type de client.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Catégorie à laquelle le client appartient. Par exemple, le client Conferencing_Attendant_1.0 appartient à la catégorie CAA.</p></td>
</tr>
</tbody>
</table>

