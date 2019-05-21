---
title: Liste des tables de conformité serveur Chat permanent dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité des conversations permanentes se compose des tables suivantes.
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295656"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="23b91-103">Liste des tables de conformité serveur Chat permanent dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="23b91-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="23b91-104">Le schéma de base de données de conformité des conversations permanentes se compose des tables suivantes.</span><span class="sxs-lookup"><span data-stu-id="23b91-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="23b91-105">Liste des tables de compatibilité de serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="23b91-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="23b91-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="23b91-106">**Table**</span></span>|<span data-ttu-id="23b91-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="23b91-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="23b91-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="23b91-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="23b91-109">Contient les événements de conformité qui n’ont pas encore été traités par l’adaptateur configuré.</span><span class="sxs-lookup"><span data-stu-id="23b91-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="23b91-110">Le tableau suivant contient des événements liés à des discussions permanentes, tels que des messages de discussion et des téléchargements de fichiers.</span><span class="sxs-lookup"><span data-stu-id="23b91-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="23b91-111">(Les événements de participants sont suivis par la table tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="23b91-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="23b91-112">(Les serveurs qui ont géré les événements dans ce tableau apparaissent dans la table tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="23b91-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="23b91-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="23b91-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="23b91-114">Contient les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="23b91-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="23b91-115">Ce tableau est étroitement couplé à la table tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="23b91-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="23b91-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="23b91-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="23b91-117">Contient les participants actuels par service de conversation et par serveur.</span><span class="sxs-lookup"><span data-stu-id="23b91-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="23b91-118">Elle est conservée en fonction des événements de jointure et de conformité de partie reçus du service de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="23b91-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="23b91-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="23b91-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="23b91-120">Contient des informations sur l’état de conformité au pool.</span><span class="sxs-lookup"><span data-stu-id="23b91-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

