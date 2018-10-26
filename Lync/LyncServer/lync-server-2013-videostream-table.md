---
title: 'Lync Server 2013 : Table VideoStream'
TOCTitle: 'Table VideoStream '
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425928(v=OCS.15)
ms:contentKeyID: 49297035
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table VideoStream dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente un flux vidéo. En règle générale, une ligne de média vidéo contient deux flux vidéo.


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
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>ID unique dans une ligne de média.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>Étrangère, primaire</p></td>
<td><p>Description de la charge utile. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-payloaddescription-table.md">Table PayloadDescription dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau maximum au cours de la session vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Durée d’aller-retour d’après les statistiques RTCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Durée d’aller-retour maximale pour le flux vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>Taux moyen de perte de paquets pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>Taux maximum de perte de paquets observé pendant l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Compte de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Estimations de la bande passante pour le flux vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char(9)</p></td>
<td><p> </p></td>
<td><p>Résolution de la vidéo en pixels (largeur x hauteur). Rapporté en tant que chaîne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Vitesse de transmission moyenne du flux vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>Fréquence d’images vidéo reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>Fréquence d’images vidéo envoyées.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Fréquence d’images vidéo maximum au cours de la session vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>Pourcentage d’images vidéo perdues.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Non disponible</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p></p></td>
<td><p>Pourcentage d’images vidéo perdues.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel qui se trouvait à la résolution CIF (Common Interchange Format).</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel qui était à la résolution VGA.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel qui était à la résolution HD720.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Pourcentage de la durée de l’appel sans suppression d’images.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Pourcentage de la durée de l’appel avec suppression d’images B.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Pourcentage de la durée de l’appel avec suppression d’images BP.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Pourcentage de la durée de l’appel avec suppression d’images BPSP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Pourcentage de la durée de l’appel avec suppression d’images BPSPI.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Données de flux du côté récepteur reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Outbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Données de flux du côté expéditeur reçues.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 signifie que la direction du flux va de l’appelant à l’appelé.</p>
<p>0 signifie que la direction du flux va de l’appelé à l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Indique en pourcentage la durée de l’état de congestion de perte de l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Indique en pourcentage la durée de l’appel pendant laquelle la congestion a été provoquée par l’arrivée en retard des paquets réseau.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Indique en pourcentage la durée pendant laquelle l’appel a tenté de récupérer des ressources réseau.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Estimation de quantité minimale de bande passante mesurée pendant l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Estimation de quantité maximale de bande passante mesurée pendant l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Écart type de l’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Estimation de quantité moyenne de bande passante mesurée pendant l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau ne pouvait pas prendre en charge la vidéo à plusieurs affichages.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p></p></td>
<td><p>Fréquence à laquelle les paquets vidéo ont été perdus.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Quantité moyenne de bande passante allouée pour la vidéo.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Étrangère</p></td>
<td><p>Type des codecs vidéo utilisés par l’émetteur. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-codecdescription-table.md">Table CodecDescription dans Lync Server 2013</a>.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Largeur de résolution utilisée par l’émetteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Hauteur de résolution utilisée par l’émetteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Fréquence d’images vidéo moyenne.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Vitesse de transmission maximale pour l’émetteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Vitesse de transmission moyenne pour l’émetteur.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nombre maximal de flux vidéo utilisés par l’émetteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Étrangère</p></td>
<td><p>Codecs vidéo utilisés par le récepteur. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-codecdescription-table.md">Table CodecDescription dans Lync Server 2013</a>.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Largeur de résolution utilisée par le récepteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Hauteur de résolution utilisée par le récepteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Fréquence d’images vidéo moyenne utilisée par le récepteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Vitesse de transmission maximale pour le récepteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Vitesse de transmission moyenne pour le récepteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Flux vidéo maximaux pour le récepteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Vitesse de transmission maximale pour le récepteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Mode vidéo (par exemple, galerie ou flux unique) pour le récepteur.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Taux de pertes de paquets à la suite de l’application de la correction d’erreur de transfert.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durée en pourcentage pendant laquelle l’indicateur de capacité dynamique a été actif.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char(9)</p></td>
<td><p></p></td>
<td><p>Résolution minimale mesurée durant l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel inférieur au seuil minimal de vitesse de transmission (70 Kbits/s).</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel inférieur au seuil minimal de fréquence d’images (7,5 images par seconde, en entrée).</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel dont la résolution était la plus faible.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durée de l’appel en secondes.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si les données ont été agrégées à partir de plusieurs appels.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

