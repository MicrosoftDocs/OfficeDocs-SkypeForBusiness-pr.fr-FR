---
title: 'Lync Server 2013 : Table Devices'
TOCTitle: Table Devices
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398351(v=OCS.15)
ms:contentKeyID: 49297251
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Devices dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Devices est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).


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
<td><p><strong>DeviceId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification de cette version matérielle.</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Fabricant de cet appareil. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-manufacturers-table.md">Table Manufacturers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Version du matériel de cet appareil. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-hardwareversions-table.md">Table HardwareVersions dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>Adresse MAC</p></td>
</tr>
</tbody>
</table>

