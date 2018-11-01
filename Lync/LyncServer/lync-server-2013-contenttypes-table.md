---
title: 'Lync Server 2013 : Table ContentTypes'
TOCTitle: Table ContentTypes
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399007(v=OCS.15)
ms:contentKeyID: 49299144
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ContentTypes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table ContentTypes est une table annexe qui stocke la liste des types de contenu utilisés dans les sessions P2P et dans les sessions de conférence. Chaque enregistrement de la table représente un type de contenu.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification du type de contenu.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td> </td>
<td><p>Nom du type de contenu.</p></td>
</tr>
</tbody>
</table>

