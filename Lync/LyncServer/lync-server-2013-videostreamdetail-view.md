---
title: 'Lync Server 2013 : vue VideoStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9b6cc13721ff249d9f8bd8bc0c38260c4ca7f55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a>Vue VideoStreamDetail dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

L’affichage VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.


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
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>entier très petit</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>ID unique dans une ligne de média.</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de début de la session.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Priorité de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de domaine complet du pool des appelants.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de domaine complet du pool des appelés.</p></td>
</tr>
<tr class="even">
<td><p>Appelant</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>Appelé</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Chaîne de l’agent utilisateur de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>type</p></td>
<td><p>Type de l’agent utilisateur de l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Chaîne de l’agent utilisateur de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>type</p></td>
<td><p>Type de l’agent utilisateur de l’appelé. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie de l’agent utilisateur de l’appelé. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom du système d’extrémité de l’appelant de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom du système d’extrémité de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>Appelants</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Système d’exploitation (OS) du système d’extrémité de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Système d’exploitation (OS) du système d’extrémité de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom de l’UC du système d’extrémité de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom de l’UC du système d’extrémité de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>type</p></td>
<td><p>Nombre de cœurs de l’UC du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>type</p></td>
<td><p>Nombre de cœurs de l’UC du point de terminaison de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Vitesse du processeur de l’UC du système d’extrémité de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Vitesse du processeur de l’UC du système d’extrémité de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>entier très petit</p></td>
<td><p>Indique si le système de l’appelant s’exécute dans un environnement virtualisé. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>entier très petit</p></td>
<td><p>Indique si le système de l’appelé s’exécute dans un environnement virtualisé. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>ConnectivityIce</p></td>
<td><p>entier très petit</p></td>
<td><p>Informations sur le chemin de médias, telles que direct ou relayé. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>int</p></td>
<td><p>Type de transport : 0 correspond à UDP, 1 correspond à TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>légèrement</p></td>
<td><p>Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP de l’appelé. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé par l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>légèrement</p></td>
<td><p>Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelé est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom du site de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom du pays/de la région du site de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom du site de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nom du pays/de la région du site de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port sur le service Edge A/V utilisé par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par l’appelé. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port sur le service Edge A/V utilisé par l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du périphérique de capture de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du périphérique de rendu de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote de périphérique de capture de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote de périphérique de rendu de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du périphérique de capture de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du périphérique de rendu de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote de périphérique de capture de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote de périphérique de rendu de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>entier très petit</p></td>
<td><p>Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>légèrement</p></td>
<td><p>Indique si l’appelant s’est connecté sur un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>décimal (18,)</p></td>
<td><p>Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>entier très petit</p></td>
<td><p>Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>légèrement</p></td>
<td><p>Indique si l’appelé est connecté ou non sur un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>décimal (18, 0)</p></td>
<td><p>Vitesse de la liaison réseau pour le point de terminaison de l’appelé (en BPS).</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Gigue réseau maximum pendant l’appel.</p></td>
</tr>
<tr class="even">
<td><p>Retour</p></td>
<td><p>int</p></td>
<td><p>Durée d’aller-retour d’après les statistiques RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Durée d’aller-retour maximale pour le flux audio.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRate</p></td>
<td><p>décimal (5, 4)</p></td>
<td><p>Taux moyen de perte de paquets pendant l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>décimal (5, 4)</p></td>
<td><p>Perte maximale de paquets observée pendant l’appel.</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</p></td>
</tr>
<tr class="odd">
<td><p>Bande passante</p></td>
<td><p>int</p></td>
<td><p>Estimations de la bande passante pour le flux audio.</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>Char (9)</p></td>
<td><p>Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels. Signalée sous forme de chaîne.</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>Vitesse de transmission moyenne du flux vidéo.</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>décimale (9, 4)</p></td>
<td><p>Fréquence d’images de la vidéo reçue.</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>décimale (9, 4)</p></td>
<td><p>Fréquence d’images de la vidéo envoyée.</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>Vitesse de transmission vidéo maximale lors de la session vidéo.</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>décimale (9, 4)</p></td>
<td><p>Vitesse à laquelle les paquets vidéo ont été perdus.</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>décimal (9.4)</p></td>
<td><p>Pourcentage du nombre total de trames vidéo perdues.</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>légèrement</p></td>
<td><p>Non utilisé.</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>Quantité moyenne de bande passante allouée à la vidéo.</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>décimal (9.4)</p></td>
<td><p>Pourcentage du nombre total de trames vidéo perdues.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>légèrement</p></td>
<td><p>Direction du flux pour les informations d’identité déclarées p. 1 signifie que la direction du flux est entre l’appelant et l’appelé ; 0 signifie que la direction du flux passe de l’appelé à l’appelant.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

