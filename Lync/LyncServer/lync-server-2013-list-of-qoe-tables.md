---
title: 'Lync Server 2013 : liste des tables QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c5078ac2e8e97364455d88d32c79a03c58f0c2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513831"
---
# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Liste des tables QoE dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Le schéma de base de données comprend les tables suivantes.

**Tables de prise en charge**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Table AppSharingMetricsThreshold dans Lync Server 2013</a></p></td>
<td><p>Stocke les valeurs optimales et acceptables pour les mesures de qualité de l’expérience utilisées avec le partage d’application.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Table CodecDescription dans Lync Server 2013</a></p></td>
<td><p>Mappe des identificateurs de codec uniques à leur codec correspondant.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">IPAddress table dans Lync Server 2013</a></p></td>
<td><p>Mappe des adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’expérience (QoE).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Table NetworkConnectionDetail dans Lync Server 2013</a></p></td>
<td><p>Mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience (QoE).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations qui indiquent si (et quand) les enregistrements de qualité de l’expérience obsolètes seront automatiquement supprimés de la base de données QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Table TraceRoute dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations de routage pour les appels.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Table useragentdef table (QoE) dans Lync Server 2013</a></p></td>
<td><p>Mappe les identificateurs d’agents utilisateurs aux noms descriptifs des agents.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Table VideoMetricsThreshold dans Lync Server 2013</a></p></td>
<td><p>Stocke les valeurs optimales et acceptables pour les mesures de qualité de l’expérience utilisées avec les appels vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Table UserAgent dans Lync Server 2013</a></p></td>
<td><p>Stocke les chaînes et les types d’agent utilisateur du protocole SIP (Session Initiation Protocol) utilisés dans des sessions audio et vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Table user dans Lync Server 2013</a></p></td>
<td><p>Stocke les URI de l’utilisateur, de conférence et de téléphone utilisés dans des sessions audio et vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Tableau de points de terminaison dans Lync Server 2013</a></p></td>
<td><p>Stocke le nom de domaine complet (FQDN) de l’ordinateur des systèmes d’extrémité participant à des sessions audio et vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Table pool dans Lync Server 2013</a></p></td>
<td><p>Stocke les noms des pools auxquels appartiennent les données de mesure.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Table Device dans Lync Server 2013</a></p></td>
<td><p>Stocke les appareils de capture et les appareils de rendu qui sont utilisés dans les appels audio/vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Table DeviceDriver dans Lync Server 2013</a></p></td>
<td><p>Stocke le pilote de l’appareil de capture et de l’appareil de rendu qui sont utilisés dans les appels audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Table Conference dans Lync Server 2013</a></p></td>
<td><p>Stocke les URI de conférence pour les scénarios de conférence ou le DialogID pour d’autres scénarios.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Table table sessioncorrelation dans Lync Server 2013</a></p></td>
<td><p>Stocke le CorrelationID pour les appels PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Table PayloadDescription dans Lync Server 2013</a></p></td>
<td><p>Stocke le Codec utilisé dans les appels audio/vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Table table appliedbandwidthsource dans Lync Server 2013</a></p></td>
<td><p>Stocke la source de la bande passante utilisée dans les appels audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Table MacAddress dans Lync Server 2013</a></p></td>
<td><p>Stocke l’adresse MAC des systèmes d’extrémité participant à des sessions audio et vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Table Dialog dans Lync Server 2013</a></p></td>
<td><p>Stocke l’ID de dialogue des sessions audio et vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Table Region dans Lync Server 2013</a></p></td>
<td><p>Stocke la région du réseau définie dans le paramètre NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Table UserSite dans Lync Server 2013</a></p></td>
<td><p>Stocke le site réseau défini dans le paramètre NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Table de sous-réseau dans Lync Server 2013</a></p></td>
<td><p>Stocke le sous-réseau défini dans le paramètre NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Table table monitoredregionlink dans Lync Server 2013</a></p></td>
<td><p>Stocke le lien de région défini dans le paramètre NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Table table monitoredusersitelink</a></p></td>
<td><p>Stocke les liens du site réseau définis dans le paramètre NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Table table endpointsubnet dans Lync Server 2013</a></p></td>
<td><p>Stocke le sous-réseau du système d’extrémité participant à une session audio et vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Table serveur dans Lync Server 2013</a></p></td>
<td><p>Stocke le nom complet ou l’adresse IP du serveur via lequel passe le média.</p></td>
</tr>
</tbody>
</table>


**Tableaux de données de mesure**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Table AppSharingStream dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité de l’expérience de la transmission réseau utilisée pour le partage d’application. Mesures de qualité de l’expérience de la transmission réseau utilisée pour le partage d’application.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Table session dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations globales sur une session audio ou audio/vidéo. Une session est définie en tant que dialogue SIP audio ou vidéo entre deux points d’extrémité.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur chaque ligne de média dans une session. Une ligne de média est une collection d’un ou plusieurs flux audio et vidéo. Généralement, une ligne de média unique aura deux flux, soit audio ou vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Table AudioStream dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité du média audio pour chaque flux audio dans la ligne de média.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Table table audiosignal dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité des médias audio dans la ligne multimédia. Cela inclut les mesures d’annulation de l’écho acoustique (AEC) et de contrôle automatique de la puissance (AGC).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Table table Videostream dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité du média vidéo pour chaque flux audio dans la ligne de média.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Table table audioclientevent dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité du média audio collectées à partir de l’événement client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Table table videoclientevent dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité du média vidéo collectées à partir de l’événement client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table DiagnosticData</strong></p></td>
<td><p>Stocke les données de diagnostic qui sont destinées à un usage interne exclusivement.</p></td>
</tr>
</tbody>
</table>


**Tables des données de synthèse**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Table ServerSummary</strong></p></td>
<td><p>Stocke les données de synthèse pour les serveurs, ces données étant essentiellement utilisées pour les rapports de qualité de l’expérience (QoE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Table UserSummary</strong></p></td>
<td><p>Stocke les données de synthèse pour les utilisateurs, ces données étant essentiellement utilisées pour les rapports de qualité de l’expérience (QoE).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table CallTypeSummary</strong></p></td>
<td><p>Stocke les données de synthèse pour les types d’appel, ces données étant essentiellement utilisées pour les rapports de qualité de l’expérience (QoE).</p></td>
</tr>
</tbody>
</table>


**Tables à utilisation interne par le serveur de surveillance**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table FrontEnd</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table Task</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZones</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table CallSummary</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table DeviceCallSumary</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table Tenant</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

