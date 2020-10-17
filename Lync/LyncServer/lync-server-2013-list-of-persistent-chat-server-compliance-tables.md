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
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="9d824-103">Liste des tables de conformité du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d824-103">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d824-104">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9d824-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9d824-105">Le schéma de la base de données de conformité de la conversation permanente se compose des tables suivantes.</span><span class="sxs-lookup"><span data-stu-id="9d824-105">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="9d824-106">Liste des tables de serveur de conformité de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="9d824-106">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d824-107">Table</span><span class="sxs-lookup"><span data-stu-id="9d824-107">Table</span></span></th>
<th><span data-ttu-id="9d824-108">Description</span><span class="sxs-lookup"><span data-stu-id="9d824-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d824-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9d824-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9d824-110">Contient les événements de conformité qui n’ont pas encore été traités par la carte configurée.</span><span class="sxs-lookup"><span data-stu-id="9d824-110">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="9d824-111">Ce tableau comprend les événements persistants liés à la conversation, tels que les messages de conversation et les téléchargements de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9d824-111">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="9d824-112">(Les événements des participants sont suivis par la table tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="9d824-112">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="9d824-113">(Les serveurs qui ont traité les événements de cette table sont répertoriés dans la table tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="9d824-113">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d824-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9d824-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9d824-115">Contient les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="9d824-115">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="9d824-116">Celle-ci est étroitement associée à la table tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="9d824-116">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d824-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9d824-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9d824-118">Contient les participants actifs par service de conversation et par serveur.</span><span class="sxs-lookup"><span data-stu-id="9d824-118">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="9d824-119">Elle est conservée en fonction des événements de conformité et de participation reçus du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="9d824-119">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d824-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9d824-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9d824-121">Contient les informations d’état de conformité au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="9d824-121">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

