---
title: 'Lync Server 2013 : Liste des tables de conformité avec le serveur de conversation permanente'
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
ms.openlocfilehash: 3c4f6e9622e839e2f1fd719b8e2d7ba95286247e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Liste des tables de conformité avec le serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Le schéma de base de données de conformité des conversations permanentes se compose des tables suivantes.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste des tables de compatibilité de serveur Chat permanent


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
<td><p>Contient les événements de conformité qui n’ont pas encore été traités par l’adaptateur configuré.</p>
<p>Le tableau suivant contient des événements liés à des discussions permanentes, tels que des messages de discussion et des téléchargements de fichiers. (Les événements de participants sont suivis par la table tblComplianceParticipant.)</p>
<p>(Les serveurs qui ont géré les événements dans ce tableau apparaissent dans la table tblComplianceFanout.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout dans Lync Server 2013</a></p></td>
<td><p>Contient les serveurs qui ont traité un événement de conformité. Ce tableau est étroitement couplé à la table tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant dans Lync Server 2013</a></p></td>
<td><p>Contient les participants actuels par service de conversation et par serveur. Elle est conservée en fonction des événements de jointure et de conformité de partie reçus du service de chat permanent.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState dans Lync Server 2013</a></p></td>
<td><p>Contient des informations sur l’état de conformité au pool.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

