---
title: Table MonitoredUserSiteLink
TOCTitle: Table MonitoredUserSiteLink
ms:assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398233(v=OCS.15)
ms:contentKeyID: 49296374
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table MonitoredUserSiteLink

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateurs.


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
<td><p><strong>UserSite1Key</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-usersite-table.md">Table UserSite dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSite2Key</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Référence tirée de la <a href="lync-server-2013-usersite-table.md">Table UserSite dans Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

