---
title: 'Lync Server 2013 : Table Server'
TOCTitle: Table Server
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398801(v=OCS.15)
ms:contentKeyID: 49298290
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Server est une table de prise en charge. Chaque enregistrement représente un serveur.


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
<td><p><strong>ServerKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant le serveur.</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>index</p></td>
<td><p>Chaîne d’adresse MAC</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>1 : serveur de médiation</p>
<p>2 : serveur de conférence A/V16394 : service Edge A/V32769 : passerelle</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar(512)</p></td>
<td><p></p></td>
<td><p>Pool auquel appartient le serveur. Applicable uniquement au serveur de conférence A/V.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>

