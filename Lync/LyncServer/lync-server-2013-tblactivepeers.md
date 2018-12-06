---
title: 'Lync Server 2013 : tblActivePeers'
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615030(v=OCS.15)
ms:contentKeyID: 49298598
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblActivePeers dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

ActivePeers contient les connexions P2P actuelles entre les services de conversation.

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
<td><p>aplServerID</p></td>
<td><p>int, non null</p></td>
<td><p>ID du serveur ayant publié l’entrée.</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>int, non null</p></td>
<td><p>ID de l’homologue auquel est connecté le serveur de publication.</p></td>
</tr>
</tbody>
</table>


### Clés

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
<td><p>&lt;aplServerID, aplPeerID&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>aplServerID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblServerIdentity.serverID.</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblServerIdentity.serverID.</p></td>
</tr>
</tbody>
</table>

