---
title: 'Lync Server 2013 : tblComplianceParticipant'
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558655(v=OCS.15)
ms:contentKeyID: 49297345
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceParticipant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblComplianceParticipant contient les participants actifs, par canal et par serveur.

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255), non null</p></td>
<td><p>URI (Uniform Resource Identifier) du canal.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>entier, non null</p></td>
<td><p>ID Principal du participant (correspondant à la table tblPrincipal.prinID).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage de l’événement qui se joint.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>Null si le participant est encore joint. Horodatage de l’événement qui quitte le canal s’il n’est pas null.</p>
<p>Ces entrées finissent par être supprimées lorsque tous les convertisseurs traitent l’événement.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255), non null</p></td>
<td><p>URI de l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>Int</p></td>
<td><p>Identité du serveur (comme dans tblServerIdentity.serverID table).</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>Session du serveur. Il s’agit d’un nombre aléatoire généré chaque fois que le service de conversation démarre. Il sert à différencier les sessions dans le but d’identifier les participants orphelins.</p></td>
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
<td><p>&lt;channelUri, userId, joinedAt&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>

