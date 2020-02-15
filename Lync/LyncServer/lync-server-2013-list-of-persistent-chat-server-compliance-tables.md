---
title: 'Lync Server 2013 : liste des tables de conformité du serveur de conversation permanente'
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
ms.openlocfilehash: fab78f554c94e11c808eeb28929d6b4511c3a695
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="4f799-102">Liste des tables de conformité du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f799-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f799-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="4f799-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="4f799-104">Le schéma de la base de données de conformité de la conversation permanente se compose des tables suivantes.</span><span class="sxs-lookup"><span data-stu-id="4f799-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="4f799-105">Liste des tables de serveur de conformité de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="4f799-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f799-106">Table</span><span class="sxs-lookup"><span data-stu-id="4f799-106">Table</span></span></th>
<th><span data-ttu-id="4f799-107">Description</span><span class="sxs-lookup"><span data-stu-id="4f799-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f799-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4f799-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4f799-109">Contient les événements de conformité qui n’ont pas encore été traités par la carte configurée.</span><span class="sxs-lookup"><span data-stu-id="4f799-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="4f799-110">Ce tableau comprend les événements persistants liés à la conversation, tels que les messages de conversation et les téléchargements de fichiers.</span><span class="sxs-lookup"><span data-stu-id="4f799-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="4f799-111">(Les événements des participants sont suivis par la table tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="4f799-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="4f799-112">(Les serveurs qui ont traité les événements de cette table sont répertoriés dans la table tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="4f799-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f799-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4f799-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4f799-114">Contient les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="4f799-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="4f799-115">Celle-ci est étroitement associée à la table tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="4f799-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f799-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4f799-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4f799-117">Contient les participants actifs par service de conversation et par serveur.</span><span class="sxs-lookup"><span data-stu-id="4f799-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="4f799-118">Elle est conservée en fonction des événements de conformité et de participation reçus du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="4f799-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f799-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4f799-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4f799-120">Contient les informations d’état de conformité au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="4f799-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

