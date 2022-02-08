---
title: Table VideoStream
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Chaque enregistrement représente un flux vidéo. Une ligne de média vidéo contient généralement deux flux vidéo.
ms.openlocfilehash: b6a67f6bc6c968e997882fb6406e7dc43d1ba7c4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393566"
---
# <a name="videostream-table"></a>Table VideoStream
 
Chaque enregistrement représente un flux vidéo. Une ligne de média vidéo contient généralement deux flux vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |R référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primaire  <br/> |ID unique dans une ligne de média.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Étranger, Principal  <br/> |Description de la charge utile. Pour plus [d’informations, voir la table PayloadDescription](payloaddescription.md) . <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Gigue réseau maximale pendant la session vidéo.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Durée d’aller-retour d’après les statistiques RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Durée maximale d’aller-retour pour le flux vidéo.  <br/> |
|**PacketLossRate** <br/> |décimal(5,4)  <br/> | <br/> |Taux moyen de perte de paquets pendant l’appel.  <br/> |
|**PacketLossRateMax** <br/> |décimal(5,4)  <br/> | <br/> |Perte maximale de paquets observée pendant l’appel.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Nombre de paquets pour le flux vidéo (protocole de transport en temps réel, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Estimations de bande passante pour le flux vidéo.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Résolution de la vidéo en pixels de largeur multipliée par la hauteur des pixels. Signalé sous la mesure d’une chaîne.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Vitesse de bit moyenne du flux vidéo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |décimal(9,4)  <br/> | <br/> |Fréquence d’images vidéo reçues.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |décimal(9,4)  <br/> | <br/> |Fréquence d’images vidéo envoyées.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Vitesse de bits vidéo maximale pendant la session vidéo.  <br/> |
|**VideoFrameLossRate** <br/> |décimal(9,4)  <br/> | <br/> |Pourcentage du nombre total d’images vidéo perdues.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Non disponible.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |décimal(9,4)  <br/> ||Pourcentage du nombre total d’images vidéo perdues.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel qui était à la résolution CIF (Common Interchange Format).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel à résolution VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel à résolution HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel sans aucune image.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec une image B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec une baisse de trame BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec une baisse de trame BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec une baisse des images BPSPI.  <br/> |
|**Entrant** <br/> |bit  <br/> | <br/> |Les données de flux côté récepteur sont reçues.  <br/> |
|**Sortant** <br/> |bit  <br/> | <br/> |Les données de flux côté expéditeur sont reçues.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 signifie que la direction du flux va de l’appelant à l’appelé.  <br/> 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage du temps où l’appel était dans un état de congestion de perte.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’appel pendant lequel la congestion a été causée par l’arrivée retardée de paquets réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indique le pourcentage du temps où l’appel était en concurrence pour les ressources réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantité minimale d’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantité maximale d’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Écart-type de l’estimation de la bande passante mesuré pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantité moyenne d’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau ne pouvait pas prendre en charge la vidéo multiview.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densité totale des rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale des rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences d’intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité totale des intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée totale des intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |décimal(9,4)  <br/> ||Taux auquel les paquets vidéo ont été perdus.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Quantité moyenne de bande passante allouée à la vidéo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Étranger  <br/> |Type de codecs vidéo utilisés par l’expéditeur. Pour plus [d’informations, voir la table CodecDescription](codecdescription.md) . <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Largeur de résolution utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Hauteur de résolution utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Transmission moyenne de fréquence d’images vidéo utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Vitesse de bits maximale pour l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Vitesse de bits moyenne de l’expéditeur.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Nombre maximal de flux vidéo utilisés par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Étranger  <br/> |Codes vidéo utilisés par le récepteur. Pour plus [d’informations, voir la table CodecDescription](codecdescription.md) . <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Largeur de résolution utilisée par le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Hauteur de résolution utilisée par le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Fréquence d’images vidéo moyenne utilisée par le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Vitesse de bits maximale pour le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Vitesse de bit moyenne pour le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Nombre maximal de flux vidéo pour le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Flux vidéo minimaux pour le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Mode vidéo (par exemple, galerie ou flux unique) pour le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Taux de perte de paquets après l’application de la correction des erreurs de forward.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Pourcentage de temps d’activité de l’indicateur de fonctionnalité dynamique.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Résolution minimale mesurée pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel inférieur au seuil de faible vitesse de bits (70 kilobits par seconde).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel inférieur au seuil de fréquence d’images faible (7,5 images par seconde, entrant).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel qui s’est produit à la résolution la plus faible.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Durée de l’appel en secondes.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indique si les données ont été agrégées à partir de plusieurs appels.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

