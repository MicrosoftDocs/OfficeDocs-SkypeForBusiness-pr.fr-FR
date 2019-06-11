---
title: 'Lync Server 2013 : Table AudioStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Table AudioStream dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

Chaque enregistrement représente un flux audio. Une ligne de médias audio contient généralement deux flux audio.


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
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
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
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Scintillement du réseau maximum lors de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>décimale (5; 4)</p></td>
<td><p> </p></td>
<td><p>Taux moyen de perte de paquets lors de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>décimale (5; 4)</p></td>
<td><p> </p></td>
<td><p>Perte de paquets maximum observée pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>décimale (9; 4)</p></td>
<td><p> </p></td>
<td><p>Densité moyenne de perte de paquets en rafales de pertes pendant l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée moyenne de perte de paquets en rafales de pertes pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>décimale (9; 4)</p></td>
<td><p> </p></td>
<td><p>Densité moyenne de perte de paquets lors de l’intervalle entre les pics de perte de paquets.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée moyenne des espaces entre les pics de perte de paquets.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Ent</p></td>
<td><p> </p></td>
<td><p>Nombre de paquets pour le flux audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bande passante</strong></p></td>
<td><p>Ent</p></td>
<td><p> </p></td>
<td><p>Estimations de bande passante pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Baisse de la dégradation du réseau pour l’ensemble de l’appel. La plage est 0,0 à 5,0. Cette mesure indique la somme que le coût du réseau a diminué en raison de la gigue et de la perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0,5.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Dégradation du réseau maximal pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Baisse de la dégradation du réseau à l’origine de gigue.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Baisse de la dégradation du réseau à l’origine de la perte de paquets.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Le codec audio utilisé pour l’appel, référencé à partir de la table PayloadDescription.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Taux d’échantillonnage pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée de l’aller-retour des statistiques RTCP. Pour une qualité acceptable, il devrait être inférieur à 100 millisecondes.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durée de l’aller-retour maximal pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>MOS du réseau à bandes moyenne pour l’appel. Cette métrique dépend du niveau de perte de paquets, de gigue et de codec utilisés. La plage est [1,0 à 5,0].</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Le réseau de bandes minimum pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Le score d’écoute de la bande moyenne prédite pour le son envoyé, y compris le niveau de voix, le niveau de bruit et les caractéristiques de l’appareil de capture.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Le minimum SendListenMOS pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Le score d’écoute de la bande moyenne prédite pour le son reçu du réseau, notamment le niveau de voix, le niveau sonore, le codec, les conditions du réseau et les caractéristiques de l’appareil de capture.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Le minimum RecvListenMOS pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indicateur indiquant si l’audio FEC a été utilisé pour l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td></td>
<td><p>Taux moyen d’échantillons masqués générés par la correction audio sur des exemples classiques.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td></td>
<td><p>Taux moyen d’échantillons étirés générés par la correction audio sur des exemples classiques.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td></td>
<td><p>Taux moyen d’échantillons compressés générés par la correction audio sur des exemples classiques.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Entrant</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Des données de flux sur le côté du destinataire sont reçues.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sortant</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Les données du flux du côté de l’expéditeur sont reçues.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 signifie que le sens du flux provient de l’appelant vers l’appelant.</p>
<p>0: le sens du flux provient de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Écart type pour les heures d’arrivée de gigue.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taux maximal de paquets masqués par la correction.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Écart type pour le rapport de paquets masqués par la correction.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taux de paquets rejetés par le taux de correction par rapport au nombre total de paquets reçus.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taux de paquets de correction d’erreur de transfert utilisés par rapport au nombre total de paquets reçus.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Nombre maximal de paquets audio compressés par le cicatrisé.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage du temps pendant lequel l’appel a été dans un état de congestion de perte.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage de l’appel au cours duquel une congestion est causée par le retard de paquets réseau.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indique le pourcentage de temps pendant lequel l’appel a été compétitif pour les ressources réseau.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité minimale d’estimation de la bande passante mesurée lors de l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité maximale d’estimation de la bande passante mesurée lors de l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Écart type de l’estimation de la bande passante mesurée lors de l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantité moyenne d’estimation de bande passante mesurée lors de l’appel.</p>
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
<td><p>float</p></td>
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
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel décodé en stéréo.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel rendu en stéréo par l’suppresseur d’écho acoustique.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taux de perte de paquets après application de la correction d’erreur de transfert.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel encodé en stéréo.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Pourcentage de l’appel capturé comme stéréo par l’suppresseur d’écho acoustique.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

