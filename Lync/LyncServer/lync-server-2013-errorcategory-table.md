---
title: Table ErrorCategory dans Lync Server 2013
TOCTitle: Table ErrorCategory dans Lync Server 2013
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204675(v=OCS.15)
ms:contentKeyID: 49296274
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ErrorCategory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau ErrorCategory contient le nom convivial de chaque classification de diagnostic Microsoft Lync Server 2013. Par défaut, Lync Server 2013 utilise les classifications suivantes :

  - 0 : réussite

  - 1 : échec attendu

  - 2 : échec inattendu

Cette table est une nouveauté de Microsoft Lync Server 2013.


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
<td><p><strong>CategoryId</strong></p></td>
<td><p>Entier très petit</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique pour la classification.</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valeur et nom convivial attribués à la classification. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>0 : réussite</p></li>
<li><p>1 : échec attendu</p></li>
<li><p>2 : échec inattendu</p></li>
</ul></td>
</tr>
</tbody>
</table>

