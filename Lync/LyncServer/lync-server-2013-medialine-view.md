---
title: 'Affichage Lync Server 2013: MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Affichage MediaLine dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Le mode MediaLine stocke les informations relatives à chaque ligne multimédia dans la base de données. Une seule session audio contient généralement une ligne multimédia audio. Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo. Toutefois, la session peut contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée. Cet affichage a été présenté dans Microsoft Lync Server 2013.


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
<th>taille</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
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
<td><p>Sécurité</p></td>
<td><p>tinyint</p></td>
<td><p>Profil de sécurité en cours d’utilisation. 0 est aucun, 1 est SRTP, 2 est v1.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Type de transport. 0 correspond au protocole UDP, 1 au port TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
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
<td><p>Indique si l’appelant figure ou non dans le réseau de l’organisation. 1 désigne l’appelant au sein du réseau d’entreprise. 0 signifie que l’appelant se trouve hors du réseau.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>Adresse MAC de l’interface réseau utilisée par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé sur le service Edge A/V utilisé par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP de l’appelant communiquée par le service Edge A/V. Cette adresse peut être différente de l’CallerIPAddr si le client est situé derrière un NAT par exemple.</p></td>
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
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nom du pilote de périphérique de rendu de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar (256</p></td>
<td><p>Description du pilote WiFi de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar (256)</p></td>
<td><p>Version du pilote WiFi de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>Détails de la connexion réseau de l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>Identifiant de l’ensemble de services standard utilisé par les appelants WiFi.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelant s’est connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.</p></td>
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
<td><p>Indique si l’appel est inclus dans le réseau d’entreprise. 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>Adresse MAC de l’interface réseau utilisée par le destinataire.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port utilisé sur le service Edge A/V utilisé par l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Adresse IP du destinataire indiquée par le service Edge A/V. Cette adresse peut être différente de l’CalleeIPAddr si le client est situé derrière un NAT par exemple.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var (50)</p></td>
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
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar (256)</p></td>
<td><p>Description du pilote WiFi de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar (256</p></td>
<td><p>Version du pilote WiFi de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>Détails de la connexion réseau du destinataire. Pour plus d’informations, voir la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>Identificateur du jeu de service utilisé par la connexion WiFi de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appelant est connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>décimale (3, 2)</p></td>
<td><p>La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Il s’agit de la bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). Cela ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante. Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitation par l’estimation de bande passante.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar (256)</p></td>
<td><p>Source de la bande passante imposée. Il décrit l’emplacement vers lequel la limite de bande passante provient (par exemple, «serveur de stratégie», «activer le serveur» ou «modalité»).</p></td>
</tr>
<tr class="odd">
<td><p>Appelant</p></td>
<td><p>bit</p></td>
<td><p>Indique si les mesures de l’appelant ont été reçues; 1 est oui, 0 est non.</p></td>
</tr>
<tr class="even">
<td><p>Appelé</p></td>
<td><p>bit</p></td>
<td><p>Indique si les mesures du destinataire de l’appel ont été reçues. 1 est oui, 0 est non.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>Indique s’il s’agit d’une portion de l’appel ou de l’appel complet.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
<td><p>Indique si un appel a été considéré comme un appel médiocre (1) ou comme bon appel (0).</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indique si l’utilisateur s’est connecté au réseau à l’aide du protocole ICE (établissement d’une connexion Internet).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

