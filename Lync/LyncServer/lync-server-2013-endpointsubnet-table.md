---
title: 'Lync Server 2013 : Table EndpointSubnet'
TOCTitle: Table EndpointSubnet
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398933(v=OCS.15)
ms:contentKeyID: 49298981
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table EndpointSubnet dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table EndpointSubnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau capturé depuis des points de terminaison.


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Représentation entière du sous-réseau.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>

