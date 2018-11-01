---
title: 'Lync Server 2013 : Table AudioStream'
TOCTitle: Table AudioStream
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425961(v=OCS.15)
ms:contentKeyID: 49297111
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table AudioStream dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente un flux audio. En règle générale, une ligne de média audio contient deux flux audio.


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
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau maximum pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>Taux moyen de perte de paquets pendant l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>Taux maximum de perte de paquets observé pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Durée moyenne des intervalles entre les rafales de pertes de paquets.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Entier</p></td>
<td><p> </p></td>
<td><p>Nombre de paquets pour le flux audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>Entier</p></td>
<td><p> </p></td>
<td><p>Estimations de la bande passante pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Dégradation de la note MOS qualité réseau maximale pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Dégradation de la note MOS qualité réseau causée par la gigue.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Dégradation de la note MOS qualité réseau causée par la perte de paquets.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Le codec audio utilisé pour l’appel, référencé depuis la table PayloadDescription.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Taux d’échantillonnage pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Durée d’aller-retour d’après les statistiques RTCP. Pour une qualité acceptable, cette valeur doit être inférieure à 100 ms.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Durée d’aller-retour maximale pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Note MOS de qualité réseau moyenne en bande passante pour l’appel. Cette mesure dépend de la perte de paquets, de la gigue et du code utilisé. La plage est comprise entre [1.0 et 5.0].</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Note MOS de qualité réseau minimale en bande passante pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Note MOS de qualité d’écoute de bande passante prédite moyenne pour l’audio envoyé, dont le niveau de voix, niveau sonore et les caractéristiques du périphérique de capture.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>SendListenMOS minimum pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Note MOS de qualité d’écoute de bande passante prédite moyenne pour l’audio reçu du réseau, dont le niveau de voix, niveau sonore, le codec, les conditions du réseau et les caractéristiques du périphérique de capture.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>RecvListenMOS minimum pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indicateur signalant si la FEC audio a été utilisée pour l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Données de flux du côté récepteur reçues.</p></td>
</tr>
<tr class="even">
<td><p><strong>Outbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Données de flux du côté expéditeur reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 signifie que la direction du flux va de l’appelant à l’appelé.</p>
<p>0 signifie que la direction du flux va de l’appelé à l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Écart type pour les délais d’arrivée (gigue).</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Taux maximal de paquets masqués par la réparation.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Écart type du taux de paquets masqués par la réparation.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Taux de paquets supprimés par la réparation en comparaison du nombre total de paquets reçus.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Taux de paquets utilisant la correction d’erreur de transfert en comparaison du nombre total de paquets reçus.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Nombre maximal de paquets audio compressés par la réparation.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Indique en pourcentage la durée de l’état de congestion de perte de l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Indique en pourcentage la durée de l’appel pendant laquelle la congestion a été provoquée par l’arrivée en retard des paquets réseau.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Indique en pourcentage la durée pendant laquelle l’appel a tenté de récupérer des ressources réseau.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Estimation de quantité minimale de bande passante mesurée pendant l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Estimation de quantité maximale de bande passante mesurée pendant l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Écart type de l’estimation de bande passante mesurée pendant l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Estimation de quantité moyenne de bande passante mesurée pendant l’appel.</p>
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
<td><p>float</p></td>
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
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel décodé en stéréo.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel rendu en stéréo par le suppresseur d’écho acoustique.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Taux de pertes de paquets à la suite de l’application de la correction d’erreur de transfert.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel encodé en stéréo.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Pourcentage de l’appel capturé en stéréo par le suppresseur d’écho acoustique.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

