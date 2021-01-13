---
title: Liste des tables de conformité du serveur de conversation permanente dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité de conversation permanente se compose des tableaux suivants.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813054"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="947da-103">Liste des tables de conformité du serveur de conversation permanente dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="947da-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="947da-104">Le schéma de base de données de conformité de conversation permanente se compose des tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="947da-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="947da-105">Liste des tables de serveur de conformité de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="947da-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="947da-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="947da-106">**Table**</span></span>|<span data-ttu-id="947da-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="947da-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="947da-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="947da-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="947da-109">Contient les événements de conformité qui n’ont pas encore été traités par la carte configurée.</span><span class="sxs-lookup"><span data-stu-id="947da-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="947da-110">Ce tableau inclut les événements de conversation permanente, tels que les messages de conversation et les téléchargements de fichiers.</span><span class="sxs-lookup"><span data-stu-id="947da-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="947da-111">(Les événements des participants sont suivis par la table tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="947da-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="947da-112">(Les serveurs qui ont traité les événements de cette table sont répertoriés dans la table tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="947da-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="947da-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="947da-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="947da-114">Contient les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="947da-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="947da-115">Celle-ci est étroitement associée à la table tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="947da-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="947da-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="947da-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="947da-117">Contient les participants actifs par service de conversation et par serveur.</span><span class="sxs-lookup"><span data-stu-id="947da-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="947da-118">Il est maintenu en fonction des événements de conformité de jointrie et de partie reçus du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="947da-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="947da-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="947da-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="947da-120">Contient les informations d’état de conformité au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="947da-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

