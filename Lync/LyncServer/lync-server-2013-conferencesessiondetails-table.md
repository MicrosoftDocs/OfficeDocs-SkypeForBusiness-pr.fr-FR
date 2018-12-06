---
title: 'Lync Server 2013 : Table ConferenceSessionDetails'
TOCTitle: Table ConferenceSessionDetails
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412741(v=OCS.15)
ms:contentKeyID: 49298340
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ConferenceSessionDetails dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente une session de conférence. Il peut s’agir de la session avec le service Focus ou de celle avec un serveur de conférence spécifique.


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
<td><p>datetime</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de la demande de session ; utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’ID pour identifier la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.*</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI de conférence Focus associée à cette session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a>. Il s’agit d’une URI de conférence Focus.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Identificateur permettant de différencier les instances des conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI de conférence de serveur de conférence associée à cette session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a>. Il s’agit de l’URI de conférence basée sur le serveur de conférence. Pour les sessions de conférence Focus, cette colonne sera nulle.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID d’un utilisateur dans la session de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID permettant d’identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur différents ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID de l’utilisateur faisant référence à l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Version de client utilisée par l’utilisateur de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Version de client utilisée par le serveur de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro d’ID pour identifier la session. Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session remplacée par cette session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si la session est démarrée par le serveur de conférence ?</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si la session est terminée par le serveur de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si l’utilisateur est connecté en interne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Code de réponse SIP (Session Initiation Protocol) à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>ID de diagnostic capturé à partir de l’en-tête SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID du serveur frontal utilisé pour cette session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID du pool dans lequel la session a été capturée. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-pools-table.md">Table Pools dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur de médiation utilisé par l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">Table MediationServers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Passerelle utilisée par l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-gateways-table.md">Table Gateways dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur Edge utilisé par l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">Table EdgeServers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Type de contenu utilisé dans la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-contenttypes-table.md">Table ContentTypes dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Heure du premier message SIP RESPONSE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Étrangère</p></td>
<td><p>Contient la valeur de type MCU URI tirée de la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>. Ce champ sert à améliorer les performances des requêtes.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ensemble de bits qui indique les attributs de l’utilisateur. Les définitions d’attributs suivantes sont répertoriées :</p>
<ul>
<li><p>Intégré au téléphone de bureau - 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ensemble de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :</p>
<ul>
<li><p>Nouvelle tentative de session - 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* Pour la plupart des sessions, SessionIdSeq a la valeur 1. Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.

