---
title: 'Lync Server 2013 : Table AppliedBandwidthSource'
TOCTitle: Table AppliedBandwidthSource
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425725(v=OCS.15)
ms:contentKeyID: 49296559
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table AppliedBandwidthSource dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.


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
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification de cette source.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthSource</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Il s’agit de la source de la capacité de bande passante imposée. Elle décrit l’origine de la limite de la bande passante (par exemple, « Serveur de stratégie », « Serveur TURN » ou « Modalité »).</p></td>
</tr>
</tbody>
</table>

