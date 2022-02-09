---
title: Table AppSharingStream
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
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: La table AppSharingStream contient la mesure Qualité de l’expérience (QoE) pour les flux de données réseau utilisés pour le partage d’application. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 69313a2885f954245460963f119619fb2b91c8d6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398528"
---
# <a name="appsharingstream-table"></a>Table AppSharingStream
 
La table AppSharingStream contient la mesure Qualité de l’expérience (QoE) pour les flux de données réseau utilisés pour le partage d’application. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primaire, étrangère  <br/> |Date et heure de début de la session.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Identificateur séquentiel utilisé pour distinguer les sessions qui ont débuté à la même date et à la même heure.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire, étrangère  <br/> | Voir [MediaLine Table](./medialine-0.md). <br/> |
|**StreamID** <br/> |int  <br/> |Primaire  <br/> |Identificateur unique du flux de partage d’application.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Gigue maximale du délai d’arrivée entre les paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Temps maximal (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Taux maximal de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Nombre de paquets envoyés.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Estimation de la quantité de bande passante unidirectionnelle disponible à la fin de la session. Indiquée en bits par seconde.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Description de la charge utile du partage d’application.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densité totale des rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale des rafales unidirectionnelles. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences d’intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité totale des intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée totale des intervalles unidirectionnels. Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier ; les intervalles indiquent des retards entre ces rafales. Cette valeur mesure le flux de données entre le client et le serveur.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||Rôle d’application (personne effectuant le partage ou spectateur) et type de contenu.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Temps total de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Temps moyen de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Temps maximal de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densité des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Durée des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Une transmission « par rafales » est une transmission dans laquelle les données sont diffusées en rafales imprévisibles par opposition à un flux régulier.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Une faible densité d’intervalles équivaut à une meilleure expérience de visionnage.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Durée des intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). De brèves durées d’intervalle équivalent à une meilleure expérience de visionnage.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Taux total de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Taux moyen de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Taux maximal de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans le taux de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Pourcentage total du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Pourcentage moyen du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Pourcentage maximal du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Densité des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Durée des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densité d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Durée des intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Nombre total d’images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Nombre moyen d’images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Nombre maximal d’images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densité de rafales dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans les images récupérées à partir de la source graphique.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Fréquence totale des images entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Fréquence moyenne des images entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Fréquence maximale des mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Fréquence totale des images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Fréquence moyenne des images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Fréquence maximale des images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Fréquence totale de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Fréquence moyenne de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Fréquence maximale de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Fréquence totale d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||Fréquence moyenne d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Fréquence maximale d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Hauteur moyenne de résolution vidéo, en pixels.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Largeur moyenne de résolution vidéo, en pixels.  <br/> |
|**Entrant** <br/> |bit  <br/> ||Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.  <br/> |
|**Sortant** <br/> |bit  <br/> ||Fréquence d’images moyenne (en images par seconde) pour les transmissions sortantes.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 signifie que la direction du flux va de l’appelant à l’appelé.  <br/> 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
