---
title: Table AudioStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Chaque enregistrement représente un flux audio. Une ligne de médias audio contient généralement deux flux audio.
ms.openlocfilehash: eae96b08f3a365288f48b7a68c75d3fd9114107d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295047"
---
# <a name="audiostream-table"></a>Table AudioStream
 
Chaque enregistrement représente un flux audio. Une ligne de médias audio contient généralement deux flux audio.
  
|Colonne|Type de données|Clé/Index|Détails|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |IDENTIFIant unique dans une ligne de médias.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Scintillement du réseau maximum lors de l’appel.  <br/> |
|**PacketLossRate** <br/> |décimale (5; 4)  <br/> | <br/> |Taux moyen de perte de paquets lors de l’appel.  <br/> |
|**PacketLossRateMax** <br/> |décimale (5; 4)  <br/> | <br/> |Perte de paquets maximum observée pendant l’appel.  <br/> |
|**BurstDensity** <br/> |décimale (9; 4)  <br/> | <br/> |Densité moyenne de perte de paquets en rafales de pertes pendant l’appel.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durée moyenne de perte de paquets en rafales de pertes pendant l’appel.  <br/> |
|**BurstGapDensity** <br/> |décimale (9; 4)  <br/> | <br/> |Densité moyenne de perte de paquets lors de l’intervalle entre les pics de perte de paquets.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durée moyenne des espaces entre les pics de perte de paquets.  <br/> |
|**PacketUtilization** <br/> |Ent  <br/> | <br/> |Nombre de paquets pour le flux audio.  <br/> |
|**Bande passante** <br/> |Ent  <br/> | <br/> |Estimations de bande passante pour le flux audio.  <br/> |
|**DegradationAvg** <br/> |décimale (3, 2)  <br/> | <br/> |Baisse de la dégradation du réseau pour l’ensemble de l’appel. La plage est 0,0 à 5,0. Cette mesure indique la somme que le coût du réseau a diminué en raison de la gigue et de la perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0,5.  <br/> |
|**DegradationMax** <br/> |décimale (3, 2)  <br/> | <br/> |Dégradation du réseau maximal pendant l’appel.  <br/> |
|**DegradationJitterAvg** <br/> |décimale (3, 2)  <br/> | <br/> |Baisse de la dégradation du réseau à l’origine de gigue.  <br/> |
|**DegradationPacketLossAvg** <br/> |décimale (3, 2)  <br/> | <br/> |Baisse de la dégradation du réseau à l’origine de la perte de paquets.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Externes  <br/> |Le codec audio utilisé pour l’appel, référencé à partir de la table PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Taux d’échantillonnage pour le flux audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Durée de l’aller-retour des statistiques RTCP. Pour une qualité acceptable, il devrait être inférieur à 100 millisecondes.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Durée de l’aller-retour maximal pour le flux audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |décimale (3, 2)  <br/> | <br/> |MOS du réseau à bandes moyenne pour l’appel. Cette métrique dépend du niveau de perte de paquets, de gigue et de codec utilisés. La plage est [1,0 à 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |décimale (3, 2)  <br/> | <br/> |Le réseau de bandes minimum pour l’appel.  <br/> |
|**SendListenMOS** <br/> |décimale (3, 2)  <br/> | <br/> |Le score d’écoute de la bande moyenne prédite pour le son envoyé, y compris le niveau de voix, le niveau de bruit et les caractéristiques de l’appareil de capture.  <br/> |
|**SendListenMOSMin** <br/> |décimale (3, 2)  <br/> | <br/> |Le minimum SendListenMOS pour l’appel.  <br/> |
|**RecvListenMOS** <br/> |décimale (3, 2)  <br/> | <br/> |Le score d’écoute de la bande moyenne prédite pour le son reçu du réseau, notamment le niveau de voix, le niveau sonore, le codec, les conditions du réseau et les caractéristiques de l’appareil de capture.  <br/> |
|**RecvListenMOSMin** <br/> |décimale (3, 2)  <br/> | <br/> |Le minimum RecvListenMOS pour l’appel.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Indicateur indiquant si l’audio FEC a été utilisé pour l’appel.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |décimale (5; 2)  <br/> ||Taux moyen d’échantillons masqués générés par la correction audio sur des exemples classiques.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |décimale (5; 2)  <br/> ||Taux moyen d’échantillons étirés générés par la correction audio sur des exemples classiques.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |décimale (5; 2)  <br/> ||Taux moyen d’échantillons compressés générés par la correction audio sur des exemples classiques.  <br/> |
|**Entrant** <br/> |bit  <br/> | <br/> |Des données de flux sur le côté du destinataire sont reçues.  <br/> |
|**Sortant** <br/> |bit  <br/> | <br/> |Les données du flux du côté de l’expéditeur sont reçues.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 signifie que le sens du flux provient de l’appelant vers l’appelant.  <br/> 0: le sens du flux provient de l’appelant.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Écart type pour les heures d’arrivée de gigue.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Taux maximal de paquets masqués par la correction.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Écart type pour le rapport de paquets masqués par la correction.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Taux de paquets rejetés par le taux de correction par rapport au nombre total de paquets reçus.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Taux de paquets de correction d’erreur de transfert utilisés par rapport au nombre total de paquets reçus.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Nombre maximal de paquets audio compressés par le cicatrisé.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage du temps pendant lequel l’appel a été dans un état de congestion de perte.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indique le pourcentage de l’appel au cours duquel une congestion est causée par le retard de paquets réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indique le pourcentage de temps pendant lequel l’appel a été compétitif pour les ressources réseau.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantité minimale d’estimation de la bande passante mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantité maximale d’estimation de la bande passante mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Écart type de l’estimation de la bande passante mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantité moyenne d’estimation de bande passante mesurée lors de l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**Moyenne unidirectionnelle relative** <br/> |float  <br/> ||Quantité moyenne de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de rafales à sens unique. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densité du Burst total unidirectionnel. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale du Burst. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de l’espacement unidirectionnel. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité de l’intervalle total à sens unique. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée totale de l’intervalle. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel décodé en stéréo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel rendu en stéréo par l’suppresseur d’écho acoustique.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Taux de perte de paquets après application de la correction d’erreur de transfert.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel encodé en stéréo.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Pourcentage de l’appel capturé comme stéréo par l’suppresseur d’écho acoustique.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
