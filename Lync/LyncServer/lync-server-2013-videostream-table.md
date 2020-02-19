---
title: 'Lync Server 2013 : table table Videostream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59799e9b6feb076575d8187936a42a408d0dba2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Table table Videostream dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-13_

Chaque enregistrement représente un flux vidéo. Une ligne de support vidéo contient généralement deux flux vidéo.


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
<td><p>R référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
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
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>type</p></td>
<td><p>Étranger, primaire</p></td>
<td><p>Description de la charge utile. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau maximale pendant la session vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Retour</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée d’aller-retour d’après les statistiques RTCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Temps d’aller-retour maximal pour le flux vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>décimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Taux moyen de perte de paquets pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>décimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Perte maximale de paquets observée pendant l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bande passante</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Estimations de bande passante pour le flux vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>Char (9)</p></td>
<td><p> </p></td>
<td><p>Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels. Signalée sous forme de chaîne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Vitesse de transmission moyenne du flux vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>décimale (9, 4)</p></td>
<td><p> </p></td>
<td><p>Fréquence d’images vidéo reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>décimale (9, 4)</p></td>
<td><p> </p></td>
<td><p>Fréquence d’images vidéo envoyées.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Vitesse de transmission vidéo maximale lors de la session vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>décimale (9, 4)</p></td>
<td><p> </p></td>
<td><p>Pourcentage du nombre total de trames vidéo perdues.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Non disponible.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>décimale (9, 4)</p></td>
<td></td>
<td><p>Pourcentage du nombre total de trames vidéo perdues.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Pourcentage de l’appel qui était à la résolution CIF (Common Interchange Format).</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Pourcentage de l’appel qui était à la résolution VGA.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Pourcentage de l’appel qui était à la résolution HD720.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel sans dépose d’image.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel avec une suppression d’image B.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel avec l’image BP.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel avec l’image BPSP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel avec l’image BPSPI.</p></td>
</tr>
<tr class="even">
<td><p><strong>Entrant</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Les données de flux du côté récepteur sont reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sortant</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Les données de flux du côté de l’expéditeur sont reçues.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>1 signifie que la direction du flux va de l’appelant à l’appelé.</p>
<p>0 signifie que la direction du flux va de l’appelé à l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Indique le pourcentage de temps pendant lequel l’appel se trouve dans un état de congestion de perte.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Indique le pourcentage de l’appel pendant lequel la congestion a été causée par le retard de l’arrivée des paquets réseau.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Indique le pourcentage de temps pendant lequel l’appel a eu accès aux ressources réseau.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité minimale d’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité maximale d’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Écart-type de l’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité moyenne d’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau ne pouvait pas prendre en charge la vidéo multivue.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>flottant</p></td>
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
<td><p>int</p></td>
<td></td>
<td><p>Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>flottant</p></td>
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
<td><p>flottant</p></td>
<td></td>
<td><p>Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>décimale (9, 4)</p></td>
<td></td>
<td><p>Vitesse à laquelle les paquets vidéo ont été perdus.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité moyenne de bande passante allouée à la vidéo.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>type</p></td>
<td><p>Etranger</p></td>
<td><p>Type de codecs vidéo utilisés par l’expéditeur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largeur de résolution utilisée par l’expéditeur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Hauteur de résolution utilisée par l’expéditeur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence d’images vidéo moyenne utilisée par l’expéditeur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vitesse de transmission maximale pour l’expéditeur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vitesse de transmission moyenne pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre maximal de flux vidéo utilisés par l’expéditeur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>type</p></td>
<td><p>Etranger</p></td>
<td><p>Codes vidéo utilisés par le récepteur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largeur de résolution utilisée par le récepteur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Hauteur de résolution utilisée par le récepteur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Fréquence d’images vidéo moyenne utilisée par le récepteur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vitesse de transmission maximale pour le récepteur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vitesse de transmission moyenne pour le récepteur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre maximal de flux vidéo pour le récepteur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre minimal de flux vidéo pour le récepteur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Mode vidéo (par exemple, Galerie ou flux unique) pour le récepteur.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Taux de perte de paquets après la correction des erreurs de transfert a été appliquée.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Pourcentage de temps pendant lequel l’indicateur de capacité dynamique était actif.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>Char (9)</p></td>
<td></td>
<td><p>Résolution minimale mesurée pendant l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Pourcentage de l’appel sous le seuil de taux de bits bas (70 kilobits par seconde).</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Pourcentage de l’appel en dessous du seuil de fréquence d’images faible (7,5 images par seconde, entrantes).</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Pourcentage de l’appel qui s’est produit à la résolution la plus faible.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>flottant</p></td>
<td></td>
<td><p>Longueur de l’appel en secondes.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Indique si les données ont été regroupées à partir de plusieurs appels.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

