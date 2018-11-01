---
title: 'Lync Server 2013 : Table User'
TOCTitle: Table User
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398505(v=OCS.15)
ms:contentKeyID: 49297513
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table User dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonne</strong></th>
<th><strong>Type de données</strong></th>
<th><strong>Clé/Index</strong></th>
<th><strong>Détails</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant cet utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Unique</p></td>
<td><p>Chaîne URI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>1 est type URI inconnu.</p>
<p>2 est URI d’utilisateur.</p>
<p>4 est URI de conférence.</p>
<p>8 est URI de téléphone.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Locataire de l’utilisateur, référencé depuis la table de locataires.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Horodatage le plus récent du moment où l’utilisateur avait un appel de mauvaise qualité audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>

