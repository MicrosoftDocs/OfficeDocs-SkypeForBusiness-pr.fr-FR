---
title: Table CodecDescription dans Lync Server 2013
TOCTitle: Table CodecDescription dans Lync Server 2013
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204797(v=OCS.15)
ms:contentKeyID: 49296839
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table CodecDescription dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table CodecDescription mappe des identificateurs de codec uniques au codec correspondant. Les codecs sont utilisés pour encoder des signaux numériques pour la transmission et la diffusion, puis à décoder ces signaux pour la lecture. Cette table est une nouveauté de Microsoft Lync Server 2013


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
<td><p><strong>CodecDescriptionKey</strong></p></td>
<td><p>smallint</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique affecté au codec.</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Description unique du codec correspondant à CodecDescriptionKey.</p></td>
</tr>
</tbody>
</table>

