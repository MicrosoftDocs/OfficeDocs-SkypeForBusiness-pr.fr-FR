---
title: 'Lync Server 2013 : Table ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Table ConferenceSessionDetails dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Chaque enregistrement représente une seule session de conférence, qui peut correspondre soit à la session ayant le focus, soit à la session associée à un serveur de conférence particulier.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Valeur</p></td>
<td><p>Etranger principal</p></td>
<td><p>Durée de la demande de session; utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session de conférence. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger principal</p></td>
<td><p>IDENTIFIant de la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session de conférence. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> . *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>URI de conférence Focus liée à cette session. Pour plus d’informations, voir la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> . Cet URI est un URI de conférence en fonction du focus.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>Identificateur</p></td>
<td></td>
<td><p>Identificateur qui différencie les instances des conférences périodiques. Chaque instance de conférence périodique a le même ConferenceURI mais une valeur ConfInstance différente.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>URI de la Conférence Server Conferencing liée à cette session. Pour plus d’informations, voir la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> . Cet URI est l’URI de conférence basée sur le serveur de conférence. Pour les sessions de conférence au focus, cette colonne a la valeur null.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID d’un utilisateur dans la session de conférence. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>identificateur</p></td>
<td></td>
<td><p>GUID permettant d’identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur d’autres ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Indique l’IDENTIFIant de l’utilisateur pour lequel l’appelant a son nom. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID de l’utilisateur avec lequel l’appel est soumis. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Version du client utilisée par l’utilisateur de la Conférence. Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Version du client utilisée par le serveur de conférence. Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Externes</p></td>
<td><p>Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>IDENTIFIant de la session. Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session qui est remplacée par cette session. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indique si la session a démarré par le serveur de conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indique si la session a été terminée par le serveur de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Si l’utilisateur est connecté à partir d’un emplacement interne ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Code de réponse SIP (Session Initiation Protocol) à l’invitation à la session. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnostic capturé à partir de l’en-tête SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID du serveur frontal utilisé pour cette session. Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID du pool dans lequel la session a été capturée. Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Serveur de médiation utilisé par l’appel. Pour plus d’informations, voir la <a href="lync-server-2013-mediationservers-table.md">table MediationServers dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Passerelle utilisée par l’appel. Pour plus d’informations, voir le <a href="lync-server-2013-gateways-table.md">tableau passerelles dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Serveur Edge utilisé par l’appel. Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Type de contenu utilisé dans la session. Pour plus d’informations, voir la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure de la première demande d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure de la première réponse SIP. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externes</p></td>
<td><p>Contient la valeur du type d’URI MCU de la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a>. Ce champ permet d’améliorer les performances de requête.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Un ensemble de bits indiquant les attributs de l’utilisateur. Les définitions d’attribut suivantes apparaissent:</p>
<ul>
<li><p>Intégré au téléphone de bureau-1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Un ensemble de bits qui indique les attributs d’appel. Les définitions d’attribut suivantes apparaissent:</p>
<ul>
<li><p>Nouvelle tentative de session-1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1. S’il s’agit d’une session à partir de la même heure, le SessionIdSeq de l’une sera 1, et ainsi de suite.

</div>

<span> </span>

</div>

</div>

</div>

