---
title: 'Lync Server 2013 : table AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Table AppSharingStream dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-21_

La table AppSharingStream contient la mesure Qualité de l’expérience (QoE) pour les flux de données réseau utilisés pour le partage d’application. Cette table a été introduite dans Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonne</strong></th>
<th><strong>Type de données</strong></th>
<th><strong>Clé/index</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dateTime</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Date et heure de début de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Identificateur séquentiel utilisé pour distinguer les sessions qui ont débuté à la même date et à la même heure.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>0 – audio</p></li>
<li><p>1 – vidéo</p></li>
<li><p>2 – Vidéo panoramique</p></li>
<li><p>3 – partage d’application/Bureau</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Identificateur unique du flux de partage d’application.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gigue moyenne détectée entre les arrivées de paquets RTP. (L’instabilité est une mesure &quot;de&quot; la fluctuations d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gigue maximale du délai d’arrivée entre les paquets RTP. (L’instabilité est une mesure &quot;de&quot; la fluctuations d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Retour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</p>
<p>Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou une surcharge d’un serveur multimédia. Les durées d’aller-retour élevées ont un impact sur la qualité des conversations audio bidirectionnelles réalisées en temps réel.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Temps maximal (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</p>
<p>Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Taux maximal de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre de paquets envoyés.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bande passante</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Estimation de la quantité de bande passante unidirectionnelle disponible à la fin de la session. Indiquée en bits par seconde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Description de la charge utile du partage d’application.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar (256)</p></td>
<td></td>
<td><p>Rôle d’application (personne effectuant le partage ou spectateur) et type de contenu.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Temps total de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Temps moyen de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Temps maximal de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences de rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol).</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Une faible densité d’intervalles équivaut à une meilleure expérience de visionnage.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). De brèves durées d’intervalle équivalent à une meilleure expérience de visionnage.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Taux total de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Taux moyen de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Taux maximal de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences de rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Pourcentage total du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Pourcentage moyen du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Pourcentage maximal du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences de rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Nombre total d’images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Nombre moyen d’images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Nombre maximal d’images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences de rafales dans les images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité de rafales dans les images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des rafales dans les images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences d’intervalles dans les images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité d’intervalles dans les images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des intervalles dans les images récupérées à partir de la source graphique.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence totale des images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence moyenne des images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence maximale des mosaïques entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences de rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence totale des images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence moyenne des images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence maximale des images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences de rafales dans la fréquence d’images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité des rafales dans la fréquence d’images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des rafales dans la fréquence d’images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence totale de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence moyenne de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence maximale de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences de rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence totale d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence moyenne d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence maximale d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences de rafales dans la fréquence d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité des rafales dans la fréquence d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des rafales dans la fréquence d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occurrences d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Densité d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée des intervalles dans la fréquence d’images sortantes pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Hauteur moyenne de résolution vidéo, en pixels.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largeur moyenne de résolution vidéo, en pixels.</p></td>
</tr>
<tr class="even">
<td><p><strong>Entrant</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sortant</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Fréquence d’images moyenne (en images par seconde) pour les transmissions sortantes.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>1 signifie que la direction du flux va de l’appelant à l’appelé.</p>
<p>0 signifie que la direction du flux va de l’appelé à l’appelant.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

