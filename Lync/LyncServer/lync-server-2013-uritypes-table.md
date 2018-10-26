---
title: 'Lync Server 2013 : Table UriTypes'
TOCTitle: Table UriTypes
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398587(v=OCS.15)
ms:contentKeyID: 49297791
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table UriTypes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-06-16_

La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Microsoft Lync Server 2013.


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
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique attribué à un type d’URI.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Descriptions des différents types d’URI. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>0 – Phone Uri</p></li>
<li><p>1 – User Uri</p></li>
</ul></td>
</tr>
</tbody>
</table>

