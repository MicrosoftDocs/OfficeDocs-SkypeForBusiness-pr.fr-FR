---
title: 'Lync Server 2013 : Table MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Table MediaLine dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-21_

Chaque enregistrement représente une ligne multimédia. (Une session audio est généralement composée d’une seule ligne de média audio. Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo, bien que la session puisse contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée.


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
<td><p>Fait référence à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>0 correspond au son principal, 1 correspond à la vidéo principale et 2 correspond à la vidéo panoramique, 3 au partage d’applications et de bureau. Cette étiquette doit être unique au sein d’une même session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Cette colonne est présente mais n’est pas utilisée dans Microsoft Lync Server 2013. Les informations relatives à la connectivité utilisée pour une ligne multimédia sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs de bits. Pour plus d’informations, reportez-vous à la <em>spécification qualité de l’expérimentation du protocole serveur</em>, disponible au téléchargement.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Identique à CallerIceWarningFlags, mais au côté de l’appelant. Pour plus d’informations, reportez-vous à la <em>spécification qualité de l’expérimentation du protocole serveur</em>, disponible au téléchargement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sécurité</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Profil de sécurité utilisé. 0 est aucun, 1 est SRTP, 2 est v1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 correspond au protocole UDP, 1 au port TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Adresse IP de l’appelant. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Port utilisé par l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> Externes</p></td>
<td><p>Sous-réseau de l’appelant. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 désigne l’appelant à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Adresse MAC de l’appelant, référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Adresse IP du service Edge A/V du serveur Lync utilisé par l’appelant. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Port utilisé par l’appelant sur le service Edge A/V.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Appareil de capture utilisé par l’appelant. Fait référence à partir de la <a href="lync-server-2013-device-table.md">table de périphériques dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Périphérique de rendu utilisé par l’appelant. Fait référence à partir de la <a href="lync-server-2013-device-table.md">table de périphériques dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Pilote pour l’appareil de capture de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Pilote pour l’appareil de rendu de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externes</p></td>
<td><p>Indique la manière dont l’appelant s’est connecté au réseau. Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>. Les valeurs par défaut sont 0 pour une connexion câblée' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>BSSID de l’appelant, si la technologie sans fil est utilisée. Référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Le lien de l’appelant. 1 est un réseau privé virtuel (VPN), 0 est non VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>décimale (18, 0)</p></td>
<td></td>
<td><p>La vitesse de connexion du réseau, en BPS, pour le point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Adresse IP du destinataire de l’appel. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Port utilisé par le destinataire de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Sous-réseau de l’appelant. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 signifie que le destinataire de l’appel se trouve à l’intérieur du réseau d’entreprise, 0 correspond au destinataire de l’appel hors du réseau.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Adresse MAC du destinataire. Fait référence à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Adresse IP du service Edge A/V utilisée par le destinataire de l’appel. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Port utilisé sur le service Edge A/V par le destinataire de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>externes</p></td>
<td><p>Appareil de capture utilisé par le destinataire de l’appel. Fait référence à partir de la <a href="lync-server-2013-device-table.md">table de périphériques dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Périphérique de rendu utilisé par le destinataire de l’appel. Fait référence à partir de la <a href="lync-server-2013-device-table.md">table de périphériques dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Pilote de l’appareil de capture du destinataire de l’appel. Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Externes</p></td>
<td><p>Pilote de l’appareil de rendu du destinataire de l’appel. Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externes</p></td>
<td><p>Indique la manière dont l’appelant s’est connecté au réseau. Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>. Les valeurs par défaut sont 0 pour une connexion câblée' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Le BSSID de l’appelant si la technologie sans fil est utilisée. Référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Le lien du destinataire de l’appel ; 1 est un réseau privé virtuel (VPN), 0 est non VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>décimale (18, 0)</p></td>
<td><p> </p></td>
<td><p>La vitesse de connexion du réseau, en BPS, pour le point de terminaison du destinataire de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Il s’agit de la bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). Ce problème ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante. Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitation par l’estimation de bande passante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Il s’agit de la source de la bande passante qui est imposée. Il décrit l’emplacement à partir duquel la limite de bande passante provient (« serveur de stratégie », « activer le serveur », « modalité », etc.). Fait référence à partir de la <a href="lync-server-2013-appliedbandwidthsource-table.md">table AppliedBandwidthSource dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appelant</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indique si les mesures de l’appelant ont été reçues ; 1 est oui, la valeur null est non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appelé</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indique si les mesures du destinataire de l’appel ont été reçues. 1 est oui, la valeur null est non.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indique si l’état correspond à une partie de la session ou à la session complète.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indique si un appel a été considéré comme un appel médiocre (valeur de 1) ou comme bon appel (0).</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>Sa</p></td>
<td></td>
<td><p>Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Adresse IP réflexive de l’utilisateur qui a placé l’appel. Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Description de l’appareil pour le pilote WiFi utilisé par l’utilisateur qui a placé l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Numéro de version du pilote WiFi utilisé par l’utilisateur qui a placé l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Adresse IP réflexive de l’utilisateur qui a reçu l’appel. Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Description de l’appareil pour le pilote WiFi utilisé par l’utilisateur qui a reçu l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Numéro de version du pilote WiFi utilisé par l’utilisateur qui a reçu l’appel.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

