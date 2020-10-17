---
title: 'Lync Server 2013 : liste des tables de conformité du serveur de conversation permanente'
description: 'Lync Server 2013 : liste des tables de conformité du serveur de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47cb28a0ca4180327c2adc48d80e9e41171a7bfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550070"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Liste des tables de conformité du serveur de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Le schéma de la base de données de conformité de la conversation permanente se compose des tables suivantes.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste des tables de serveur de conformité de la conversation permanente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData dans Lync Server 2013</a></p></td>
<td><p>Contient les événements de conformité qui n’ont pas encore été traités par la carte configurée.</p>
<p>Ce tableau comprend les événements persistants liés à la conversation, tels que les messages de conversation et les téléchargements de fichiers. (Les événements des participants sont suivis par la table tblComplianceParticipant.)</p>
<p>(Les serveurs qui ont traité les événements de cette table sont répertoriés dans la table tblComplianceFanout.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout dans Lync Server 2013</a></p></td>
<td><p>Contient les serveurs qui ont traité un événement de conformité. Celle-ci est étroitement associée à la table tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant dans Lync Server 2013</a></p></td>
<td><p>Contient les participants actifs par service de conversation et par serveur. Elle est conservée en fonction des événements de conformité et de participation reçus du service de conversation permanente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState dans Lync Server 2013</a></p></td>
<td><p>Contient les informations d’état de conformité au niveau du pool.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

