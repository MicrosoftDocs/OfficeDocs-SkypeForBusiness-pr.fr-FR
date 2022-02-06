---
title: Table AudioStream
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Chaque enregistrement représente un flux audio. Une ligne de média audio contient généralement deux flux audio.
---

# <a name="audiostream-table"></a>Table AudioStream
 
Chaque enregistrement représente un flux audio. Une ligne de média audio contient généralement deux flux audio.
  
|Colonne|Type de données|Clé/Index|Détails|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primaire  <br/> |ID unique dans une ligne de média.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Gigue réseau maximum pendant l’appel.  <br/> |
|**PacketLossRate** <br/> |décimal(5,4)  <br/> | <br/> |Taux moyen de perte de paquets pendant l’appel.  <br/> |
|**PacketLossRateMax** <br/> |décimal(5,4)  <br/> | <br/> |Perte maximale de paquets observée pendant l’appel.  <br/> |
|**BurstDensity** <br/> |décimal(9,4)  <br/> | <br/> |Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.  <br/> |
|**BurstGapDensity** <br/> |décimal(9,4)  <br/> | <br/> |Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durée moyenne des intervalles entre les rafales de pertes de paquets.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Nombre de paquets pour le flux audio.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|**DegradationAvg** <br/> |décimal(3,2)  <br/> | <br/> |Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.  <br/> |
|**DegradationMax** <br/> |décimal(3,2)  <br/> | <br/> |Dégradation de la note MOS qualité réseau maximale pendant l’appel.  <br/> |
|**DegradationJitterAvg** <br/> |décimal(3,2)  <br/> | <br/> |Dégradation de la note MOS qualité réseau causée par la gigue.  <br/> |
|**DegradationPacketLossAvg** <br/> |décimal(3,2)  <br/> | <br/> |Dégradation de la note MOS qualité réseau causée par la perte de paquets.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Étranger  <br/> |Codec audio utilisé pour l’appel, référencé à partir de la table PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Taux d’échantillonnage pour le flux audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Durée d’aller-retour d’après les statistiques RTCP. Pour une qualité acceptable, cette limite doit être inférieure à 100 ms.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Durée d’aller-retour maximale pour le flux audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |décimal(3,2)  <br/> | <br/> |Note MOS qualité réseau moyenne en large bande pour l’appel. Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé. La plage est [1.0 à 5.0].  <br/> |
|**OverallMinNetworkMOS** <br/> |décimal(3,2)  <br/> | <br/> |Mos réseau à bande large minimale pour l’appel.  <br/> |
|**SendListenMOS** <br/> |décimal(3,2)  <br/> | <br/> |Note MOS moyenne d’écoute large bande prévue pour l’audio envoyé, y compris le niveau de voix, le niveau de bruit et les caractéristiques de l’appareil de capture.  <br/> |
|**SendListenMOSMin** <br/> |décimal(3,2)  <br/> | <br/> |Valeur SendListenMOS minimale pour l’appel.  <br/> |
|**RecvListenMOS** <br/> |décimal(3,2)  <br/> | <br/> |Note MOS d’écoute large bande prévue moyenne pour l’audio reçu du réseau, y compris le niveau de voix, le niveau de bruit, le codec, les conditions réseau et les caractéristiques de l’appareil de capture.  <br/> |
|**RecvListenMOSMin** <br/> |décimal(3,2)  <br/> | <br/> |RecvListenMOS minimum pour l’appel.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Indicateur indiquant si le FEC audio a été utilisé pour l’appel.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |décimal(5,2)  <br/> ||Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |décimal(5,2)  <br/> ||Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |décimal(5,2)  <br/> ||Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.  <br/> |
|**Entrant** <br/> |bit  <br/> | <br/> |Les données de flux côté récepteur sont reçues.  <br/> |
|**Sortant** <br/> |bit  <br/> | <br/> |Les données de flux côté expéditeur sont reçues.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 signifie que le sens du flux va de l’appelant à l’appelé.  <br/> 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
|**JitterInterArrivalsD** <br/> |float  <br/> ||Écart-type pour les temps d’arrivée de gigue.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Ratio maximal de paquets masqués par le correcteur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Écart-type pour le rapport des paquets masqués par le système de soins.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Ratio des paquets supprimés par le resserrement par rapport au nombre total de paquets reçus.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Ratio des paquets de correction d’erreur avant utilisés par rapport au nombre total de paquets reçus.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Nombre maximal de paquets audio compressés par le système de soins.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage du temps où l’appel était dans un état de congestion de perte.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’appel pendant lequel la congestion a été causée par l’arrivée retardée de paquets réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indique le pourcentage du temps où l’appel était en concurrence pour les ressources réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantité minimale d’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantité maximale d’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Écart-type de l’estimation de la bande passante mesuré pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantité moyenne d’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densité totale des rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale des rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences d’intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité totale des intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée totale des intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel décodé comme stéréo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel rendu comme stéréo par l’annulation de l’écho sonore.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Taux de perte de paquets après l’application de la correction des erreurs de forward.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel codé en stéréo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel capturé comme stéréo par l’annuleur d’écho sonore.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
