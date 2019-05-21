---
title: Table AppSharingStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: La table AppSharingStream contient des métriques de qualité d’utilisation pour les flux réseau utilisés pour le partage d’application. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 61606f204310b3956eb74bd19d0c9d8d421e7818
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295117"
---
# <a name="appsharingstream-table"></a>Table AppSharingStream
 
La table AppSharingStream contient des métriques de qualité d’utilisation pour les flux réseau utilisés pour le partage d’application. Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Valeur  <br/> |Etranger principal  <br/> |Date et heure de démarrage de la session.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Etranger principal  <br/> |Identificateur séquentiel permettant de faire la distinction entre les sessions qui ont commencé à la même date et en même temps.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Etranger principal  <br/> | Voir [table MediaLine](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**StreamID** <br/> |int  <br/> |Principal  <br/> |Identificateur unique du flux de partage d’application.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Scintillement maximal détecté entre les arrivées de Paquets RTP. (Gigue est une mesure du «shakiness» d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Quantité maximale de (en millisecondes) requise pour le paquet du protocole de transport en temps réel pour voyager vers un autre point de terminaison, puis retour. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Taux maximal de perte de Paquets RTP (Real-Time Transport Protocol). (La perte de paquets se produit lorsque les paquets RTP, un protocole utilisé pour transmettre des contenus audio et vidéo sur Internet, n’a pas pu atteindre leur destination.) Les taux de perte élevés sont généralement causés par une congestion; absence de bande passante; encombrement ou interférence sans fil; ou un serveur multimédia surchargé. La perte de paquets génère généralement une distorsion ou une perte de son.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Nombre de paquets envoyés.  <br/> |
|**Bande passante** <br/> |int  <br/> ||Durée de bande passante estimée disponible à la fin de la session. État en bits par seconde.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Description de la charge utile de partage d’application.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantité totale de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> |
|**Moyenne unidirectionnelle relative** <br/> |float  <br/> ||Quantité moyenne de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantité maximale de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de rafales à sens unique. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densité du Burst total unidirectionnel. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durée totale du Burst. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Nombre total d’occurrences de l’espacement unidirectionnel. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densité de l’intervalle total à sens unique. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durée totale de l’intervalle. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)  <br/> ||Rôle d’application (partage ou visionneuse) et type de contenu.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Durée totale du traitement des vignettes du protocole RDP (Remote Desktop Protocol). Un total supérieur équivaut à un délai plus long dans l’interface d’affichage.  <br/> |
|**Vignettes RDP** <br/> |float  <br/> ||Durée de traitement moyenne des vignettes du protocole RDP (Remote Desktop Protocol). Un total supérieur équivaut à un délai plus long dans l’interface d’affichage.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Temps de traitement maximal pour les vignettes de protocole RDP (Remote Desktop Protocol). Un total supérieur équivaut à un délai plus long dans l’interface d’affichage.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Des occurrences de Burst dans le temps de traitement des vignettes de protocole RDP (Remote Desktop Protocol). Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densité Burst du temps de traitement des vignettes du protocole RDP (Remote Desktop Protocol). Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Durée Burst du temps de traitement des vignettes de protocole RDP (Remote Desktop Protocol). Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Occurrences de l’espace dans le temps de traitement des vignettes de protocole RDP (Remote Desktop Protocol).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||La densité de l’intervalle du temps de traitement des vignettes RDP (Remote Desktop Protocol). La densité de faible interépaisseur correspond à une meilleure expérience d’affichage.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Durée de l’intervalle du temps de traitement des vignettes RDP (Remote Desktop Protocol). Les durées de faible intervalle sont assimilées à une meilleure expérience d’affichage.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Taux total de vignettes capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Taux moyen des vignettes capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Taux maximal de vignettes capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |dans t  <br/> ||Occurrences de Burst dans le taux de vignettes capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densité Burst dans le taux de vignettes capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Durée Burst dans le taux de vignettes capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences de l’espace dans le taux de vignettes capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densité de l’intervalle dans le taux de vignettes capturées (en mosaïques par seconde).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Durée de l’intervalle en fonction du taux de vignettes capturées (en mosaïques par seconde).  <br/> |
|**Vignettes altérées** <br/> |float  <br/> ||Pourcentage total du contenu n’ayant pas atteint la visionneuse, mais qui a été ignoré et écrasé par le contenu actualisé.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Pourcentage moyen du contenu n’ayant pas atteint la visionneuse, mais qui a été ignoré et écrasé par le contenu actualisé.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Pourcentage maximal du contenu n’ayant pas atteint la visionneuse, mais a été ignoré et écrasé par le contenu actualisé.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Des occurrences de Burst pour le contenu n’ayant pas atteint la visionneuse, mais qui ont été ignorées et écrasées par le contenu fraîche.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Densité Burst pour le contenu n’ayant pas atteint la visionneuse, mais qui a été ignoré et écrasé par le contenu actualisé.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Durée Burst pour le contenu n’ayant pas atteint la visionneuse, mais qui a été supprimée et écrasé par le contenu fraîche.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Occurrences d’espace pour le contenu n’ayant pas atteint la visionneuse, mais qui ont été ignorées et écrasées par le contenu fraîche.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densité de l’intervalle pour le contenu n’ayant pas atteint la visionneuse, mais qui a été supprimée et écrasé par le contenu actualisé.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Durée de l’intervalle pour le contenu n’ayant pas atteint la visionneuse, mais qui a été annulée et écrasée par le contenu actualisé.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Nombre total d’images abîmées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Nombre moyen de trames abîmées dans la source graphique.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Nombre maximal d’images abîmées dans la source graphique.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Des occurrences de Burst dans les trames abîmées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densité Burst dans les trames abîmées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Durée Burst dans les trames rachetées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences de l’espace dans les trames abîmées dans la source graphique.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densité de l’intervalle dans les trames rachetées à partir de la source graphique.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Durée de l’intervalle dans les trames abîmées par la source graphique.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Taux total d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Taux moyen d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Taux maximal de vignettes entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Des occurrences de Burst dans le taux de vignettes entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densité Burst dans le taux de vignette entrante tel qu’il est reçu par la visionneuse.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Durée Burst dans le taux de vignette entrante tel qu’il est reçu par la visionneuse.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences de l’espace dans le taux de vignette entrantes reçues par la visionneuse.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densité de l’intervalle dans le taux de vignette entrante tel qu’il est reçu par la visionneuse.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Durée de l’intervalle dans le taux de vignette entrante tel qu’il est reçu par la visionneuse.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Taux total d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Taux moyen d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Taux maximal d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Des occurrences de Burst dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densité Burst dans la fréquence d’images entrantes reçue par la visionneuse.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Durée Burst dans la fréquence d’images entrantes reçue par la visionneuse.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences de l’espace dans la fréquence d’images entrantes reçues par la visionneuse.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densité de l’intervalle dans la fréquence d’images entrantes reçue par la visionneuse.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Durée de l’intervalle dans la fréquence d’images entrantes reçue par la visionneuse.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Taux total de vignettes sortantes de l’expéditeur.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Taux moyen d’une vignette sortante pour l’expéditeur.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Taux de vignette sortante maximal pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Des occurrences de Burst dans le taux de vignette sortante pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densité Burst dans le taux de vignette sortante pour l’expéditeur.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Durée Burst dans le taux de vignette sortante pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Occurrences de l’espace dans le taux de vignette sortante de l’expéditeur.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densité de l’intervalle dans le taux de vignette sortante pour l’expéditeur.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Durée de l’intervalle dans le taux de vignette sortante pour l’expéditeur.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Taux total d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||taux moyen d’images sortantes pour l’expéditeur.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Taux maximal d’images sortant pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Des occurrences de Burst dans le taux d’images sortant pour l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densité Burst dans le taux d’image sortant de l’expéditeur.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Durée Burst dans le taux d’images sortant de l’expéditeur.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Occurrences de l’espace dans le taux d’image sortant de l’expéditeur.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densité de l’intervalle dans le taux d’image sortant de l’expéditeur.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Durée de l’intervalle dans le taux d’image sortant de l’expéditeur.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Hauteur moyenne de la résolution vidéo, en pixels.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Largeur de résolution vidéo moyenne, en pixels.  <br/> |
|**Entrant** <br/> |bit  <br/> ||Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.  <br/> |
|**Sortant** <br/> |bit  <br/> ||Fréquence d’images moyenne (en images par seconde) pour les transmissions sortantes.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 signifie que le sens du flux provient de l’appelant vers l’appel.  <br/> 0: le sens du flux provient de l’appelant.  <br/> |
   

