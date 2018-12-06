---
title: 'Lync Server 2013 : Table Subnet'
TOCTitle: Table Subnet
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398582(v=OCS.15)
ms:contentKeyID: 49297780
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Subnet dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.


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
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Représentation sous forme d’entier de l’adresse IP de sous-réseau.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetMask</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Masque de sous-réseau.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-usersite-table.md">Table UserSite dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetDescription</strong></p></td>
<td><p>nvarchar(512)</p></td>
<td><p></p></td>
<td><p>Description du sous-réseau.</p></td>
</tr>
</tbody>
</table>

