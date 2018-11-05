---
title: 'Lync Server 2013 : Table Device'
TOCTitle: Table Device
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398930(v=OCS.15)
ms:contentKeyID: 49298966
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Device dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.


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
<td><p><strong>DeviceKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique qui identifie ce périphérique.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>DeviceName + DeviceType est unique</p></td>
<td><p>Nom du périphérique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceType</strong></p></td>
<td><p>bit</p></td>
<td><p>DeviceName + DeviceType est unique</p></td>
<td><p>Type de périphérique. 1 correspond à un périphérique de capture, 0 à un périphérique de rendu.</p></td>
</tr>
</tbody>
</table>

