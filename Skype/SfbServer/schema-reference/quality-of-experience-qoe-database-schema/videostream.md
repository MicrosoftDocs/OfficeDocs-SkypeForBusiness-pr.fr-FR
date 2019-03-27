---
title: Table VideoStream
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Chaque enregistrement représente un flux vidéo. Généralement, une seule ligne de média vidéo contient deux flux vidéo.
ms.openlocfilehash: d6eeeb96acc766859d6b57594bd11a5538593da3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881680"
---
# <a name="videostream-table"></a>Table VideoStream
 
Chaque enregistrement représente un flux vidéo. Généralement, une seule ligne de média vidéo contient deux flux vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |R référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |ID unique au sein d’une ligne de média.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Étrangère, primaire  <br/> |Description de la charge utile. Consultez la [table PayloadDescription](payloaddescription.md) pour plus d’informations. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Gigue réseau moyenne à partir des statistiques de contrôle protocole RTCP (Real Time).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Gigue réseau maximum au cours de la session vidéo.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Durée d’aller-retour d’après les statistiques RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Durée d’aller-retour maximale pour le flux vidéo.  <br/> |
|**PacketLossRate** <br/> |Decimal(5,4)  <br/> | <br/> |Taux de perte de paquets moyenne pendant l’appel.  <br/> |
|**PacketLossRateMax** <br/> |Decimal(5,4)  <br/> | <br/> |Perte maximale de paquets observée pendant l’appel.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Estimations de la bande passante pour le flux vidéo.  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |Résolution de la vidéo en pixels de large multiplié par pixels de haut. Indiqué sous forme de chaîne.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Vitesse de transmission moyenne du flux vidéo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |Decimal(9,4)  <br/> | <br/> |Fréquence d’images vidéo reçue.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |Decimal(9,4)  <br/> | <br/> |Fréquence d’images vidéo envoyée.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Vitesse de transmission vidéo maximale au cours de la session vidéo.  <br/> |
|**VideoFrameLossRate** <br/> |Decimal(9,4)  <br/> | <br/> |Pourcentage du total des images vidéo perdues.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |N’est pas disponible.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |Decimal(9,4)  <br/> ||Pourcentage du total des images vidéo perdues.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel qui était à la résolution Interchange Format CIF (Common).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel qui était à la résolution VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Pourcentage de l’appel qui était à la résolution HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec suppression d’images.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec suppression d’images B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec images BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec images bpsp.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Pourcentage de la durée de l’appel avec images bpspi.  <br/> |
|**Trafic entrant** <br/> |bit  <br/> | <br/> |Données de flux du côté récepteur reçues.  <br/> |
|**Sortant** <br/> |bit  <br/> | <br/> |Données de flux côté expéditeur reçues.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 signifie que la direction du flux va de l’appelant vers l’appelé.  <br/> 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’heure de l’appel dans un état de congestion de perte.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’appel au cours de laquelle la congestion a été provoquée par l’arrivée en retard des paquets réseau.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indique le pourcentage du temps lorsque l’appel a été concurrentes des ressources réseau.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantité minimale de l’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantité maximale de l’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Écart-type de l’estimation de bande passante mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantité moyenne de l’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Pourcentage de l’appel où le point de terminaison déterminé que la connexion réseau ne peut pas en charge la vidéo.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de la latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantité moyenne de latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densité des rafales à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale rafale à sens unique. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité d’intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée des intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |Decimal(9,4)  <br/> ||Fréquence à laquelle les paquets vidéo ont été perdues.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Quantité moyenne de bande passante allouée à la vidéo.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Étrangère  <br/> |Type de codec vidéo utilisé par l’expéditeur. Consultez la [table CodecDescription](codecdescription.md) pour plus d’informations. <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Largeur de résolution utilisée par l’expéditeur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Hauteur de résolution utilisée par l’expéditeur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Transmission de débit d’images vidéo moyenne utilisée par l’expéditeur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Vitesse de transmission maximale pour l’expéditeur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Vitesse de transmission moyenne pour l’expéditeur.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Nombre maximal de flux vidéo utilisés par l’expéditeur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Étrangère  <br/> |Codes vidéo utilisées par le récepteur. Consultez la [table CodecDescription](codecdescription.md) pour plus d’informations. <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Largeur de résolution utilisée par le récepteur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Hauteur de résolution utilisée par le récepteur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Fréquence d’images vidéo moyenne utilisée par le récepteur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Vitesse de transmission maximale pour le récepteur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Vitesse de transmission moyenne pour le récepteur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Flux vidéo maximaux pour le récepteur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Flux vidéo minimales pour le récepteur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Mode vidéo (par exemple, galerie ou flux unique) pour le récepteur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Taux de perte de paquets après que la correction d’erreur de transfert a été appliquée.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Pourcentage de temps que l’indicateur de capacité dynamique a été actif.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char (9)  <br/> ||Résolution minimale mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel inférieur au seuil de taux de transmission faible (70 kilobits par seconde).  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel inférieur au seuil de fréquence d’images basse (7,5 images par seconde, entrantes).  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel qui était la plus faible résolution.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Durée de l’appel en secondes.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indique si les données ont été collectées à partir de plusieurs appels.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
   

