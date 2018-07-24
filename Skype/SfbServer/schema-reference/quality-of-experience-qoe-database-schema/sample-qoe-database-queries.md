---
title: Exemples de requête de base de données QoE
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: Cette section contient des exemples de requêtes pour la base de données de qualité de l’expérience (QoE).
ms.openlocfilehash: c66d0fdc51ee3382034f5fba1e98f93a8799f312
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020596"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="bbbda-103">Exemples de requête de base de données QoE</span><span class="sxs-lookup"><span data-stu-id="bbbda-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="bbbda-104">Cette section contient des exemples de requêtes pour la base de données de qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="bbbda-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="bbbda-105">L’exemple suivant permet d’obtenir la gigue et paquet perte moyenne de tous les flux audio.</span><span class="sxs-lookup"><span data-stu-id="bbbda-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="bbbda-106">L’exemple suivant permet de trouver le nombre total de conférences qui ont utilisé la Console de réunion.</span><span class="sxs-lookup"><span data-stu-id="bbbda-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync
```

<span data-ttu-id="bbbda-107">L’exemple suivant permet d’obtenir ConversstionalMOS, SendingMOS et ListendingMOS par le périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="bbbda-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```
select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
from
(
   select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

   union

   select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

)as t
group by t.DeviceName
order by SampleNum desc
```