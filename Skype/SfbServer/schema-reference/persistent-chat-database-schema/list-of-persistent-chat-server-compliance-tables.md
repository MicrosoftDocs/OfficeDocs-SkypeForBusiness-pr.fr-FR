---
title: Liste des tableaux de conformité permanente Chat Server dans Skype pour Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité Chat persistant est constitué par les tableaux suivants.
ms.openlocfilehash: 801e8d5457a26ef968f700df16a68d36560548c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="dad7d-103">Liste des tableaux de conformité permanente Chat Server dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="dad7d-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="dad7d-104">Le schéma de base de données de conformité Chat persistant est constitué par les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="dad7d-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="dad7d-105">Liste des Tables de la conformité permanente de Chat Server</span><span class="sxs-lookup"><span data-stu-id="dad7d-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="dad7d-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="dad7d-106">**Table**</span></span>|<span data-ttu-id="dad7d-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="dad7d-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="dad7d-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="dad7d-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="dad7d-109">Contient les événements de conformité qui n’ont pas encore été traitées par l’adaptateur configuré.</span><span class="sxs-lookup"><span data-stu-id="dad7d-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="dad7d-110">Ce tableau inclut les événements liés à Chat persistants, tels que des messages de conversation et les téléchargements de fichiers.</span><span class="sxs-lookup"><span data-stu-id="dad7d-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="dad7d-111">(Les événements participant sont suivis par la table de tblComplianceParticipant).</span><span class="sxs-lookup"><span data-stu-id="dad7d-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="dad7d-112">(Les serveurs de traitement des événements dans cette table sont répertoriés dans le tableau tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="dad7d-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="dad7d-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="dad7d-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="dad7d-114">Contient les serveurs dont le traitement d’un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="dad7d-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="dad7d-115">Cette table est étroitement associée à la table tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="dad7d-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="dad7d-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="dad7d-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="dad7d-117">Contient des participants en cours par le service chat et par serveur.</span><span class="sxs-lookup"><span data-stu-id="dad7d-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="dad7d-118">Il est conservé en fonction des événements de conformité jointure et une partie reçus du service Chat persistant.</span><span class="sxs-lookup"><span data-stu-id="dad7d-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="dad7d-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="dad7d-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="dad7d-120">Contient des informations d’état de conformité de l’ensemble du pool.</span><span class="sxs-lookup"><span data-stu-id="dad7d-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

