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

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="c5e04-102">Liste des tables de conformité avec le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5e04-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5e04-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="c5e04-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="c5e04-104">Le schéma de base de données de conformité des conversations permanentes se compose des tables suivantes.</span><span class="sxs-lookup"><span data-stu-id="c5e04-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="c5e04-105">Liste des tables de compatibilité de serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="c5e04-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5e04-106">Table</span><span class="sxs-lookup"><span data-stu-id="c5e04-106">Table</span></span></th>
<th><span data-ttu-id="c5e04-107">Description</span><span class="sxs-lookup"><span data-stu-id="c5e04-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5e04-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e04-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e04-109">Contient les événements de conformité qui n’ont pas encore été traités par l’adaptateur configuré.</span><span class="sxs-lookup"><span data-stu-id="c5e04-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="c5e04-110">Le tableau suivant contient des événements liés à des discussions permanentes, tels que des messages de discussion et des téléchargements de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c5e04-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="c5e04-111">(Les événements de participants sont suivis par la table tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="c5e04-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="c5e04-112">(Les serveurs qui ont géré les événements dans ce tableau apparaissent dans la table tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="c5e04-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e04-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e04-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e04-114">Contient les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="c5e04-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="c5e04-115">Ce tableau est étroitement couplé à la table tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="c5e04-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e04-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e04-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e04-117">Contient les participants actuels par service de conversation et par serveur.</span><span class="sxs-lookup"><span data-stu-id="c5e04-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="c5e04-118">Elle est conservée en fonction des événements de jointure et de conformité de partie reçus du service de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="c5e04-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e04-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e04-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e04-120">Contient des informations sur l’état de conformité au pool.</span><span class="sxs-lookup"><span data-stu-id="c5e04-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

