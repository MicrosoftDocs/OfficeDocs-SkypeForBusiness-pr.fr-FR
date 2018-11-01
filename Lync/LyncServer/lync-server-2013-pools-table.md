---
title: 'Lync Server 2013 : Table Pools'
TOCTitle: Table Pools
ms:assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398991(v=OCS.15)
ms:contentKeyID: 49299092
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Pools dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Pools est une table de prise en charge qui stocke des informations sur les différents pools. Chaque enregistrement de la table représente un pool.


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
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique qui identifie ce pool.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Nom de domaine complet du pool.</p></td>
</tr>
</tbody>
</table>

