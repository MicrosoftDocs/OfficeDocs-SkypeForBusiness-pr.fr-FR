---
title: 'Affichage Lync Server 2013: AudioStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10992007c76321f8ed3b436b9786cbef840173ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Affichage AudioStreamDetail dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Le mode AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>IDENTIFIant unique dans une ligne de médias.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de début de la session.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Catégorie de boîte de dialogue: 0 est le serveur Lync en jambes du serveur de médiation; 1 est le serveur de médiation pour le tronçon de passerelle PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Indicateur indiquant si l’appel a été ignoré ou non.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Le cas échéant, indique pourquoi un appel n’a pas été ignoré, même si les ID de contournement correspondent. Une seule valeur est définie:</p>
<p>0x0001-ID de contournement inconnu pour la carte réseau par défaut.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Priorité de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet du pool d’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du pool d’appel.</p></td>
</tr>
<tr class="even">
<td><p>Appelant</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>Appelé</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Chaîne de l’agent utilisateur de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>type</p></td>
<td><p>Type de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Chaîne de l’agent utilisateur de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>type</p></td>
<td><p>Type de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>Appelant</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Système d’exploitation (se) du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Système d’exploitation (se) du point de terminaison de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom de l’UC du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom de l’UC du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>type</p></td>
<td><p>Nombre de cœurs d’UC du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>type</p></td>
<td><p>Nombre de cœurs d’UC du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Vitesse de processeur de l’UC du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Vitesse de processeur de l’UC du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indique si le système de l’appelant s’exécute dans un environnement virtualisé. Pour plus d’informations, voir la <a href="lync-server-2013-endpoint-table.md">table Endpoint dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indique si le système de l’appelant s’exécute dans un environnement virtualisé. Pour plus d’informations, voir la <a href="lync-server-2013-endpoint-table.md">table Endpoint dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>Clé de corrélation. Fait référence à partir de la <a href="lync-server-2013-sessioncorrelation-table.md">table SessionCorrelation dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Des informations sur le chemin multimédia, par exemple direct ou relayé. Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant. Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant. Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Le type de transport: 0 correspond au protocole UDP; 1 est le protocole TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé par l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelant se trouve à l’intérieur du réseau intervalle: 1 désigne l’appelant à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelant se trouve à l’intérieur de l’intervalle réseau: 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom du site de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom du pays/de la région du site de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom du site du ou des appelants.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom du pays/de la région du site de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé sur le service Edge A/V utilisé par l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Clé d’adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé sur le service Edge A/V utilisé par l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom de l’appareil de capture de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom de l’appareil de rendu de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote de périphérique de capture de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote de périphérique de rendu de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom de l’appareil de capture du destinataire.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom de l’appareil de rendu de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote de l’appareil de capture du appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote du périphérique de rendu de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Type de connexion réseau de l’appelant: 0 est filaire, 1 est un réseau sans fil.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelant s’est connecté via un réseau privé virtuel: 1 est un réseau privé virtuel (VPN), 0 est non VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>décimale (18, 0)</p></td>
<td><p>Vitesse de liaison réseau pour le point de terminaison de l’appelant en bps.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Type de connexion réseau du ou du destinataire: 0 est filaire, 1 est un téléphone sans fil.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelant s’est connecté via un réseau privé virtuel: 1 est un réseau privé virtuel (VPN), 0 est non VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>décimale (18, 0)</p></td>
<td><p>Vitesse de liaison réseau pour le point de terminaison de l’appelant en bps.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). Ce problème ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante. Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitant l’estimation de la bande passante.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Scintillement du réseau maximum lors de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>décimale (5; 4)</p></td>
<td><p>Taux moyen de perte de paquets lors de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>décimale (5; 4)</p></td>
<td><p>Perte de paquets maximum observée pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>décimale (9; 4)</p></td>
<td><p>Densité moyenne de perte de paquets en rafales de pertes pendant l’appel.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Durée moyenne de perte de paquets en rafales de pertes pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>décimale (9; 4)</p></td>
<td><p>Densité moyenne de perte de paquets lors de l’intervalle entre les pics de perte de paquets.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Durée moyenne des espaces entre les pics de perte de paquets.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Nombre de paquets pour le flux audio.</p></td>
</tr>
<tr class="even">
<td><p>Bande passante</p></td>
<td><p>int</p></td>
<td><p>Estimations de bande passante pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>Baisse de la dégradation du réseau pour l’ensemble de l’appel. La plage est 0,0 à 5,0. Cette mesure indique la somme que le coût du réseau a diminué en raison de la gigue et de la perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>Dégradation du réseau maximal pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>Baisse de la dégradation du réseau à l’origine de gigue.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>Baisse de la dégradation du réseau à l’origine de la perte de paquets.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Le codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Taux d’échantillonnage pour le flux audio.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Le niveau du signal audio après le contrôle de gain analogique pour le son envoyé par l’appelant. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Niveau du signal audio de l’appelant reçu. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Le niveau sonore de contrôle du bruit de l’appelant envoyé. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Le niveau de bruit audio de contrôle de gain analogique pour le son reçu par l’appelant. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Amélioration de la perte d’écho pour l’appelant. L’unité de cette métrique est dB. Les valeurs inférieures représentent moins d’écho. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur de l’appelant. Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Moyenne des problèmes par cinq minutes pour la capture du micro de l’appelant. Pour une qualité optimale, il devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>décimale (9; 2)</p></td>
<td><p>Taux d’utilisation de l’horloge du périphérique microphone de l’appelant par rapport à l’horloge de l’UC.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>décimale (9; 2)</p></td>
<td><p>Taux d’horloge des périphériques de haut-parleurs de l’appelant par rapport à l’horloge de l’UC.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>décimale (9; 2)</p></td>
<td><p>Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>décimale (9; 2)</p></td>
<td><p>Moyenne de l’erreur d’horodatage du flux de haut-parleur de l’appelant, en millisecondes, au cours des dernières 20 secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>type</p></td>
<td><p>Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite. Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causes d’un événement ECHO pour l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>décimale (5; 2)</p></td>
<td><p>Pourcentage de temps pendant lequel l’écho est détecté dans le flux de capture du microphone de l’appelant. Si le casque est utilisé, la valeur doit être faible.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>décimale (5; 2)</p></td>
<td><p>Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé de l’appelant. Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant; Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être comprise entre-30 et-18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant. Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Contrôle automatique de gain sur le côté du serveur de médiation appliqué au son de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Moyenne quadratique (quadratique) du signal entrant à l’appelant pour les 30 premières secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Représente le niveau du signal audio du contrôle du gain sur le son de l’appel envoyé. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Niveau du signal audio pour le son de l’appelant reçu. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Le niveau sonore de contrôle du bruit d’après-analogue pour le son de l’appel envoyé. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Le niveau sonore du contrôle du bruit de la fonction de gain analogique pour le son de l’appelant reçu. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Extension du retour de l’écho pour l’appelant. L’unité de cette métrique est dB. Les valeurs inférieures représentent moins d’écho. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur de l’appelant. Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Moyenne des problèmes par cinq minutes pour la capture du micro de l’appelant. Pour une qualité optimale, il devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>décimale (9; 2)</p></td>
<td><p>Taux d’utilisation de l’horloge du périphérique du micro du destinataire, par rapport à l’horloge de l’UC.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>décimale (9; 2)</p></td>
<td><p>Taux d’horloge de l’horloge du périphérique du présentateur, par rapport à l’horloge du processeur.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>décimale (9; 2)</p></td>
<td><p>Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>décimale (9; 2)</p></td>
<td><p>Moyenne de l’erreur d’horodatage du flux de rendu du haut-parleur de l’appelant, en millisecondes, au cours des dernières 20 secondes de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>type</p></td>
<td><p>Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite. Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causes d’un événement ECHO pour l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>décimale (5; 2)</p></td>
<td><p>Pourcentage de temps pendant lequel l’écho est détecté dans le flux de capture du micro de l’appelant. Si le casque est utilisé, la valeur doit être faible.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>décimale (5; 2)</p></td>
<td><p>Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé du destinataire du appel. Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant; Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être comprise entre [-30 et-18] dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelé. Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Contrôle automatique de gain sur le côté du serveur de médiation appliqué au son de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Moyenne quadratique (quadratique) du signal entrant à l’appelant pour les 30 premières secondes de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>décimale (5; 2)</p></td>
<td><p>Taux moyen d’échantillons masqués générés par la correction audio sur des exemples classiques.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>décimale (5; 2)</p></td>
<td><p>Taux moyen d’échantillons étirés générés par la correction audio sur des exemples classiques.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>décimale (5; 2)</p></td>
<td><p>Taux moyen d’échantillons compressés générés par la correction audio sur des exemples classiques.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Durée de l’aller-retour des statistiques RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Durée de l’aller-retour maximal pour le flux audio.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>MOS du réseau à bandes moyenne pour l’appel. Cette métrique dépend du niveau de perte de paquets, de gigue et de codec utilisés. La plage est 1,0 à 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>Débit du réseau à large bande minimum pour l’appel.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>Score d’écoute de la bande moyenne prédite pour le son envoyé, avec les caractéristiques de niveau de voix, de niveau de bruit et de périphérique de capture.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>SendListenMOS minimum pour l’appel.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>Score d’écoute de la bande moyenne prédite pour le son reçu du réseau, y compris le niveau de synthèse vocale, le niveau sonore, le codec, les conditions du réseau et les caractéristiques de l’appareil de capture.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>RecvListenMOS minimum pour l’appel.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’audio FEC a été utilisé pour l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Indique la direction des informations d’identification par le biais de la déclaration p; 1 signifie que le sens du flux provient de l’appelant vers l’appelant; 0: le sens du flux provient de l’appelant.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

