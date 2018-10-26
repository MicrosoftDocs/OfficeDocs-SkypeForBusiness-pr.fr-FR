---
title: 'Lync Server 2013 : Liste des tables d’enregistrement des détails des appels'
TOCTitle: Liste des tables d’enregistrement des détails des appels
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398084(v=OCS.15)
ms:contentKeyID: 49296084
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste des tables d’enregistrement des détails des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le schéma de base de données de l’enregistrement des détails des appels comprend les tables suivantes.

## Tables statiques


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
<td><p>Stocke la liste des priorités d’appel possibles, telles que les appels très urgents, urgents, normaux, non urgents, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Table ConferenceJoinTimeThresholds dans Lync Server 2013</a></p></td>
<td><p>Stocke les limites de classification utilisées par le rapport du temps de connexion à la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Table DeRegisterType dans Lync Server 2013</a></p></td>
<td><p>Stocke la liste des raisons possibles de désinscription des utilisateurs, telles que « initiative du client », « expiration de l’inscription », « blocage du client », etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Table MediaList dans Lync Server 2013</a></p></td>
<td><p>Stocke la liste des types de médias qui peuvent générer des entrées dans la base de données (par exemple, la messagerie instantanée, l’audio, la vidéo et le transfert de fichiers).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Table PurgeSettings dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations qui indiquent si (et quand) les enregistrements des détails des appels obsolètes seront automatiquement supprimés de la base de données d’enregistrement des détails des appels.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Table Roles dans Lync Server 2013</a></p></td>
<td><p>Stocke la liste possible des rôles de conférence (par exemple, participant et présentateur).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Table SIPResponseMetaData dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste des codes de réponse SIP ainsi que la classification et la définition de chacun de ces codes.</p></td>
</tr>
</tbody>
</table>


## Tables de prise en charge


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
<td><p>Stocke les clients (à la fois le type de client et le numéro de version) de chaque client impliqué dans un appel comprenant des informations capturées dans cette base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de ConferenceURI utilisés dans les appels relatifs à la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Table ContentTypes dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de types de contenus SIP (Session Initiation Protocol) utilisés à la fois dans les appels P2P et les appels de conférence.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Table Devices dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste d’appareils, notamment leur fabricant, la version du matériel et l’adresse MAC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les ID de dialogue pour chaque session dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Table EdgeServers dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de serveurs Edge utilisés pour les appels externes.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Table Gateways dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de passerelles utilisées pour les appels VoIP (Voice over Internet Protocol).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Table HardwareVersions dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de versions matérielles d’appareils (téléphone de bureau).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Table Manufacturers dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de fabricants et d’appareils (téléphone de bureau).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Table Mcus dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les différents serveurs de conférence A/V et leurs URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Table MediationServers dans Lync Server 2013</a></p></td>
<td><p>Stocke une liste de serveurs de médiation utilisés pour les appels VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Table !Phones dans Lync Server 2013</a></p></td>
<td><p>Stocke tous les numéros de téléphone utilisés dans les appels VoIP qui ont été archivés ou dont les détails des appels ont été enregistrés.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Table Pools dans Lync Server 2013</a></p></td>
<td><p>Stocke les noms du pool sur lequel les messages instantanés ont été capturés.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a></p></td>
<td><p>Stocke le nom des serveurs impliqués dans les appels.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a></p></td>
<td><p>Stocke les clients pris en charge par le déploiement en cours. Il existe des clients intégrés pour les utilisateurs d’entreprise, les utilisateurs fédérés, les utilisateurs de connectivité de messagerie instantanée publique et les utilisateurs anonymes.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a></p></td>
<td><p>Mappe les identificateurs d’agents utilisateurs aux noms descriptifs des agents.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a></p></td>
<td><p>Stocke les URI des utilisateurs qui ont participé à des sessions enregistrées ou archivées dans cette base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Table UserStatistics dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur l’utilisation du système pour chaque utilisateur.</p></td>
</tr>
</tbody>
</table>


## Tables spécifiques aux enregistrements des détails des appels de conférence


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
<td><p>Stocke des informations sur toutes les conférences qui ont été archivées ou dont les détails ont été enregistrés, notamment le ConferenceURI, et l’heure de début et de fin.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Table ConferenceSessionDetails dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur chaque session de conférence fondée sur le protocole SIP, notamment l’heure de début et de fin, l’ID utilisateur, le code de réponse et l’ID de diagnostic pour chaque session.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Table FocusJoinsAndLeaves dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les événements d’arrivée et de départ d’un utilisateur dans la conférence, notamment le rôle des utilisateurs et la version du client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Table McuJoinsAndLeaves dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les serveurs de conférence A/V impliqués dans une conférence et les heures de départ et d’arrivée de l’utilisateur.</p></td>
</tr>
</tbody>
</table>


## Tables des messages dans les conférences de messagerie instantanée


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
<td><p>Pour chaque conférence de messagerie instantanée, stocke le nombre de messages qui ont été envoyés par chaque utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Table IMReportSummary dans Lync Server 2013</a></p></td>
<td><p>Fournit un rapport global sur les sessions de messagerie instantanée ouvertes dans une organisation.</p></td>
</tr>
</tbody>
</table>


## Tables des sessions P2P


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
<td><p>Stocke des informations sur chaque session P2P, notamment l’heure de début et de fin, l’ID utilisateur, le code de réponse et le nombre de messages pour chaque utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Table FileTransfers dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les sessions de transfert de fichiers, notamment le nom de fichier et le résultat (accepté, rejeté ou annulé).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Table Media dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les différents types de médias impliqués dans les sessions P2P.</p></td>
</tr>
</tbody>
</table>


## Table des détails des appels VoIP


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
<td><p>Pour chaque appel VoIP/RTC à deux utilisateurs, stocke des informations sur l’appel, telles que l’ID téléphonique du téléphone VoIP, la passerelle utilisée et le participant qui a été déconnecté. Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">Table SessionDetails dans Lync Server 2013</a> pour le code de réponse et les heures de début et de fin de l’appel.</p>

> [!NOTE]  
> Si l’un des participants à l’appel est un utilisateur VoIP ou si un serveur de médiation a été impliqué dans cet appel, un enregistrement sera créé dans cette table. Les informations concernant les appels VoIP/VoIP n’impliquant pas de téléphone RTC (réseau téléphonique commuté) sont capturées dans la <a href="lync-server-2013-sessiondetails-table.md">Table SessionDetails dans Lync Server 2013</a>.

</td>
</tr>
</tbody>
</table>


## Table pour l’audit d’appel E9-1-1


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
<td><p>Pour chaque appel très urgents, tel que l’appel Enhanced 9-1-1 (E9-1-1), stocke les informations d’emplacement concernant l’appel. Fait référence à la <a href="lync-server-2013-sessiondetails-table.md">Table SessionDetails dans Lync Server 2013</a> pour le code de réponse et les heures de début et de fin de l’appel.</p>

> [!NOTE]  
> Cette table ne contient que le blob d’emplacement pour l’appel E9-1-1. Fait référence à la table SessionDetails pour d’autres informations détaillées concernant l’appel.

</td>
</tr>
</tbody>
</table>


## Tables d’identification et de résolution des problèmes


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
<td><p>Stocke des informations sur les différents processus dans Lync Server 2013 impliqués dans le routage et les connexions.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Table CallType dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les types d’appel, tels que « audio », « messagerie instantanée », « audio et vidéo » et « partage d’application ».</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Table ErrorCategory dans Lync Server 2013</a></p></td>
<td><p>Stocke le nom convivial de chaque classification de diagnostic Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Table ErrorDef dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les types d’erreurs et leurs définitions.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Table ErrorReport dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les erreurs qui se sont produites.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Table ProgressReport dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les rapports de progression des différentes étapes impliquées dans le processus Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


Les tables de la liste suivante sont utilisées en interne par Lync Server. Elles ne sont pas détaillées dans ce document.

## Tables destinées à une utilisation interne par Lync Server


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
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table FrontEnd</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table MSMQProcessing</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table Syndicators</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table SyndicatorsTenantMap</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table Task</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>

