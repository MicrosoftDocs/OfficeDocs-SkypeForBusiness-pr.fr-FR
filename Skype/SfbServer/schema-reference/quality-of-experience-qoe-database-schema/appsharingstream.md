---
title: Table AppSharingStream
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: La table AppSharingStream contient des mesures de qualité de l’expérience pour les flux de réseau utilisés pour le partage d’application. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 8e01cc4d35269b34e3e6fba13fd331139e3f7ae7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212340"
---
# <a name="appsharingstream-table"></a>Table AppSharingStream
 
La table AppSharingStream contient des mesures de qualité de l’expérience pour les flux de réseau utilisés pour le partage d’application. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |dateTime  <br/> |Primaire, étrangère  <br/> |Date et heure de début de la session.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Identificateur séquentiel utilisé pour faire la distinction entre les sessions qui ont débuté à la même date et en même temps.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire, étrangère  <br/> | Voir [Table MediaLine](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de l’application de flux de partage.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Gigue maximale détectée entre l’arrivée de paquets RTP. (Gigue est une mesure de « tremblement » d’un appel). Valeurs de gigue haute sont généralement causés par congestion ou un serveur multimédia surchargée et entraîner audio déformé ou perdue.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Quantité maximale de (en millisecondes) requise pour un paquet de Real-Time Transport Protocol à se déplacent vers un autre point de terminaison. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Taux maximal de perte de paquets RTP (Real-Time Transport Protocol). (La perte de paquets se produit lorsque les paquets RTP, un protocole utilisé pour la transmission audio et vidéo via Internet, n’a pas pu atteindre leur destination.) Taux de perte haute sont généralement provoquées par la congestion ; manque de bande passante ; congestion sans fil ou interférences ; ou un serveur multimédia surchargée. Perte de paquets entraîne audio déformé ou perdue.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Nombre de paquets envoyés.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Estimée à sens unique la bande passante disponible à la fin de la session. Indiqué en bits par seconde.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Description de la charge utile de partage d’application.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de la latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantité moyenne de latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence à sens unique. Latence à sens unique relative mesure le délai entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densité des rafales à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale rafale à sens unique. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité d’intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée des intervalles à sens unique total. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu ; intervalles indiquent les retards entre ces rafales. Cette mesure exhaustive de flux de données entre le client et le serveur.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||Rôle d’application (personne effectuant le partage ou spectateur) et type de contenu.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Nombre total de temps de traitement des mosaïques protocole remote desktop protocol (RDP). Un total supérieur équivaut à un délai plus long dans l’expérience d’affichage.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Durée moyenne de traitement pour les mosaïques protocole remote desktop protocol (RDP). Un total supérieur équivaut à un délai plus long dans l’expérience d’affichage.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Temps de traitement maximal pour les mosaïques protocole remote desktop protocol (RDP). Un total supérieur équivaut à un délai plus long dans l’expérience d’affichage.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans le temps de traitement pour les mosaïques protocole remote desktop protocol (RDP). Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densité des rafales dans le temps de traitement pour les mosaïques protocole remote desktop protocol (RDP). Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Durée dans le temps de traitement pour les mosaïques protocole remote desktop protocol (RDP) des rafales. Une transmission « rafales » est une transmission où flux de données en rafales imprévisibles au lieu d’un flux continu.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans le temps de traitement pour les mosaïques protocole remote desktop protocol (RDP).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans le temps de traitement pour les mosaïques protocole remote desktop protocol (RDP). Densité d’intervalles faible équivaut à un meilleur confort de visualisation.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Durée des intervalles dans le temps de traitement pour les mosaïques protocole remote desktop protocol (RDP). Durées des intervalles courte correspondent à un meilleur confort de visualisation.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Taux total de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Taux moyen de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Taux maximal de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence de mosaïques capturées (en mosaïques par seconde).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Pourcentage total du contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Pourcentage moyen du contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Pourcentage maximal du contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Densité des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Durée des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densité d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Durée des intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été au lieu de cela ignoré et remplacé par du contenu.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Nombre total d’images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Nombre moyen d’images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Nombre maximal d’images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans les images récupérées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans les images récupérées à partir de la source graphique.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Nombre total de fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Moyenne de fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Fréquence de mosaïques maximale entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Nombre total de fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Moyenne de fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Maximum fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Total fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Moyenne fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Maximum fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Total fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||moyenne fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Maximum fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occurrences de rafales dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densité des rafales dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Durée des rafales dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densité d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Durée des intervalles dans la fréquence d’images sortantes pour l’expéditeur.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Hauteur moyenne de résolution vidéo, en pixels.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Largeur moyenne de résolution vidéo, en pixels.  <br/> |
|**Trafic entrant** <br/> |bit  <br/> ||Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.  <br/> |
|**Sortant** <br/> |bit  <br/> ||Fréquence d’images moyenne (en images par seconde) pour les transmissions sortantes.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 signifie que la direction du flux va de l’appelant vers l’appelé.  <br/> 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
   

