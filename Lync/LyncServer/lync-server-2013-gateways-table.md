---
title: 'Lync Server 2013 : Table Gateways'
TOCTitle: Table Gateways
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412795(v=OCS.15)
ms:contentKeyID: 49298458
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Gateways dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Gateways est une table de prise en charge. Chaque enregistrement contient des informations sur une passerelle impliquée dans des appels du réseau téléphonique commuté possédant des enregistrements dans la base de données.


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
<td><p><strong>GatewayId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant cette passerelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p> </p></td>
<td><p>Nom de la passerelle.</p></td>
</tr>
</tbody>
</table>

