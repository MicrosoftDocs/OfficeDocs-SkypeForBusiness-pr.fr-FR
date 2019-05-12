---
title: Exemples de requête de base de données QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: Cette section contient des exemples de requêtes pour la base de données de qualité de l’expérience (QoE).
ms.openlocfilehash: bd9cbebba26b18fcabd70417716f3f94153ef133
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920179"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="40b15-103">Exemples de requête de base de données QoE</span><span class="sxs-lookup"><span data-stu-id="40b15-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="40b15-104">Cette section contient des exemples de requêtes pour la base de données de qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="40b15-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="40b15-105">L’exemple suivant permet d’obtenir la gigue et paquet perte moyenne de tous les flux audio.</span><span class="sxs-lookup"><span data-stu-id="40b15-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="40b15-106">L’exemple suivant permet de trouver le nombre total de conférences qui ont utilisé la Console de réunion.</span><span class="sxs-lookup"><span data-stu-id="40b15-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
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

<span data-ttu-id="40b15-107">L’exemple suivant permet d’obtenir ConversstionalMOS, SendingMOS et ListendingMOS par le périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="40b15-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
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
