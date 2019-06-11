---
title: 'Lync Server 2013 : Liste des tables QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c82c38a995fd9e847057fedbbce1422085332b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Liste des tables QoE dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

Le schéma de base de données se compose des tables suivantes.

**Tableaux pris en charge**


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
<td><p>Stocke les valeurs optimales et acceptables pour la qualité de mesure d’utilisation utilisée avec le partage d’application.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Table CodecDescription dans Lync Server 2013</a></p></td>
<td><p>Mappe des identificateurs de codec uniques au codec correspondant.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a></p></td>
<td><p>Mappe les adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’utilisation.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Table NetworkConnectionDetail dans Lync Server 2013</a></p></td>
<td><p>Mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’utilisation.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations qui spécifient si (et quand) les enregistrements de qualité d’expérimentation obsolètes seront automatiquement supprimés de la base de données QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Tableau TraceRoute dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations d’acheminement des appels.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) dans Lync Server 2013</a></p></td>
<td><p>Mappe des identificateurs d’agent utilisateur aux noms descriptifs de l’agent.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Table VideoMetricsThreshold dans Lync Server 2013</a></p></td>
<td><p>Stocke les valeurs optimales et acceptables pour la qualité de mesure d’utilisation utilisée avec les appels vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Table UserAgent dans Lync Server 2013</a></p></td>
<td><p>Stocke les chaînes d’agent utilisateur SIP (Session Initiation Protocol) et les types UA utilisés dans les sessions audio et vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Table User dans Lync Server 2013</a></p></td>
<td><p>Stocke les URI d’utilisateur, de conférence et de téléphone utilisés dans les sessions audio et vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Table Endpoint dans Lync Server 2013</a></p></td>
<td><p>Stocke les noms de domaine complets des points de terminaison participant aux sessions audio et vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Table Pool dans Lync Server 2013</a></p></td>
<td><p>Stocke les noms des pools auxquels les données de mesure appartiennent.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Table Device dans Lync Server 2013</a></p></td>
<td><p>Stocker des périphériques de capture et des appareils de rendu qui sont utilisés dans un appel audio/vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Table DeviceDriver dans Lync Server 2013</a></p></td>
<td><p>Stocke le pilote pour l’appareil de capture et l’appareil de rendu utilisé pour les appels audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Table Conference dans Lync Server 2013</a></p></td>
<td><p>Stocke les URI de conférence pour les scénarios de conférence ou DialogID pour d’autres scénarios.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Table SessionCorrelation dans Lync Server 2013</a></p></td>
<td><p>Stocke l’CorrelationID pour les appels PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Table PayloadDescription dans Lync Server 2013</a></p></td>
<td><p>Stocke le codec utilisé pour les appels audio/vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Table AppliedBandwidthSource dans Lync Server 2013</a></p></td>
<td><p>Stocke la source de bande passante utilisée dans les appels audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Table MacAddress dans Lync Server 2013</a></p></td>
<td><p>Stocke l’adresse MAC des points de terminaison qui participent à des sessions audio et vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Table Dialog dans Lync Server 2013</a></p></td>
<td><p>Stocke l’ID de boîte de dialogue des sessions audio et vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Table Region dans Lync Server 2013</a></p></td>
<td><p>Stocke la région réseau définie dans le paramètre NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Table UserSite dans Lync Server 2013</a></p></td>
<td><p>Stocke le site réseau défini dans le paramètre NC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Table Subnet dans Lync Server 2013</a></p></td>
<td><p>Stocke le sous-réseau défini dans le paramètre NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Table MonitoredRegionLink dans Lync Server 2013</a></p></td>
<td><p>Stocke le lien région défini dans le paramètre NC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Table MonitoredUserSiteLink</a></p></td>
<td><p>Stocke les liens de site réseau définis dans le paramètre NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Table EndpointSubnet dans Lync Server 2013</a></p></td>
<td><p>Stocke le sous-réseau du point de terminaison participant à une session audio et vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Table Server dans Lync Server 2013</a></p></td>
<td><p>Stocke le nom complet ou l’adresse IP du serveur sur lequel le média est transmis.</p></td>
</tr>
</tbody>
</table>


**Tableaux pour les données de mesure**


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
<td><p>Stocke les métriques de qualité de l’utilisation pour les flux réseau utilisés pour le partage d’application. Métrique de qualité de l’utilisation des flux réseau utilisés pour le partage d’application.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Table Session dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations globales sur une session audio ou vidéo. Une session est définie sous forme de boîte de dialogue SIP audio ou vidéo entre deux points de terminaison.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations relatives à chaque ligne multimédia dans une session. Une ligne de média est une collection d’un ou de plusieurs flux audio et vidéo. En règle générale, une seule ligne multimédia comporte deux flux, audio ou vidéo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Table AudioStream dans Lync Server 2013</a></p></td>
<td><p>Stocke les métriques de qualité de média audio de chaque flux audio dans la ligne multimédia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Table AudioSignal de Lync Server 2013</a></p></td>
<td><p>Stocke les mesures de qualité de média audio dans la ligne multimédia. Cela inclut les métriques de suppression de l’écho acoustique et de contrôle de gain automatique.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Table VideoStream dans Lync Server 2013</a></p></td>
<td><p>Stocke les métriques de qualité de média vidéo pour chaque flux audio dans la ligne multimédia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Table AudioClientEvent dans Lync Server 2013</a></p></td>
<td><p>Stocke les métriques de qualité de média audio collectées à partir de l’événement client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Table VideoClientEvent dans Lync Server 2013</a></p></td>
<td><p>Stocke les métriques de qualité de média vidéo collectées à partir de l’événement client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table DiagnosticData</strong></p></td>
<td><p>Stocke les données de diagnostic pour un usage interne uniquement.</p></td>
</tr>
</tbody>
</table>


**Tableaux pour les données récapitulatives**


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
<td><p>Stocke les données de synthèse pour les serveurs, ces données sont utilisées pour le rapport qualité de l’utilisation (QoE) uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table UserSummary</strong></p></td>
<td><p>Stocke les données de synthèse des utilisateurs, ces données sont utilisées uniquement pour le rapport QoE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table CallTypeSummary</strong></p></td>
<td><p>Données de synthèse du magasin pour les types d’appel, ces données sont utilisées uniquement pour le rapport QoE.</p></td>
</tr>
</tbody>
</table>


**Tables pour une utilisation interne par le serveur de surveillance**


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
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table frontale</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tableau de tâches</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fuseau</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table CallSummary</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table DeviceCallSumary</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table de locataire</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

