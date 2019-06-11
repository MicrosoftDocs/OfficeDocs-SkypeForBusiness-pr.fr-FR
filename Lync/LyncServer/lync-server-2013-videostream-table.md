---
title: 'Lync Server 2013 : Table VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Table VideoStream dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-12-13_

Chaque enregistrement représente un flux vidéo. Une ligne de média vidéo contient généralement deux flux vidéo.


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
<th><strong>Clé/Index</strong></th>
<th><strong>Détails</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Principal</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>R référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>IDENTIFIant unique dans une ligne de médias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>type</p></td>
<td><p>Étranger, primaire</p></td>
<td><p>Description de la charge utile. Pour plus d’informations, voir la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Scintillement du réseau maximum lors de la session vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée de l’aller-retour des statistiques RTCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée de l’aller-retour maximal pour le flux vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>décimale (5; 4)</p></td>
<td><p> </p></td>
<td><p>Taux moyen de perte de paquets lors de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>décimale (5; 4)</p></td>
<td><p> </p></td>
<td><p>Perte de paquets maximum observée pendant l’appel.</p></td>
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
<td><p>car (9)</p></td>
<td><p> </p></td>
<td><p>Résolution de la vidéo, en pixels, de largeur multipliée par la hauteur en pixels. Signalée en tant que chaîne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Vitesse de transmission moyenne du flux vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>décimale (9; 4)</p></td>
<td><p> </p></td>
<td><p>Fréquence d’images vidéo reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>décimale (9; 4)</p></td>
<td><p> </p></td>
<td><p>Fréquence d’images vidéo envoyées.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Débit vidéo maximum lors de la session vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>décimale (9; 4)</p></td>
<td><p> </p></td>
<td><p>Pourcentage du nombre total de trames vidéo perdues.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Non disponible.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>décimale (9; 4)</p></td>
<td></td>
<td><p>Pourcentage du nombre total de trames vidéo perdues.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Pourcentage de l’appel à la résolution CAF (Common Interchange Format).</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Pourcentage de l’appel à la résolution VGA.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Pourcentage de l’appel passé à la résolution HD720.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel sans cadre.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel avec la dépose de l’image B.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel avec la liste déroulante.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel avec BPSP Frame.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Pourcentage de la durée de l’appel avec BPSPI Frame.</p></td>
</tr>
<tr class="even">
<td><p><strong>Entrant</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Des données de flux sur le côté du destinataire sont reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sortant</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Les données du flux du côté de l’expéditeur sont reçues.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 signifie que le sens du flux provient de l’appelant vers l’appel.</p>
<p>0: le sens du flux provient de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage du temps pendant lequel l’appel a été dans un état de congestion de perte.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage de l’appel au cours duquel une congestion est causée par le retard de paquets réseau.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage de temps pendant lequel l’appel a été compétitif pour les ressources réseau.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité minimale d’estimation de la bande passante mesurée lors de l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité maximale d’estimation de la bande passante mesurée lors de l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Écart type de l’estimation de la bande passante mesurée lors de l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité moyenne d’estimation de bande passante mesurée lors de l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau n’a pas pu prendre en charge la vidéo multivue.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Quantité totale de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Moyenne unidirectionnelle relative</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Quantité moyenne de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Quantité maximale de latence à sens unique. Latence relative à sens unique, mesure du délai entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre total d’occurrences de rafales à sens unique. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Densité du Burst total unidirectionnel. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Durée totale du Burst. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu. Cette métrique mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre total d’occurrences de l’espacement unidirectionnel. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densité de l’intervalle total à sens unique. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Durée totale de l’intervalle. Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales. Cette métrique mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cause du taux</strong></p></td>
<td><p>décimale (9; 4)</p></td>
<td></td>
<td><p>Taux d’interruption des paquets vidéo.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité moyenne de bande passante allouée pour la vidéo.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>type</p></td>
<td><p>Externes</p></td>
<td><p>Type de codecs vidéo utilisés par l’expéditeur. Pour plus d’informations, voir la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largeur de résolution utilisée par l’expéditeur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Hauteur de résolution utilisée par l’expéditeur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Transmission moyenne de la fréquence d’images vidéo utilisée par l’expéditeur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Taux de bits maximal pour l’expéditeur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Taux de bits moyen pour l’expéditeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre maximal de flux vidéo utilisés par l’expéditeur.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>type</p></td>
<td><p>Externes</p></td>
<td><p>Codes vidéo utilisés par le destinataire. Pour plus d’informations, voir la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largeur de résolution utilisée par le destinataire.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Hauteur de résolution utilisée par le destinataire.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cause reçues</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Fréquence d’images vidéo moyenne utilisée par le destinataire.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vitesse de transmission maximale du destinataire.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Taux de bits moyen pour le destinataire.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Flux vidéo maximal pour le destinataire.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Flux vidéo minimal pour le destinataire.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Mode vidéo (par exemple, Galerie ou flux unique) pour le destinataire.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taux de perte de paquets après application de la correction d’erreur de transfert.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cause du pourcentage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de temps pendant lequel l’indicateur de capacité dynamique a été actif.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>car (9)</p></td>
<td></td>
<td><p>Résolution minimale mesurée lors de l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel inférieur au seuil de faible taux de bits (70 kilobits par seconde).</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cause du pourcentage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel inférieur au seuil de fréquence d’images faible (7,5 images par seconde, entrant).</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cause du pourcentage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel qui s’est produit à la résolution la plus basse.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Durée de l’appel en secondes.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indique si les données ont été agrégées à partir de plusieurs appels.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

