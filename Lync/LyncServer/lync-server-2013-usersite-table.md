---
title: 'Lync Server 2013 : Table UserSite'
TOCTitle: Table UserSite
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398256(v=OCS.15)
ms:contentKeyID: 49296421
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table UserSite dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.


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
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique d’identification de ce site utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Unique</p></td>
<td><p>Nom d’utilisateur du site.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Référencé depuis la <a href="lync-server-2013-region-table.md">Table Region dans Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

