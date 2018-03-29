---
title: Table de AppSharingStream
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: La table AppSharingStream contient des mesures de qualité pour les flux de réseau utilisés pour le partage d’application. Cette table a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: a10370814da5630a6d453b2ff4cad44b16b74ff1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="appsharingstream-table"></a>Table de AppSharingStream
 
La table AppSharingStream contient des mesures de qualité pour les flux de réseau utilisés pour le partage d’application. Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primaires et étrangères  <br/> |Date et heure de début de la session.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Identificateur séquentiel permet de distinguer entre les sessions qui a permis à la même date et en même temps.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaires et étrangères  <br/> |Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :  <br/> 0 - audio  <br/> 1 - vidéo  <br/> 2 - vidéo panoramique  <br/> 3 - partage d’application/de bureau  <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de l’application de partage de flux de données.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Bougé maximal détecté entre l’arrivée des paquets RTP. (Variation est une mesure de la « tremblement » d’un appel). Valeurs d’instabilité élevé sont généralement provoquées par un serveur surchargé de média ou de la congestion et entraînent audio déformée ou perdue.  <br/> |
|**Aller-retour** <br/> |int  <br/> ||Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Quantité maximale de (en millisecondes) nécessaire à un paquet de protocole de Transport en temps réel pour un voyage à un autre point de terminaison, puis de nouveau. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Taux maximal de perte de paquets RTP (Real-Time Transport Protocol). (Perte de paquets se produit lorsque les paquets RTP, un protocole utilisé pour la transmission audio et vidéo sur Internet, n’a pas pu atteindre leur destination.) Taux de perte élevée sont généralement causées par un encombrement ; manque de bande passante ; encombrement sans fil ou interférence ; ou un serveur média surchargé. Perte de paquets entraîne généralement audio déformée ou perdue.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Nombre de paquets envoyés.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Estimée à sens unique la bande passante disponible à la fin de la session. Signalé en bits par seconde.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Description de l’application de partage de charge utile.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Montant total de la latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Montant moyen de latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Montant maximal de latence à sens unique. Latence d’unilatérale relative mesure le temps entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occurrences de total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densité de total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée du total rafale à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occurrences de total écart à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité de total écart à sens unique. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée de l’intervalle d’unilatérale total. Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non un flux régulier ; des écarts indiquent les délais entre ces pics d’activité. Cette mesure mesure des flux de données entre le client et le serveur.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||Type de rôle d’application (Observateur ou partagé) et le contenu.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Durée totale de traitement pour les mosaïques avec protocole remote desktop protocol (RDP). Un total plus élevé correspond à un délai plus long dans l’expérience d’affichage.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Durée moyenne de traitement pour les mosaïques avec protocole remote desktop protocol (RDP). Un total plus élevé correspond à un délai plus long dans l’expérience d’affichage.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Temps de traitement maximal pour les mosaïques avec protocole remote desktop protocol (RDP). Un total plus élevé correspond à un délai plus long dans l’expérience d’affichage.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||En mode rafale des occurrences dans le temps de traitement pour les mosaïques avec protocole remote desktop protocol (RDP). Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Rafale de densité dans le temps de traitement pour les mosaïques avec protocole remote desktop protocol (RDP). Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Rafale de durée dans le temps de traitement pour les mosaïques avec protocole remote desktop protocol (RDP). Une transmission de « rafales » est une transmission où les données sont véhiculées en rafales imprévisibles et non d’un flux continu.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Occurrences d’écart dans le temps de traitement pour les mosaïques avec protocole remote desktop protocol (RDP).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densité des écarts dans le temps de traitement pour les mosaïques avec protocole remote desktop protocol (RDP). Densité de faible espace équivaut à un meilleur confort de visualisation.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Des écarts de durée dans le temps de traitement pour les mosaïques avec protocole remote desktop protocol (RDP). Durée de l’intervalle court correspondent à un meilleur confort de visualisation.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Taux total de carreaux capturé (en mosaïques par seconde).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Taux moyen de mosaïques capturés (en mosaïques par seconde).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Taux maximal de mosaïques capturés (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |dans t  <br/> ||En mode rafale des occurrences dans le taux de mosaïques capturés (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Rafale de densité du taux de mosaïques capturés (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Rafale de durée dans le taux de mosaïques capturés (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’écart dans le taux de mosaïques capturés (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densité d’écart dans le taux de mosaïques capturés (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Durée écart du taux de mosaïques capturés (en mosaïques par seconde).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Pourcentage total du contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimé et remplacé par contenu actualisé.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Pourcentage moyen du contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimé et remplacé par contenu actualisé.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Pourcentage maximal du contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimé et remplacé par contenu actualisé.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||En mode rafale d’occurrences du contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimées et remplacées par contenu actualisé.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||En mode rafale de la densité du contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimées et remplacées par contenu actualisé.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Rafale de durée pour le contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimée et remplacée par contenu actualisé.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Occurrences d’espace pour le contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimées et remplacées par contenu actualisé.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densité de l’espace pour le contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimée et remplacée par contenu actualisé.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Durée de l’intervalle pour le contenu qui n’a pas atteint la visionneuse mais a été plutôt supprimée et remplacée par contenu actualisé.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Nombre total de trames raclés à partir de la source du graphique.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Nombre moyen de trames raclés à partir de la source du graphique.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Nombre maximal d’images raclés à partir de la source du graphique.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||En mode rafale des occurrences dans les images raclés à partir de la source du graphique.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Rafale de densité dans les cadres raclés à partir de la source du graphique.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Rafale de durée dans les cadres raclés à partir de la source du graphique.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences de discontinuité dans les cadres raclés à partir de la source du graphique.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densité de discontinuité dans les cadres raclés à partir de la source du graphique.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Durée écart dans les cadres raclés à partir de la source du graphique.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Total taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Moyenne des taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Entrant maximal mosaïque taux comme reçu par la visionneuse.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Rafale occurrences dans le taux de mosaïque comme reçu par la visionneuse.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Rafale densité dans le taux de mosaïque comme reçu par la visionneuse.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Rafale de durée dans le taux de mosaïque comme reçu par l’Observateur.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences d’écart dans le taux de mosaïque comme reçu par la visionneuse.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densité d’écart dans le taux de mosaïque comme reçu par la visionneuse.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Des écarts de durée dans le taux de mosaïque comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Total taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Moyenne des taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Maximum taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Rafale occurrences dans le taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Rafale de densité dans le taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Rafale de durée dans le taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||L’intervalle des occurrences dans le taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densité d’écart dans le taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Des écarts de durée dans le taux d’images entrantes comme reçu par la visionneuse.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Total taux de mosaïque sortantes de l’expéditeur.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Moyenne mosaïque vitesse de sortie de l’expéditeur.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Débit maximal du sortant mosaïque de l’expéditeur.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||En mode rafale des occurrences de la vitesse de sortie de mosaïque pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Rafale de densité dans la vitesse de sortie de mosaïque pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Rafale de durée dans la vitesse de sortie de mosaïque pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Écart des occurrences dans la vitesse de sortie de mosaïque pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densité d’écart de la vitesse de sortie de mosaïque pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Durée d’écart de la vitesse de sortie de mosaïque pour l’expéditeur.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Total sortant cadence pour l’expéditeur.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||moyenne fréquence d’images sortantes de l’expéditeur.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Sortant débit de trames maximal pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Rafale occurrences dans la fréquence d’images sortantes de l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Rafale de densité dans la fréquence d’images sortant de l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Rafale de durée dans la fréquence d’images sortantes de l’expéditeur.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Écart des occurrences dans la fréquence d’images sortantes de l’expéditeur.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densité d’écart de la fréquence d’images sortantes de l’expéditeur.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Durée écart de la fréquence d’images sortantes de l’expéditeur.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Moyenne de résolution vidéo hauteur, en pixels.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Moyenne de résolution vidéo largeur, en pixels.  <br/> |
|**Trafic entrant** <br/> |bit  <br/> ||Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.  <br/> |
|**Sortant** <br/> |bit  <br/> ||Fréquence d’images moyenne (en images par seconde) pour des transmissions sortantes.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 signifie que la direction du flux de données est de l’appelant à l’appelé.  <br/> 0 signifie que la direction du flux de données est de l’appelé vers l’appelant.  <br/> |
   

