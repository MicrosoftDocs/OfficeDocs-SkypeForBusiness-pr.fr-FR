﻿---
title: 'Lync Server 2013 : Exemples de requête de base de données QoE'
TOCTitle: Exemples de requête de base de données QoE
ms:assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398100(v=OCS.15)
ms:contentKeyID: 49296117
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exemples de requête de base de données QoE dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-17_

Cette section contient des exemples de requêtes pour la base de données QoE (Quality of Experience).

Utilisez l’exemple suivant pour obtenir la moyenne de la gigue et de la perte de paquets pour tous les flux audio.

    select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream

Utilisez l’exemple suivant pour trouver le nombre total de conférences qui ont utilisé la console de réunion.

    select avg(ConversationalMOS)
    from SessionView s
    inner join MediaLineView m
    on s.ConferenceDateTime = m.ConferenceDateTime
       and s.SessionSeq = m.SessionSeq
       and m.MediaLineLabel = 0 -- audio media line
       and s.CallerUserAgentType = 4 -- Lync
       and s.CalleeUserAgentType = 4 -- Lync

Utilisez l’exemple suivant pour obtenir ConversstionalMOS, SendingMOS et ListendingMOS par appareil capturé.

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

