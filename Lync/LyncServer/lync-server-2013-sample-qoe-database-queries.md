---
title: 'Lync Server 2013 : Exemples de requête de base de données QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sample QoE database queries
ms:assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398100(v=OCS.15)
ms:contentKeyID: 48183280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e26da6f9e7ed26b4cce896401ed497ed8376f37b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sample-qoe-database-queries-in-lync-server-2013"></a><span data-ttu-id="53e17-102">Exemples de requête de base de données QoE dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53e17-102">Sample QoE database queries in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53e17-103">_**Dernière modification de la rubrique:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="53e17-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="53e17-104">Cette section contient des exemples de requêtes pour la base de données de qualité de l’expertise (QoE).</span><span class="sxs-lookup"><span data-stu-id="53e17-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span>

<span data-ttu-id="53e17-105">Utilisez l’exemple suivant pour obtenir le taux de gigue et de perte de paquets pour tous les flux audio.</span><span class="sxs-lookup"><span data-stu-id="53e17-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>

    select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream

<span data-ttu-id="53e17-106">Pour connaître le nombre total de conférences à l’aide de la console de réunion, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="53e17-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>

    select avg(ConversationalMOS)
    from SessionView s
    inner join MediaLineView m
    on s.ConferenceDateTime = m.ConferenceDateTime
       and s.SessionSeq = m.SessionSeq
       and m.MediaLineLabel = 0 -- audio media line
       and s.CallerUserAgentType = 4 -- Lync
       and s.CalleeUserAgentType = 4 -- Lync

<span data-ttu-id="53e17-107">Pour obtenir ConversstionalMOS, SendingMOS et ListendingMOS par appareil de capture, utilisez l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="53e17-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>

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

</div>

<span> </span>

</div>

</div>

</div>

