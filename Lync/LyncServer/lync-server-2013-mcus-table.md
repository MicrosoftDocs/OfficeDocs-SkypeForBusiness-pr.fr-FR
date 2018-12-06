---
title: 'Lync Server 2013 : Table Mcus'
TOCTitle: Table Mcus
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425742(v=OCS.15)
ms:contentKeyID: 49296632
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Mcus dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Mcus est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence par téléphone (qui s’exécutent en tant que processus sur des serveurs frontaux), ainsi que du service de conférence web et du service de conférence audio/vidéo.


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
<td><p><strong>McuId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant ce serveur de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><strong>McuTypeId</strong></p></td>
<td><p>inyint</p></td>
<td><p>Étrangère</p></td>
<td><p>Type de serveur de conférence, tel que conf:chat (pour les messageries instantanées) ou conf:audio-video. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

