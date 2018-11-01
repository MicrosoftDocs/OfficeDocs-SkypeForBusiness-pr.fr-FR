---
title: 'Lync Server 2013 : Table Region'
TOCTitle: Table Region
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398235(v=OCS.15)
ms:contentKeyID: 49296379
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Region dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Region est une table de prise en charge. Chaque enregistrement représente une région ou un pays défini dans les paramètres de configuration réseau.


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
<td><p><strong>RegionKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification de ce pays ou cette région.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegionName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Unique</p></td>
<td><p>Nom de ce pays ou cette région.</p></td>
</tr>
</tbody>
</table>

