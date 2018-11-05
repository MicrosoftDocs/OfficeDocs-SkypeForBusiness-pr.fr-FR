---
title: 'Lync Server 2013 : Table Conference'
TOCTitle: Table Conference
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425762(v=OCS.15)
ms:contentKeyID: 49296698
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Conference dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Conference est une table de prise en charge. Chaque enregistrement représente une conférence ou une session P2P.


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
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification de cet enregistrement de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>unique</p></td>
<td><p>URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session P2P.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Checksum</strong></p></td>
<td><p>Int</p></td>
<td><p>index</p></td>
<td><p>Checksum de l’URI de la conférence. À usage interne.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>DateHeure</p></td>
<td><p></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>

