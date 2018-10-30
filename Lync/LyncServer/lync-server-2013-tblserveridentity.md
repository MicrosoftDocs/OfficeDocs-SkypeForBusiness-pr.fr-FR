---
title: 'Lync Server 2013 : tblServerIdentity'
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558648(v=OCS.15)
ms:contentKeyID: 49297263
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblServerIdentity dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversations permanentes.

### Colonnes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serverID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID de serveur. Correspond à l’ID d’instance du magasin central de gestion.</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Adresse de serveur utilisant l’adresse WCF (Windows Communication Foundation).</p></td>
</tr>
<tr class="odd">
<td><p>serverLastPingTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Dernière fois où le serveur de canal a mis à jour cette ligne pour faire la preuve de son exécution.</p></td>
</tr>
</tbody>
</table>


### Clé

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serverID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>

