---
title: Table AudioStream
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Chaque enregistrement représente un flux de données audio. Une ligne d’un média audio contient généralement deux flux de données audio.
ms.openlocfilehash: 63cd2f63eed5d423750a50a23ae347a97725d65f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="audiostream-table"></a>Table AudioStream
 
Chaque enregistrement représente un flux de données audio. Une ligne d’un média audio contient généralement deux flux de données audio.
  
|Colonne ***|Type de données ***|Clé / Index ***|Détails ***|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |ID unique d’une ligne de media.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Instabilité du réseau moyenne à partir des statistiques de protocole de contrôle en temps réel (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Bougé maximal du réseau lors de l’appel.  <br/> |
|**PacketLossRate** <br/> |Decimal(5,4)  <br/> | <br/> |Taux de perte de paquet moyenne lors de l’appel.  <br/> |
|**PacketLossRateMax** <br/> |Decimal(5,4)  <br/> | <br/> |Perte de paquet maximale observée au cours de l’appel.  <br/> |
|**BurstDensity** <br/> |Decimal(9,4)  <br/> | <br/> |Densité moyenne de perte de paquet pendant les pics de pertes lors de l’appel.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durée moyenne de perte de paquets pendant les pics de pertes lors de l’appel.  <br/> |
|**BurstGapDensity** <br/> |Decimal(9,4)  <br/> | <br/> |Densité moyenne de perte de paquets au cours des intervalles entre les pics de perte de paquets.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durée moyenne des écarts entre les pics de perte de paquets.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Nombre de paquets pour le flux de données audio.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|**DegradationAvg** <br/> |Decimal (3,2)  <br/> | <br/> |Dégradation de MOS de réseau pour l’appel entière. La plage est de 0.0 à 5.0. Cette métrique indique le montant de que la MOS de réseau a été réduite en raison de la perte de gigue et de paquet. Pour une qualité acceptable elle doit être inférieure à 0,5.  <br/> |
|**DegradationMax** <br/> |Decimal (3,2)  <br/> | <br/> |Dégradation du réseau MOS maximale lors de l’appel.  <br/> |
|**DegradationJitterAvg** <br/> |Decimal (3,2)  <br/> | <br/> |Dégradation du réseau MOS due au gigue.  <br/> |
|**DegradationPacketLossAvg** <br/> |Decimal (3,2)  <br/> | <br/> |Réseau MOS engendrés par la perte de paquets.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Étrangère  <br/> |Le Codec audio utilisé pour l’appel, référencé à partir de la Table de PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Taux d’échantillonnage du flux audio.  <br/> |
|**Aller-retour** <br/> |int  <br/> | <br/> |Délai d’aller-retour à partir des statistiques RTCP. Pour une qualité acceptable, cela devrait être inférieure à 100 millisecondes.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Temps d’aller-retour maximale pour le flux de données audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |Decimal (3,2)  <br/> | <br/> |Moyenne à large bande MOS de réseau pour l’appel. Cette mesure dépend de la perte de paquets, l’instabilité et codec utilisé. La plage est [1.0 à 5.0].  <br/> |
|**OverallMinNetworkMOS** <br/> |Decimal (3,2)  <br/> | <br/> |Le minimum à large bande MOS de réseau pour l’appel.  <br/> |
|**SendListenMOS** <br/> |Decimal (3,2)  <br/> | <br/> |Le MOS écoute moyenne wideband prévue score audio envoyés, y compris le niveau de reconnaissance vocale, niveau de bruit et capturer des caractéristiques du périphérique.  <br/> |
|**SendListenMOSMin** <br/> |Decimal (3,2)  <br/> | <br/> |La SendListenMOS minimale pour l’appel.  <br/> |
|**RecvListenMOS** <br/> |Decimal (3,2)  <br/> | <br/> |Le score d’écoute le MOS moyenne de large bande prévue pour l’audio reçus à partir du réseau, y compris le niveau de reconnaissance vocale, niveau de bruit, codec, des conditions réseau et caractéristiques des périphériques de capture.  <br/> |
|**RecvListenMOSMin** <br/> |Decimal (3,2)  <br/> | <br/> |La RecvListenMOS minimale pour l’appel.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Indicateur signalant si FEC audio a été utilisé pour l’appel.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |Decimal(5,2)  <br/> ||Taux moyen d’échantillons permettant des dissimuler générées par le correcteur audio à des exemples typiques.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |Decimal(5,2)  <br/> ||Taux moyen d’échantillons étirés générées par le correcteur audio à des exemples typiques.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |Decimal(5,2)  <br/> ||Taux moyen d’échantillons compressés générées par le correcteur audio à des exemples typiques.  <br/> |
|**Trafic entrant** <br/> |bit  <br/> | <br/> |Réception des données de flux sur le récepteur.  <br/> |
|**Sortant** <br/> |bit  <br/> | <br/> |Réception des données de flux sur le côté de l’expéditeur.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 signifie que la direction du flux de données est celui de l’appelant à l’appelé.  <br/> 0 signifie que la direction du flux de données est de l’appelé vers l’appelant.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Écart-type pour les heures d’arrivée de bougé.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Rapport maximal de paquets masqué par le guérisseur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Écart-type pour le taux de paquets masqué par le guérisseur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Taux de paquets ignorés par le guérisseur par rapport au nombre total de paquets reçus.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Taux de paquets de correction aval des erreurs utilisée par rapport au nombre total de paquets reçus.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Nombre maximal de paquets audio qui ont été compressés par le guérisseur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’heure de l’appel dans un état de congestion de perte.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’appel au cours de laquelle congestion a été provoquée par l’arrivée de retardée des paquets réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indique le pourcentage du temps lorsque l’appel a été en compétition pour les ressources réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Montant minimal d’estimation de la bande passante est mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Durée estimation de la bande passante maximale mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Écart-type de l’estimation de la bande passante est mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durée estimation de la bande passante moyenne mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Montant total de la latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Montant moyen de latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Montant maximal de latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occurrences de total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densité de total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée du total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occurrences de total écart à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité de total écart à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée de l’intervalle d’unilatérale total. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel de décodage stéréo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel de rendu en tant que stéréo par l’annulateur d’écho acoustique.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Taux de perte de paquets après que correction aval des erreurs a été appliquée.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel codée en tant que stéréo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel capturée en tant que stéréo par l’annulateur d’écho acoustique.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

