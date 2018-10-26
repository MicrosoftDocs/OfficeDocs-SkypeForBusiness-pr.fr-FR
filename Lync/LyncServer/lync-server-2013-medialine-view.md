---
title: Vue MediaLine
TOCTitle: Vue MediaLine
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49891237
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue MediaLine

 

_**Dernière rubrique modifiée :** 2015-03-09_

La vue MediaLine stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo, bien que la session puisse contenir deux lignes de média vidéo si un dispositif de conférence est utilisé ou si la vue Galerie est utilisée. Cette vue est une nouveauté de Microsoft Lync Server 2013.


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
<th>details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</p></td>
</tr>
<tr class="even">
<td><p>Security</p></td>
<td><p>tinyint</p></td>
<td><p>Le profil de sécurité en cours d’utilisation. 0 est AUCUN, 1 est SRTP, 2 est V1.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Type de transport. 0 est UDP, 1 est TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelant se trouve ou non à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant est à l’intérieur du réseau de l’entreprise. 0 indique que l’appelant se trouve à l’extérieur du réseau.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar(256)</p></td>
<td><p>Adresse MAC ou interface réseau utilisé par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé sur le service Edge A/V utilisé par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Adresse IP de l’appelant indiquée par le service Edge A/V. Cette adresse peut être différente de CallerIPAddr si le client se trouve derrière un dispositif NAT par exemple.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nom du périphérique de capture de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nom du périphérique de rendu de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nom du pilote de périphérique de capture de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nom du pilote de périphérique de rendu de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar(256</p></td>
<td><p>Description du pilote Wifi de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar(256)</p></td>
<td><p>Version du pilote Wifi de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar(256)</p></td>
<td><p>Détails de la connexion réseau de l’appelant. Pour plus d’informations, voir <a href="lync-server-2013-networkconnectiondetail-table.md">Table NetworkConnectionDetail dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar(256)</p></td>
<td><p>Identificateur BSSID (Basic Service Set Identifier) utilisé par la connexion WiFi de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel, 0 pour un réseau non VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Adresse IP de l’appelé. il peut s’agir d’une adresse IPv4 ou IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé par l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelé se trouve ou non à l’intérieur du réseau de l’entreprise. 1 signifie que l’appelé est à l’intérieur du réseau de l’entreprise, 0 indique que l’appelé se trouve à l’extérieur du réseau.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar(256)</p></td>
<td><p>Adresse MAC ou interface réseau utilisé par l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par l’appelé. Pour plus d’informations, voir la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé sur le service Edge A/V utilisé par l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Adresse IP de l’appelé indiquée par le service Edge A/V. Cette adresse peut être différente de CallerIPAddr si le client se trouve derrière un dispositif NAT par exemple.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var(50)</p></td>
<td><p>Nom du périphérique de capture de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nom du périphérique de rendu de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nom du pilote de périphérique de capture de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nom du pilote de périphérique de rendu de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar(256)</p></td>
<td><p>Description du pilote Wifi de l’appelé.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar(256</p></td>
<td><p>Version du pilote Wifi de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar(256)</p></td>
<td><p>Détails de la connexion réseau de l’appelé. Pour plus d’informations, voir <a href="lync-server-2013-networkconnectiondetail-table.md">Table NetworkConnectionDetail dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar(256)</p></td>
<td><p>Identificateur BSSID (Basic Service Set Identifier) utilisé par la connexion WiFi de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelé s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non-VPN.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Note MOS qualité conversation à bande étroite des sessions audio (basées sur les deux flux audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Bande passante effectivement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar(256)</p></td>
<td><p>Source de la capacité de bande passante imposée. Elle décrit l’origine de la limite de la bande passante (par exemple, « Serveur de stratégie », « Serveur TURN » ou « Modalité »).</p></td>
</tr>
<tr class="odd">
<td><p>Appelant</p></td>
<td><p>bit</p></td>
<td><p>Indique si des mesures ont été reçues de la part de l’appelant ; 1 pour oui, 0 pour non.</p></td>
</tr>
<tr class="even">
<td><p>Appelé</p></td>
<td><p>bit</p></td>
<td><p>Indique si des mesures ont été reçues de la part du récepteur de l’appel ; 1 pour oui, 0 pour non.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>Indique si le rapport s’applique à une partie de l’appel ou à l’intégralité de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
<td><p>Indique si un appel a été classé comme médiocre (1) ou bon (0).</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indique si l’utilisateur appelé s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</p></td>
</tr>
</tbody>
</table>

