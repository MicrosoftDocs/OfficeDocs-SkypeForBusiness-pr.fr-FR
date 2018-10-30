---
title: 'Lync Server 2013 : Table Servers'
TOCTitle: Table Servers
ms:assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398223(v=OCS.15)
ms:contentKeyID: 49296349
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Servers dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Servers est une table de prise en charge qui stocke des informations relatives aux divers serveurs. Chaque enregistrement de la table représente un serveur.


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
<td><p><strong>ServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification de ce serveur.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerFQDN</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Nom de domaine complet du serveur</p></td>
</tr>
</tbody>
</table>

