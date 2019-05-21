---
title: Table VideoStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Chaque enregistrement représente un flux vidéo. Une ligne de média vidéo contient généralement deux flux vidéo.
ms.openlocfilehash: 678f8b14fb3746ddd50a83ebd68c3878237908e4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294522"
---
# <a name="videostream-table"></a>Table VideoStream
 
Chaque enregistrement représente un flux vidéo. Une ligne de média vidéo contient généralement deux flux vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |R référencé à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |IDENTIFIant unique dans une ligne de médias.  <br/> |
|**VideoPayloadDescription** <br/> |type  <br/> |Étranger, primaire  <br/> |Description de la charge utile. Pour plus d’informations, voir la [table PayloadDescription](payloaddescription.md) . <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Scintillement du réseau maximum lors de la session vidéo.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Durée de l’aller-retour des statistiques RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Durée de l’aller-retour maximal pour le flux vidéo.  <br/> |
|**PacketLossRate** <br/> |décimale (5; 4)  <br/> | <br/> |Taux moyen de perte de paquets lors de l’appel.  <br/> |
|**PacketLossRateMax** <br/> |décimale (5; 4)  <br/> | <br/> |Perte de paquets maximum observée pendant l’appel.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).  <br/> |
|**Bande passante** <br/> |int  <br/> | <br/> |Estimations de bande passante pour le flux vidéo.  <br/> |
|**VideoResolution** <br/> |car (9)  <br/> | <br/> |Résolution de la vidéo, en pixels, de largeur multipliée par la hauteur en pixels. Signalée en tant que chaîne.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Vitesse de transmission moyenne du flux vidéo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |décimale (9; 4)  <br/> | <br/> |Fréquence d’images vidéo reçues.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |décimale (9; 4)  <br/> | <br/> |Fréquence d’images vidéo envoyées.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Débit vidéo maximum lors de la session vidéo.  <br/> |
|**VideoFrameLossRate** <br/> |décimale (9; 4)  <br/> | <br/> |Pourcentage du nombre total de trames vidéo perdues.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Non disponible.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |décimale (9; 4)  <br/> ||Pourcentage du nombre total de trames vidéo perdues.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel à la résolution CAF (Common Interchange Format).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel à la résolution VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel passé à la résolution HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel sans cadre.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec la dépose de l’image B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec la liste déroulante.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec BPSP Frame.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec BPSPI Frame.  <br/> |
|**Entrant** <br/> |bit  <br/> | <br/> |Des données de flux sur le côté du destinataire sont reçues.  <br/> |
|**Sortant** <br/> |bit  <br/> | <br/> |Les données du flux du côté de l’expéditeur sont reçues.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 signifie que le sens du flux provient de l’appelant vers l’appel.  <br/> 0: le sens du flux provient de l’appelant.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage du temps pendant lequel l’appel a été dans un état de congestion de perte.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’appel au cours duquel une congestion est causée par le retard de paquets réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indique le pourcentage de temps pendant lequel l’appel a été compétitif pour les ressources réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantité minimale d’estimation de la bande passante mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantité maximale d’estimation de la bande passante mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Écart type de l’estimation de la bande passante mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantité moyenne d’estimation de bande passante mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau n’a pas pu prendre en charge la vidéo multivue.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**Moyenne unidirectionnelle relative** <br/> |float  <br/> ||Quantité moyenne de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de rafales à sens unique. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densité du Burst total unidirectionnel. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale du Burst. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de l’espacement unidirectionnel. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité de l’intervalle total à sens unique. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée totale de l’intervalle. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**Cause du taux** <br/> |décimale (9; 4)  <br/> ||Taux d’interruption des paquets vidéo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Quantité moyenne de bande passante allouée pour la vidéo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |type  <br/> |Externes  <br/> |Type de codecs vidéo utilisés par l’expéditeur. Pour plus d’informations, voir la [table CodecDescription](codecdescription.md) . <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Largeur de résolution utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Hauteur de résolution utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Transmission moyenne de la fréquence d’images vidéo utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Taux de bits maximal pour l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Taux de bits moyen pour l’expéditeur.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Nombre maximal de flux vidéo utilisés par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |type  <br/> |Externes  <br/> |Codes vidéo utilisés par le destinataire. Pour plus d’informations, voir la [table CodecDescription](codecdescription.md) . <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Largeur de résolution utilisée par le destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Hauteur de résolution utilisée par le destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**Cause reçues** <br/> |float  <br/> ||Fréquence d’images vidéo moyenne utilisée par le destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Vitesse de transmission maximale du destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Taux de bits moyen pour le destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Flux vidéo maximal pour le destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Flux vidéo minimal pour le destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Mode vidéo (par exemple, Galerie ou flux unique) pour le destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Taux de perte de paquets après application de la correction d’erreur de transfert.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**Cause du pourcentage** <br/> |float  <br/> ||Pourcentage de temps pendant lequel l’indicateur de capacité dynamique a été actif.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |car (9)  <br/> ||Résolution minimale mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel inférieur au seuil de faible taux de bits (70 kilobits par seconde).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**Cause du pourcentage** <br/> |float  <br/> ||Pourcentage de l’appel inférieur au seuil de fréquence d’images faible (7,5 images par seconde, entrant).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**Cause du pourcentage** <br/> |float  <br/> ||Pourcentage de l’appel qui s’est produit à la résolution la plus basse.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Durée de l’appel en secondes.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indique si les données ont été agrégées à partir de plusieurs appels.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

