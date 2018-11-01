---
title: 'Lync Server 2013 : Table SessionCorrelation'
TOCTitle: Table SessionCorrelation
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398091(v=OCS.15)
ms:contentKeyID: 49296102
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table SessionCorrelation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un CorrelationID qui sert à corréler plusieurs sessions.


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
<td><p><strong>Checksum</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification de ce serveur de conférence A/V.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationID</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Les sessions corrélées auront le même ID de corrélation.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>DateHeure</p></td>
<td><p> </p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>

