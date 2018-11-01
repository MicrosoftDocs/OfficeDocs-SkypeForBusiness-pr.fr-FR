---
title: Table IPAddress dans Lync Server 2013
TOCTitle: Table IPAddress dans Lync Server 2013
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205077(v=OCS.15)
ms:contentKeyID: 49298037
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table IPAddress dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience. Cette table est une nouveauté de Microsoft Lync Server 2013.


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
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique pour l’adresse IP spécifiée.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>varchar(50)</p></td>
<td><p>Uniques</p></td>
<td><p>Adresse IP unique (par exemple, 189.168.1.1) qui est mappée à IpAddressKey. Il peut d’agir d’une adresse IPv4 ou IPv6.</p></td>
</tr>
</tbody>
</table>

