---
title: 'Lync Server 2013 : tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>tblComplianceParticipant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-12_

tblComplianceParticipant contient les participants actuels par canal et par serveur.

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255), pas null</p></td>
<td><p>URI (Uniform Resource Identifier) de canal.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>ent, non null</p></td>
<td><p>ID principal du participant (correspondant à la table tblPrincipal. prinID).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint, pas null</p></td>
<td><p>Date et heure de l’événement de jointure.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>NULL si le participant reste connecté. Horodatage du canal quittant l’événement s’il n’a pas la valeur null.</p>
<p>Ces entrées sont finalement supprimées lorsque tous les traducteurs traitent l’événement.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255), pas null</p></td>
<td><p>URI de l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>Identité du serveur (comme dans la table tblServerIdentity. serverID).</p></td>
</tr>
<tr class="odd">
<td><p>ID</p></td>
<td><p>bigint</p></td>
<td><p>Session du serveur. Il s’agit d’un nombre aléatoire généré chaque fois qu’un service de conversation démarre. Il est utilisé pour différencier les sessions à des fins d’identification de participants orphelins.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Clé

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


</div>

<span> </span>

</div>

</div>

</div>

