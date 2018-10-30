---
title: 'Lync Server 2013 : Table MediaLine '
TOCTitle: Table MediaLine
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425920(v=OCS.15)
ms:contentKeyID: 49297010
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table MediaLine dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente une ligne de média. (Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo, même si la session peut contenir deux lignes de média vidéo si un dispositif de conférence est utilisé ou si la vue Galerie est utilisée.)


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
<td><p>Référencée depuis la <a href="lync-server-2013-session-table.md">Table Session dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-session-table.md">Table Session dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>0 est audio principal, 1 est vidéo principale, 2 est vidéo panoramique et 3 est partage d’application/bureau. Cette étiquette doit être unique au cours d’une même session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Même si cette colonne est présente, elle n’est pas utilisée dans Microsoft Lync Server 2013. Les informations relatives à la connectivité utilisée pour une ligne de média sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires. Pour plus d’informations, reportez-vous à <em>Quality of Experience Monitoring Server Protocol Specification</em> , que vous pouvez télécharger.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Identique à CallerIceWarningFlags, mais du côté de l’appelé. Pour plus d’informations, reportez-vous à <em>Quality of Experience Monitoring Server Protocol Specification</em> , que vous pouvez télécharger.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sécurité</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Le profil de sécurité en cours d’utilisation. 0 est AUCUN, 1 est SRTP, 2 est V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 est UDP, 1 est TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Adresse IP de l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Port utilisé par l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Sous-réseau de l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 signifie que l’appelant est à l’intérieur du réseau de l’entreprise, 0 signifie que l’appelant est en dehors du réseau.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Adresse mac de l’appelant, référencée depuis la <a href="lync-server-2013-macaddress-table.md">Table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Adresse IP du service Edge A/V Lync Server utilisé par l’appelant. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Port utilisé sur le service Edge A/V par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Périphérique de capture utilisé par l’appelant. Référencé depuis la <a href="lync-server-2013-device-table.md">Table Device dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Périphérique de rendu utilisé par l’appelant. Référencé depuis la <a href="lync-server-2013-device-table.md">Table Device dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Pilote pour le périphérique de capture de l’appelant, référencé depuis la <a href="lync-server-2013-devicedriver-table.md">Table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Pilote pour le périphérique de rendu de l’appelant, référencé depuis la <a href="lync-server-2013-devicedriver-table.md">Table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Étrangère</p></td>
<td><p>Indique le mode de connexion de l’appelant au réseau. Les valeurs sont obtenues via la <a href="lync-server-2013-networkconnectiondetail-table.md">Table NetworkConnectionDetail dans Lync Server 2013</a>. Les valeurs typiques sont 0 pour une connexion câblée, 1 pour une connexion WiFi et 3 pour une connexion Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>BSSID de l’appelant si le mode sans fil est utilisé. Référencé depuis la <a href="lync-server-2013-macaddress-table.md">Table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Liaison de l’appelant. 1 pour réseau privé virtuel (VPN), 0 pour non-VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimal(18,0)</p></td>
<td><p></p></td>
<td><p>Vitesse de la liaison réseau, en bits/s, pour le point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Adresse IP du récepteur de l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Port utilisé par le récepteur de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Sous-réseau de l’appelé. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 signifie que le récepteur de l’appel est à l’intérieur du réseau de l’entreprise, 0 signifie que le récepteur de l’appel est en dehors du réseau.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Adresse Mac de l’appelé. Référencée depuis la <a href="lync-server-2013-macaddress-table.md">Table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par le destinataire de l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Port utilisé sur le service Edge A/V par le récepteur de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Périphérique de capture utilisé par le récepteur de l’appel. Référencé depuis la <a href="lync-server-2013-device-table.md">Table Device dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Périphérique de rendu utilisé par le récepteur de l’appel. Référencé depuis la <a href="lync-server-2013-device-table.md">Table Device dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Pilote pour le périphérique de capture du récepteur de l’appel, référencé depuis la <a href="lync-server-2013-devicedriver-table.md">Table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Étrangère</p></td>
<td><p>Pilote pour le périphérique de rendu du récepteur de l’appel, référencé depuis la <a href="lync-server-2013-devicedriver-table.md">Table DeviceDriver dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Étrangère</p></td>
<td><p>Indique le mode de connexion de l’appelé au réseau. Les valeurs sont obtenues via la <a href="lync-server-2013-networkconnectiondetail-table.md">Table NetworkConnectionDetail dans Lync Server 2013</a>. Les valeurs typiques sont 0 pour une connexion câblée, 1 pour une connexion WiFi et 3 pour une connexion Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>BSSID de l’appelé si le mode sans fil est utilisé. Référencé depuis la <a href="lync-server-2013-macaddress-table.md">Table MacAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Liaison du récepteur l’appel. 1 pour réseau privé virtuel (VPN), 0 pour non-VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimal(18,0)</p></td>
<td><p> </p></td>
<td><p>Vitesse de la liaison réseau, en bits/s, pour le point de terminaison du récepteur de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Bande passante effectivement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Source de la limite de bande passante imposée. Elle décrit d’où provient la limite de bande passante (serveur de stratégie, serveur TURN, modalité, etc.). Référencée depuis la <a href="lync-server-2013-appliedbandwidthsource-table.md">Table AppliedBandwidthSource dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indique si des mesures ont été reçues de la part de l’appelant ; 1 pour oui, une valeur null pour non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Callee</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indique si des mesures ont été reçues de la part du récepteur de l’appel ; 1 pour oui, une valeur null pour non.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si le rapport porte sur une partie de la session ou sur la session entière.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si un appel a été classé comme étant un appel médiocre (valeur 1) ou un appel de bonne qualité (0).</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td><p></p></td>
<td><p>Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Adresse IP réflexive de l’utilisateur qui a passé l’appel. Dans les organisations qui utilisent la conversion d’adresses réseau (NAT), l’adresse IP réflexive correspond à l’adresse IP du serveur proxy.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Description de l’appareil correspondant au pilote WiFi employé par l’utilisateur qui a passé l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro de version du pilote WiFi employé par l’utilisateur qui a passé l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Adresse IP réflexive de l’utilisateur qui a reçu l’appel. Dans les organisations qui utilisent la conversion d’adresses réseau (NAT), l’adresse IP réflexive correspond à l’adresse IP du serveur proxy.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Description de l’appareil correspondant au pilote WiFi employé par l’utilisateur qui a reçu l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro de version du pilote WiFi employé par l’utilisateur qui a reçu l’appel.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

