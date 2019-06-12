---
title: 'Lync Server 2013 : tblActivePeers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb6089cfa3f3a9da8103dd0d0691031dac05d05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a>tblActivePeers dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-29_

tblActivePeers contient les connexions d’égal à égal actuelles entre les services de discussion.

### <a name="columns"></a>Celles

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
<td><p>ent, non null</p></td>
<td><p>ID du serveur qui a publié l’entrée.</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>ent, non null</p></td>
<td><p>ID de l’homologue auquel est connecté le serveur de publication.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Permettent

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
<td><p>Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

