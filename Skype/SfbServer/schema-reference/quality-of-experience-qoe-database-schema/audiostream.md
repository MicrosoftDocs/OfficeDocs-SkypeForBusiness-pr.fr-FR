---
title: Table AudioStream
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Chaque enregistrement représente un seul flux audio. Généralement, une seule ligne de média audio contient deux flux audio.
ms.openlocfilehash: 7c1e7ae70a04aabc7db704aaaad873bc5b2100c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894134"
---
# <a name="audiostream-table"></a>Table AudioStream
 
Chaque enregistrement représente un seul flux audio. Généralement, une seule ligne de média audio contient deux flux audio.
  
|Colonne|Type de données|Clé/Index|Détails|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |ID unique au sein d’une ligne de média.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Gigue réseau moyenne à partir des statistiques de contrôle protocole RTCP (Real Time).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Gigue réseau maximum pendant l’appel.  <br/> |
|**PacketLossRate** <br/> |Decimal(5,4)  <br/> | <br/> |Taux de perte de paquets moyenne pendant l’appel.  <br/> |
|**PacketLossRateMax** <br/> |Decimal(5,4)  <br/> | <br/> |Perte maximale de paquets observée pendant l’appel.  <br/> |
|**BurstDensity** <br/> |Decimal(9,4)  <br/> | <br/> |Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.  <br/> |
|**BurstGapDensity** <br/> |Decimal(9,4)  <br/> | <br/> |Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durée moyenne des intervalles entre rafales de pertes de paquets.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Nombre de paquets pour le flux audio.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|**DegradationAvg** <br/> |Decimal (3,2)  <br/> | <br/> |Dégradation de la note MOS qualité réseau pour l’appel entière. Plage est 0.0 et 5.0. Cette mesure indique la quantité de que la note MOS qualité réseau a été réduite en raison de la perte de gigue et de paquets. Pour une qualité acceptable elle doit être inférieure à 0,5.  <br/> |
|**DegradationMax** <br/> |Decimal (3,2)  <br/> | <br/> |Dégradation de la note MOS qualité réseau maximale pendant l’appel.  <br/> |
|**DegradationJitterAvg** <br/> |Decimal (3,2)  <br/> | <br/> |Dégradation de la note MOS qualité réseau causée par la gigue.  <br/> |
|**DegradationPacketLossAvg** <br/> |Decimal (3,2)  <br/> | <br/> |Dégradation de la note MOS qualité réseau causée par la perte de paquets.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Étrangère  <br/> |Le Codec audio utilisé pour l’appel, référencé depuis la PayloadDescription Table.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Taux d’échantillonnage pour le flux audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Durée d’aller-retour d’après les statistiques RTCP. Pour une qualité acceptable doit être inférieure à 100 millisecondes.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Durée d’aller-retour maximale pour le flux audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |Decimal (3,2)  <br/> | <br/> |Moyenne de bande passante réseau MOS pour l’appel. Cette mesure varie selon le codec utilisé, une instabilité et la perte de paquets. Plage est [1.0 et 5.0].  <br/> |
|**OverallMinNetworkMOS** <br/> |Decimal (3,2)  <br/> | <br/> |La minimale en bande passante réseau MOS pour l’appel.  <br/> |
|**Valeur SendListenMOS** <br/> |Decimal (3,2)  <br/> | <br/> |La note MOS qualité d’écoute bande passante prédite moyenne pour l’audio envoyé, y compris le niveau de voix, niveau sonore et les caractéristiques du périphérique de capture.  <br/> |
|**SendListenMOSMin** <br/> |Decimal (3,2)  <br/> | <br/> |SendListenMOS minimum pour l’appel.  <br/> |
|**Valeur RecvListenMOS** <br/> |Decimal (3,2)  <br/> | <br/> |Le score de note MOS qualité d’écoute de bande passante prédite moyenne pour l’audio reçu du réseau, y compris le niveau de voix, niveau sonore, codec, les conditions réseau et caractéristiques du périphérique de capture.  <br/> |
|**RecvListenMOSMin** <br/> |Decimal (3,2)  <br/> | <br/> |RecvListenMOS minimum pour l’appel.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Indicateur signalant si la FEC audio a été utilisée pour l’appel.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |Decimal(5,2)  <br/> ||Taux moyen d’échantillons masqués générés par soin audio aux échantillons communs.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |Decimal(5,2)  <br/> ||Taux moyen d’échantillons étendus générés par soin audio aux échantillons communs.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |Decimal(5,2)  <br/> ||Taux moyen d’échantillons compressés générés par soin audio aux échantillons communs.  <br/> |
|**Trafic entrant** <br/> |bit  <br/> | <br/> |Données de flux du côté récepteur reçues.  <br/> |
|**Sortant** <br/> |bit  <br/> | <br/> |Données de flux côté expéditeur reçues.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 signifie que la direction du flux va de l’appelant à l’appelé.  <br/> 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Écart-type pour les heures d’arrivée de gigue.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Taux maximal de paquets masqués par la réparation.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Écart type du taux de paquets masqués par la réparation.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Taux de paquets supprimés par la réparation par rapport au nombre total de paquets reçus.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Taux de paquets de correction d’erreur de transfert par rapport au nombre total de paquets reçus.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Nombre maximal de paquets audio compressés par la réparation.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’heure de l’appel dans un état de congestion de perte.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’appel au cours de laquelle la congestion a été provoquée par l’arrivée en retard des paquets réseau.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indique le pourcentage du temps lorsque l’appel a été concurrentes des ressources réseau.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantité minimale de l’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantité maximale de l’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Écart-type de l’estimation de bande passante mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantité moyenne de l’estimation de la bande passante mesurée pendant l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de la latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantité moyenne de latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densité des rafales à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale rafale à sens unique. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité d’intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée des intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel décodé en stéréo.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel rendu en stéréo par le SUPPRESSEUR d’écho acoustique.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Taux de perte de paquets après que la correction d’erreur de transfert a été appliquée.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel encodé en stéréo.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel capturé en stéréo par le SUPPRESSEUR d’écho acoustique.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
