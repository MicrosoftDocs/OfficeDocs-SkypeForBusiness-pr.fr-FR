---
title: 'Lync Server 2013 : Liste des tables d’enregistrement des détails des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0c620eaf6b54a89604071a18f445d20816178bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Liste des tables d’enregistrement des détails des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Le schéma de base de données d’enregistrement des détails des appels (CDR) se compose des tableaux suivants.

<div>

## <a name="static-tables"></a>Tableaux statiques


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Table CallPriorities dans Lync Server 2013</a></p></td>
<td><p>Cette liste contient les différentes priorités d’appels (par exemple, l’urgence, le standard, le standard, les non urgentes, etc.).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Table ConferenceJoinTimeThresholds dans Lync Server 2013</a></p></td>
<td><p>Stocke les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Table DeRegisterType dans Lync Server 2013</a></p></td>
<td><p>Stocke la liste des causes possibles de l’inscription d’un utilisateur &quot;, telles que&quot; &quot;le client lancé&quot; &quot;, l’inscription&quot; a expiré, le blocage du client, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Table MediaList dans Lync Server 2013</a></p></td>
<td><p>Stocke la liste de types de médias qui peuvent générer des entrées dans la base de données (par exemple, messagerie instantanée, audio, vidéo et transfert de fichiers).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Table PurgeSettings dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations qui spécifient si les enregistrements de détails des appels obsolètes sont automatiquement supprimés de la base de données CDR.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Table Roles dans Lync Server 2013</a></p></td>
<td><p>Stocke la liste des rôles de conférences possibles (par exemple, participants et présentateur).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Table SIPResponseMetaData dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>Tableaux pris en charge


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a></p></td>
<td><p>Stocke les clients (le type de client et le numéro de version) de chaque client impliqué dans un appel et les informations capturées dans cette base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de ConferenceURIs utilisés dans les appels liés à la Conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Table ContentTypes dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de types de contenu SIP (Session Initiation Protocol) qui sont utilisés dans les appels d’égal à égal et les téléconférences.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Table Devices dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste d’appareils, dont le fabricant, la version matérielle et l’adresse MAC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur l’ID de boîte de dialogue de chaque session dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Table EdgeServers dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de serveurs Edge utilisés pour les appels externes.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Table Gateways dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste des passerelles utilisées pour les appels voix sur IP (VoIP).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Table HardwareVersions dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de versions matérielles d’appareils (téléphone de bureau).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Table Manufacturers dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de fabricants de périphériques (téléphone de bureau).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Table Mcus dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les divers serveurs de conférence A/V et leurs URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Table MediationServers dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de serveurs de médiation qui sont utilisés pour les appels VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Table !Phones dans Lync Server 2013</a></p></td>
<td><p>Stocke tous les numéros de téléphone utilisés pour les appels VoIP archivés ou dont les détails des appels ont été enregistrés.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Table Pools dans Lync Server 2013</a></p></td>
<td><p>Stocke les noms de la liste des messages INSTANTANÉs capturés.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a></p></td>
<td><p>Stocke le nom des serveurs impliqué dans les appels.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a></p></td>
<td><p>Stocke les locataires pris en charge par le déploiement actuel. Il s’agit de clients intégrés d’entreprise, d’utilisateurs fédérés, d’utilisateurs de la connectivité de messagerie instantanée publique et d’utilisateurs anonymes.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a></p></td>
<td><p>Mappe des identificateurs d’agent utilisateur aux noms descriptifs de l’agent.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a></p></td>
<td><p>Stocke les URI utilisateur des utilisateurs qui ont participé à des sessions enregistrées ou archivées dans cette base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Table UserStatistics dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur l’utilisation individuelle du système par un utilisateur.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Tableaux spécifiques aux enregistrements de la Conférence CDR


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur toutes les conférences archivées ou dont les détails ont été enregistrés, y compris ConferenceURI et les heures de début et de fin.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Table ConferenceSessionDetails dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur chaque session de conférence SIP, y compris l’heure de début et de fin, l’ID d’utilisateur, le code de réponse et l’ID de diagnostic de chaque session.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Table FocusJoinsAndLeaves dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les joints et les feuilles de conférence, y compris le rôle et la version du client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Table McuJoinsAndLeaves dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les serveurs de téléconférence A/V qui participent à une conférence et l’utilisateur a rejoint et laisse des heures.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Tableaux de messages dans les conférences de messagerie instantanée


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Table ConferenceMessageCount dans Lync Server 2013</a></p></td>
<td><p>Pour chaque conférence par messagerie instantanée, stocke le nombre de messages envoyés par chaque utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Table IMReportSummary dans Lync Server 2013</a></p></td>
<td><p>Fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>Tables pour les sessions d’égal à égal


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Table SessionDetails dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur chaque session d’égal à égal, y compris l’heure de début et de fin, l’ID d’utilisateur, le code de réponse et le nombre de messages pour chaque utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Table FileTransfers dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur les sessions de transfert de fichiers, y compris le nom de fichier et le résultat (accepté, rejeté ou annulé).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Table Media dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur les différents types de médias impliqués dans les sessions d’égal à égal.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Tableau des détails des appels VoIP


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Table VoipDetails dans Lync Server 2013</a></p></td>
<td><p>Pour chaque appel VoIP/PSTN à deux tiers, enregistre les informations relatives à l’appel, telles que l’ID de téléphone du téléphone VoIP, la passerelle utilisée et la partie déconnectée. Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</a> pour les appels de début/fin et le code de réponse.</p>
<div>

> [!NOTE]  
> S’il s’agit d’un utilisateur VoIP ou d’un serveur de médiation qui intervient dans le cas d’un appel, un enregistrement est créé dans ce tableau. Les informations sur les appels VoIP/VoIP qui n’impliquent pas de téléphone RTC (réseau téléphonique commuté) sont capturées dans la <A href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</A>.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Tableau pour l’audit d’appels E9-1-1


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Table Locations dans Lync Server 2013</a></p></td>
<td><p>Pour chaque appel d’urgence, par exemple un appel 9-1-1 amélioré (E9-1-1), stocke les informations d’emplacement relatives à l’appel. Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">table SessionDetails dans Lync Server 2013</a> pour les appels de début/fin et le code de réponse.</p>
<div>

> [!NOTE]  
> Ce tableau contient uniquement l’objet blob d’emplacement pour l’appel E9-1-1. Fait référence à la table SessionDetails pour obtenir d’autres informations détaillées sur l’appel.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Tableaux pour la résolution des problèmes


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Table Application dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations relatives à divers processus au sein de Lync Server 2013 qui participent au routage et aux connexions.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Table CallType dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les types de l’appel (par exemple, « audio », « messages instantanés », « audio et vidéo » et « partage d’application »).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Table ErrorCategory dans Lync Server 2013</a></p></td>
<td><p>Stocke le nom convivial pour chaque classification de diagnostic Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Table ErrorDef dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les types d’erreurs et leurs définitions.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Table ErrorReport dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur les erreurs qui se sont produites.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Table ProgressReport dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les rapports de progression de diverses étapes associées aux processus Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


Les tables de la liste suivante sont utilisées en interne par Lync Server. Leurs détails ne sont pas décrits dans ce document.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Tables pour une utilisation interne par Lync Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
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
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table frontale</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table MSMQProcessing</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table syndicators</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table SyndicatorsTenantMap</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tableau de tâches</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fuseau</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

