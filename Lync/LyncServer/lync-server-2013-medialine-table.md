---
title: 'Lync Server 2013 : table MediaLine'
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
ms.openlocfilehash: 03f967b50c2fa9eae4f2599ce96dc9c592a57006
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516141"
---
# <a name="medialine-table-in-lync-server-2013"></a>Table MediaLine dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-21_

Chaque enregistrement représente une ligne de support. (Une session audio contient généralement un seul média audio. Une session audio et vidéo (A/V) contient généralement une ligne de support audio et une ligne de support vidéo, bien que la session puisse contenir deux lignes de support vidéo si un appareil de conférence est utilisé ou si la vue de la Galerie est utilisée.


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
<td><p>Référencé à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Primaire</p></td>
<td><p>0 correspond à l’audio principal, 1 à la vidéo principale et 2 à la vidéo panoramique, 3 au partage d’application/de bureau. Cette étiquette doit être unique au sein d’une même session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>entier très petit</p></td>
<td><p> </p></td>
<td><p>Cette colonne est présente, mais n’est pas utilisée dans Microsoft Lync Server 2013. Les informations relatives à la connectivité utilisée pour une ligne multimédia sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Informations sur le processus d’établissement de connectivité interactive (ICE) décrit dans bits Flags. Pour plus d’informations, reportez-vous à la <em>spécification Quality of expérience Monitoring Server Protocol</em>, disponible en téléchargement.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Identique à CallerIceWarningFlags, mais sur le côté de l’appelé. Pour plus d’informations, reportez-vous à la <em>spécification Quality of expérience Monitoring Server Protocol</em>, disponible en téléchargement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sécurité</strong></p></td>
<td><p>entier très petit</p></td>
<td><p> </p></td>
<td><p>Le profil de sécurité utilisé. 0 est AUCUN, 1 est SRTP, 2 est V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>entier très petit</p></td>
<td><p> </p></td>
<td><p>0 est UDP, 1 est TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Adresse IP de l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
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
<td><p> Etranger</p></td>
<td><p>Sous-réseau de l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Adresse MAC de l’appelant, référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Adresse IP du service Edge A/V de Lync Server utilisé par l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Port utilisé sur le service Edge A/V par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Appareil de capture utilisé par l’appelant. Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Périphérique de rendu utilisé par l’appelant. Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Pilote pour le périphérique de capture de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Pilote pour le périphérique de rendu de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Etranger</p></td>
<td><p>Indique la façon dont l’appelant s’est connecté au réseau. Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>. Les valeurs par défaut sont 0 pour une connexion filaire' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Le BSSID de l’appelant si la connexion sans fil est utilisée. Référencé depuis la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Le lien de l’appelant. 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>décimal (18, 0)</p></td>
<td></td>
<td><p>Vitesse de la liaison réseau, en bits/s, pour le point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Adresse IP du récepteur d’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Port utilisé par le récepteur d’appels.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Sous-réseau de l’appelé. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>1 signifie que le récepteur d’appels se trouve à l’intérieur du réseau d’entreprise, 0 signifie que le récepteur d’appels se trouve à l’extérieur du réseau.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Adresse MAC de l’appelé. Référencé à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par le récepteur d’appels. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Port utilisé sur le service Edge A/V par le récepteur d’appels.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Appareil de capture utilisé par le récepteur d’appels. Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Périphérique de rendu utilisé par le récepteur d’appels. Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Pilote pour l’appareil de capture du récepteur de l’appel. Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Etranger</p></td>
<td><p>Pilote pour le périphérique de rendu du récepteur d’appel. Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Etranger</p></td>
<td><p>Indique le mode de connexion de l’appelé au réseau. Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>. Les valeurs par défaut sont 0 pour une connexion filaire' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>De l’appelé BSSID si la connexion sans fil est utilisée. Référencé depuis la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Le lien du récepteur d’appels ; 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>décimal (18, 0)</p></td>
<td><p> </p></td>
<td><p>Vitesse de la liaison réseau, en BPS, pour le point de terminaison du récepteur d’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>décimale (3, 2)</p></td>
<td><p> </p></td>
<td><p>Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Il s’agit de la bande passante réelle appliquée au flux d’envoi donné en fonction de divers paramètres de stratégie (TURN, API, SDP, Server Policy, etc.). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Il s’agit de la source de la capacité de bande passante imposée. Elle indique l’origine de la limite de bande passante ("Server Policy", "TURN Server", "modalité", etc.). Référencé à partir de la <a href="lync-server-2013-appliedbandwidthsource-table.md">table table appliedbandwidthsource dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Indique si les mesures de l’appelant ont été reçues ; 1 est oui, la valeur null est non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appelé</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Indique si les mesures du récepteur d’appels ont été reçues ; 1 est oui, la valeur null est non.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Indique si le rapport est destiné à une partie de la session ou à la session complète.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Indique si un appel a été classé comme un appel médiocre (valeur 1) ou un appel de bonne qualité (0).</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>Entier très petit</p></td>
<td></td>
<td><p>Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>entier très petit</p></td>
<td></td>
<td><p>Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Adresse IP réflexive de l’utilisateur qui a passé l’appel. Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Description de l’appareil pour le pilote WiFi employé par l’utilisateur qui a passé l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Numéro de version du pilote WiFi employé par l’utilisateur qui a passé l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Adresse IP réflexive de l’utilisateur qui a reçu l’appel. Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Description de l’appareil pour le pilote WiFi employé par l’utilisateur qui a reçu l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Numéro de version du pilote WiFi employé par l’utilisateur qui a reçu l’appel.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

