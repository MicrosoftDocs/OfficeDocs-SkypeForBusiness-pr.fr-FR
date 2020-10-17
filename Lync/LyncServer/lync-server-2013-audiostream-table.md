---
title: 'Lync Server 2013 : table AudioStream'
description: 'Lync Server 2013 : table AudioStream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552340"
---
# <a name="audiostream-table-in-lync-server-2013"></a>Table AudioStream dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Chaque enregistrement représente un flux audio. Une ligne multimédia audio contient généralement deux flux audio.


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
<td><p>DateHeure</p></td>
<td><p>Primaire</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Primaire</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>ID unique dans une ligne de média.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau maximum pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>décimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Taux moyen de perte de paquets pendant l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>décimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Perte maximale de paquets observée pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>décimale (9, 4)</p></td>
<td><p> </p></td>
<td><p>Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>décimale (9, 4)</p></td>
<td><p> </p></td>
<td><p>Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée moyenne des intervalles entre les rafales de pertes de paquets.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Nombre de paquets pour le flux audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bande passante</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Estimations de la bande passante pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Dégradation de la note MOS qualité réseau maximale pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Dégradation de la note MOS qualité réseau causée par la gigue.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Dégradation de la note MOS qualité réseau causée par la perte de paquets.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Codec audio utilisé pour l’appel, référencé à partir de la table PayloadDescription.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Taux d’échantillonnage pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Retour</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée d’aller-retour d’après les statistiques RTCP. Pour une qualité acceptable, cette valeur doit être inférieure à 100 ms.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée d’aller-retour maximale pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Note MOS qualité réseau moyenne en large bande pour l’appel. Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé. La plage est [1,0 to 5,0].</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Le MOS de réseau à large bande minimum pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Nombre moyen de scores de retour à la ligne pour l’audio envoyé, y compris le niveau de voix, le niveau sonore et les caractéristiques du périphérique de capture.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>SendListenMOS minimale pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Nombre moyen de scores de retour à la ligne pour l’audio reçu du réseau, y compris le niveau de voix, le niveau sonore, le codec, les conditions réseau et les caractéristiques du périphérique de capture.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>RecvListenMOS minimale pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Indicateur signalant si la fonction FEC audio a été utilisée pour l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td></td>
<td><p>Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td></td>
<td><p>Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td></td>
<td><p>Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Entrants</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Les données de flux du côté récepteur sont reçues.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sortant</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Les données de flux du côté de l’expéditeur sont reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>1 signifie que la direction du flux est entre l’appelant et l’appelé.</p>
<p>0 signifie que la direction du flux va de l’appelé à l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Écart-type pour les heures d’arrivée de gigue.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Ratio maximal de paquets masqués par la réparation.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Écart-type pour le rapport des paquets masqués par le réparer.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Ratio de paquets supprimés par la réparation par rapport au nombre total de paquets reçus.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Rapport entre les paquets de correction d’erreur de transfert utilisés et le nombre total de paquets reçus.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Nombre maximal de paquets audio qui ont été compressés par le réparer.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage de temps pendant lequel l’appel se trouve dans un état de congestion de perte.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage de l’appel pendant lequel la congestion a été causée par le retard de l’arrivée des paquets réseau.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage de temps pendant lequel l’appel a eu accès aux ressources réseau.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité minimale d’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité maximale d’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Écart-type de l’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité moyenne d’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel décodé en stéréo.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel rendu stéréo par le suppresseur d’écho acoustique.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taux de perte de paquets après la correction des erreurs de transfert a été appliquée.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel codé en stéréo.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel capturé en tant que stéréo par le suppresseur d’écho acoustique.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

