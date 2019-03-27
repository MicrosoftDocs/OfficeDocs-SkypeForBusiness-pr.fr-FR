---
title: Liste des tables de conformité Persistent Chat Server dans Skype pour Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité conversation permanente comprend les tables suivantes.
ms.openlocfilehash: 18c35cc71da43dcf25bb477e81a2471b483ee86d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874314"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="4b2a6-103">Liste des tables de conformité Persistent Chat Server dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4b2a6-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="4b2a6-104">Le schéma de base de données de conformité conversation permanente comprend les tables suivantes.</span><span class="sxs-lookup"><span data-stu-id="4b2a6-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="4b2a6-105">Liste des Tables de conformité de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="4b2a6-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="4b2a6-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="4b2a6-106">**Table**</span></span>|<span data-ttu-id="4b2a6-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="4b2a6-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4b2a6-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="4b2a6-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="4b2a6-109">Contient les événements de conformité qui n’ont pas encore été traitées par la carte configurée.</span><span class="sxs-lookup"><span data-stu-id="4b2a6-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="4b2a6-110">Ce tableau inclut les événements liés à la conversation permanente, telles que les messages de conversation et les téléchargements de fichiers.</span><span class="sxs-lookup"><span data-stu-id="4b2a6-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="4b2a6-111">(Participant événements suivis par le tableau tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="4b2a6-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="4b2a6-112">(Les serveurs qui ont traité les événements de cette table sont répertoriés dans la table tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="4b2a6-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="4b2a6-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="4b2a6-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="4b2a6-114">Contient les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="4b2a6-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="4b2a6-115">Ce tableau est étroitement associé à la table tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="4b2a6-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="4b2a6-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="4b2a6-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="4b2a6-117">Contient les participants actifs par le service de conversation et par serveur.</span><span class="sxs-lookup"><span data-stu-id="4b2a6-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="4b2a6-118">Il est conservé en fonction des événements de conformité join et composant reçus à partir du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="4b2a6-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="4b2a6-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="4b2a6-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="4b2a6-120">Contient des informations d’état de conformité au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="4b2a6-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

