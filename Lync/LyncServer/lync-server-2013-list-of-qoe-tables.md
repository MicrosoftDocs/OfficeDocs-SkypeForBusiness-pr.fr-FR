---
title: 'Lync Server 2013 : Liste des tables QoE'
TOCTitle: Liste des tables QoE
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398236(v=OCS.15)
ms:contentKeyID: 49296380
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste des tables QoE dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

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
<td><p><a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a></p></td>
<td><p>Mappe des adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’expérience (QoE).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Table NetworkConnectionDetail dans Lync Server 2013</a></p></td>
<td><p>Mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience (QoE).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Table PurgeSettings (QoE) dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations qui indiquent si (et quand) les enregistrements de qualité de l’expérience obsolètes seront automatiquement supprimés de la base de données QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Table TraceRoute dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations de routage pour les appels.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Table UserAgentDef (QoE) dans Lync Server 2013</a></p></td>
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
<td><p><a href="lync-server-2013-user-table.md">Table User dans Lync Server 2013</a></p></td>
<td><p>Stocke les URI de l’utilisateur, de conférence et de téléphone utilisés dans des sessions audio et vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Table Endpoint dans Lync Server 2013</a></p></td>
<td><p>Stocke le nom de domaine complet (FQDN) de l’ordinateur des points de terminaison participant à des sessions audio et vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Table Pool dans Lync Server 2013</a></p></td>
<td><p>Stocke les noms des pools auxquels appartiennent les données de mesure.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Table Device dans Lync Server 2013</a></p></td>
<td><p>Stocke les appareils de capture et les appareils de rendu utilisés dans les appels audio/vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Table DeviceDriver dans Lync Server 2013</a></p></td>
<td><p>Stocke le pilote de l’appareil de capture et de l’appareil de rendu utilisés dans les appels audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Table Conference dans Lync Server 2013</a></p></td>
<td><p>Stocke les URI de conférence pour les scénarios de conférence ou le DialogID pour d’autres scénarios.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Table SessionCorrelation dans Lync Server 2013</a></p></td>
<td><p>Stocke le CorrelationID pour les appels RTC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Table PayloadDescription dans Lync Server 2013</a></p></td>
<td><p>Stocke le Codec utilisé dans les appels audio/vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Table AppliedBandwidthSource dans Lync Server 2013</a></p></td>
<td><p>Stocke la source de la bande passante utilisée dans les appels audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Table MacAddress dans Lync Server 2013</a></p></td>
<td><p>Stocke l’adresse MAC des points de terminaison participant à des sessions audio et vidéo.</p></td>
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
<td><p><a href="lync-server-2013-subnet-table.md">Table Subnet dans Lync Server 2013</a></p></td>
<td><p>Stocke le sous-réseau défini dans le paramètre NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Table MonitoredRegionLink dans Lync Server 2013</a></p></td>
<td><p>Stocke le lien de région défini dans le paramètre NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Table MonitoredUserSiteLink</a></p></td>
<td><p>Stocke les liens du site réseau définis dans le paramètre NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Table EndpointSubnet dans Lync Server 2013</a></p></td>
<td><p>Stocke le sous-réseau du point de terminaison participant à une session audio et vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Table Server dans Lync Server 2013</a></p></td>
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
<td><p><a href="lync-server-2013-session-table.md">Table Session dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations globales sur une session audio ou audio/vidéo. Une session est définie en tant que dialogue SIP audio ou vidéo entre deux points de terminaison.</p></td>
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
<td><p><a href="lync-server-2013-audiosignal-table.md">Table AudioSignal de Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité du média audio dans la ligne de média, notamment les mesures de suppression d’écho et de réglage de puissance automatique.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Table VideoStream dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité du média vidéo pour chaque flux audio dans la ligne de média.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Table AudioClientEvent dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité du média audio collectées à partir de l’événement client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Table VideoClientEvent dans Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité du média vidéo collectées à partir de l’événement client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table DiagnosticData</strong></p></td>
<td><p>Stocke les données de diagnostic destinées à un usage interne exclusivement.</p></td>
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
<td><p>Stocke les d-onnées de synthèse pour les serveurs, ces données étant essentiellement utilisées pour les rapports de qualité de l’expérience (QoE).</p></td>
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
<td><p><strong>Table VideoCallSummary</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table ASCallSummary</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>

