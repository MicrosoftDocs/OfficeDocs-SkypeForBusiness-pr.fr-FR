---
title: 'Lync Server 2013 : Table DeviceDriver'
TOCTitle: Table DeviceDriver
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398844(v=OCS.15)
ms:contentKeyID: 49298859
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table DeviceDriver dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table DeviceDriver est une table de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou par un périphérique de rendu.


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
<td><p><strong>DeviceDriverKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification de cet enregistrement de pilote de périphérique.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>unique</p></td>
<td><p>Nom du pilote de périphérique.</p></td>
</tr>
</tbody>
</table>

