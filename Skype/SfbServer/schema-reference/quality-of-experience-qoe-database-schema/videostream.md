---
title: Table VideoStream
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Chaque enregistrement représente un flux vidéo. Une ligne de média vidéo contient généralement deux flux vidéo.
ms.openlocfilehash: 27a9c8cdd8b1975b7854147b5855a8494155ce2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="videostream-table"></a>Table VideoStream
 
Chaque enregistrement représente un flux vidéo. Une ligne de média vidéo contient généralement deux flux vidéo.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |R est référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |ID unique d’une ligne de media.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Étranger, principal  <br/> |Description de la charge utile. Consultez le [tableau de PayloadDescription](payloaddescription.md) pour plus d’informations. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Instabilité du réseau moyenne à partir des statistiques de protocole de contrôle en temps réel (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Bougé maximal du réseau au cours de la session vidéo.  <br/> |
|**Aller-retour** <br/> |int  <br/> | <br/> |Délai d’aller-retour à partir des statistiques RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Temps d’aller-retour maximale du flux vidéo.  <br/> |
|**PacketLossRate** <br/> |Decimal(5,4)  <br/> | <br/> |Taux de perte de paquet moyenne lors de l’appel.  <br/> |
|**PacketLossRateMax** <br/> |Decimal(5,4)  <br/> | <br/> |Perte de paquet maximale observée au cours de l’appel.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Nombre de paquets de flux vidéo (temps réel Transport Protocol, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Estimations de la bande passante pour le flux vidéo.  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |Résolution de la vidéo dans multiplié par la hauteur des pixels pixels de large. Signalé comme une chaîne.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Vitesse de transmission moyenne du flux vidéo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |Decimal(9,4)  <br/> | <br/> |La fréquence d’image reçue.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |Decimal(9,4)  <br/> | <br/> |Le taux d’image vidéo envoyé.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Le débit vidéo maximal au cours de la session vidéo.  <br/> |
|**VideoFrameLossRate** <br/> |Decimal(9,4)  <br/> | <br/> |Pourcentage du nombre total de trames vidéo qui sont perdues.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |N’est pas disponible.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |Decimal(9,4)  <br/> ||Pourcentage du nombre total de trames vidéo qui sont perdues.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Le pourcentage de l’appel qui était à la résolution de Common Interchange Format (caf).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Le pourcentage de l’appel qui était en résolution VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Le pourcentage de l’appel qui était à la résolution de HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Pourcentage de durée d’appel avec aucune perte d’image.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Pourcentage de durée d’appel avec perte d’image B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Pourcentage de durée d’appel avec perte d’image de fond de panier.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Pourcentage de durée d’appel avec perte d’image BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Pourcentage de durée d’appel avec perte d’image BPSPI.  <br/> |
|**Trafic entrant** <br/> |bit  <br/> | <br/> |Réception des données de flux sur le récepteur.  <br/> |
|**Sortant** <br/> |bit  <br/> | <br/> |Réception des données de flux sur le côté de l’expéditeur.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 signifie que la direction du flux de données est de l’appelant à l’appelé.  <br/> 0 signifie que la direction du flux de données est de l’appelé vers l’appelant.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’heure de l’appel dans un état de congestion de perte.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’appel au cours de laquelle congestion a été provoquée par l’arrivée de retardée des paquets réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indique le pourcentage du temps lorsque l’appel a été en compétition pour les ressources réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Montant minimal d’estimation de la bande passante est mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Durée estimation de la bande passante maximale mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Écart-type de l’estimation de la bande passante est mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durée estimation de la bande passante moyenne mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Pourcentage de l’appel dans lequel le point de terminaison déterminé que la connexion réseau ne permettaient pas de vidéo multivue.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Montant total de la latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Montant moyen de latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Montant maximal de latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occurrences de total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densité de total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée du total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occurrences de total écart à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité de total écart à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée de l’intervalle d’unilatérale total. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |Decimal(9,4)  <br/> ||Taux auquel les paquets vidéo ont été perdues.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Durée moyenne de la bande passante allouée pour la vidéo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Étrangère  <br/> |Type de codecs vidéo utilisés par l’expéditeur. Consultez le [tableau de CodecDescription](codecdescription.md) pour plus d’informations. <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Largeur de la résolution utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Hauteur de la résolution utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Transmission du taux de trame vidéo moyenne utilisée par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Vitesse de transmission maximale pour l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Vitesse de transmission moyenne de l’expéditeur.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Nombre maximal de flux vidéo utilisé par l’expéditeur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Étrangère  <br/> |Codes vidéo utilisées par le récepteur. Consultez le [tableau de CodecDescription](codecdescription.md) pour plus d’informations. <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Largeur de résolution utilisé par le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Hauteur de résolution utilisé par le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Taux de trame vidéo moyenne utilisé par le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Vitesse de transmission maximale pour le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Vitesse de transmission moyenne du récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Flux vidéo maximales pour le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Flux vidéo minimales pour le récepteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Mode vidéo (par exemple, la galerie ou flux de données unique) pour le destinataire.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Taux de perte de paquets après que correction aval des erreurs a été appliquée.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Pourcentage de temps que l’indicateur de fonctionnalité dynamique a été active.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char (9)  <br/> ||Résolution minimale mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel en dessous du seuil de taux faible (70 kilobits par seconde).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel au-dessous du seuil de taux d’images (7,5 images par seconde, entrantes).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Pourcentage de l’appel qui a eu lieu à la résolution la plus basse.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Durée de l’appel en secondes.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indique si les données ont été collectées à partir des appels multiples.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

