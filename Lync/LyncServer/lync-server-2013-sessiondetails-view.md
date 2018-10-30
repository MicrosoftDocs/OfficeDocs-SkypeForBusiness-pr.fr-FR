---
title: Vue SessionDetails
TOCTitle: Vue SessionDetails
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49891592
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue SessionDetails

 

_**Dernière rubrique modifiée :** 2015-03-09_

La vue DétailsSession stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux, ou un autre type de session. Cette vue a été introduite dans Microsoft Lync Server 2013.


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
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>dateheure</p></td>
<td><p>Heure de la demande de session. Utilisée de concert avec SessionIdSeq pour identifier de manière unique une session. Voir la table <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>entier</p></td>
<td><p>Numéro d’identification de la session. Utilisée de concert avec SessionIdTime pour identifier de manière unique une session. Voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>dateheure</p></td>
<td><p>Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données générées à partir du message INVITE initial de la session. S’il n’y a aucun message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE, or INFO). Ce champ est généralement renseigné avec des données générées à partir du message INVITE initial de la session. S’il n’y a aucun message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE, ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur ayant démarré la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur ayant participé à la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur ayant démarré la session. Voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur ayant participé à la session. Voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Locataire de l’utilisateur ayant démarré la session. Voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locataire de l’utilisateur ayant participé à la session. Voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificateur unique du point de terminaison de l’utilisateur ayant démarré la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificateur unique du point de terminaison de l’utilisateur ayant participé à la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>dateheure</p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>entier</p></td>
<td><p>Nombre de messages envoyés par l’utilisateur ayant démarré la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>entier</p></td>
<td><p>Nombre de messages envoyés par l’utilisateur ayant participé à la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version du client utilisé par l’utilisateur ayant démarré la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>entier</p></td>
<td><p>Client utilisé par l’utilisateur ayant démarré la session. Voir la <a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Nom de catégorie du client utilisé par l’utilisateur ayant démarré la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version du client utilisé par l’utilisateur ayant participé à la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToClientType</strong></p></td>
<td><p>entier</p></td>
<td><p>Client utilisé par l’utilisateur ayant participé à la session. Voir la <a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Nom de catégorie du client utilisé par l’utilisateur ayant participé à la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur cible de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Type d’URI de l’utilisateur cible de la session. Voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur au nom duquel la session a été démarrée.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur au nom duquel la session a été démarrée. Voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locataire de l’utilisateur au nom duquel la session a été démarrée. Voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur ayant référencé la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur ayant référencé la session. Voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locataire de l’utilisateur ayant référencé la session. Voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>ID de dialogue SIP. Le format est :</p>
<p>dialogue;de-balise;à-balise</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>GUID qui sert à corréler plusieurs sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>dateheure</p></td>
<td><p>Heure du dialogue remplacé par la session. Utilisé de concert avec ReplaceDialogIdSeq pour identifier de manière unique un dialogue remplacé par la session. Voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>entier</p></td>
<td><p>Numéro d’identification de la session. Utilisée de concert avec ReplaceDialogIdTime pour identifier de manière unique un dialogue remplacé par la session. Voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>ID de dialogue SIP que la session remplace. Le format est :</p>
<p>dialogue;de-balise;à-balise</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>dateheure</p></td>
<td><p>Heure de la réponse du premier message INVITE. Ce champ est généralement renseigné avec des données générées à partir du message INVITE initial de la session. S’il n’y a aucun message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE, ou INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>entier</p></td>
<td><p>Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données générées à partir du message INVITE initial de la session. S’il n’y a aucun message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE, ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>entier</p></td>
<td><p>ID de diagnostic capturé à partir des en-têtes SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type de contenu de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du serveur frontal ayant capturé les données pour cette session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du pool ayant capturé les données pour cette session.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur ayant démarré la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur ayant démarré la session</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si l’utilisateur ayant démarré la session s’est connecté à partir du réseau interne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si l’utilisateur ayant participé à la session s’est connecté à partir du réseau interne.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Priorité d’appel de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>petit entier</p></td>
<td><p>Indique les attributs de l’utilisateur ayant démarré la session. Les définitions d’attributs suivantes sont autorisées :</p>
<p>0x01 - Intégré au téléphone de bureau</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>petit entier</p></td>
<td><p>Indique les attributs de l’utilisateur ayant démarré la session. Les définitions d’attributs suivantes sont autorisées :</p>
<p>0x01 - Intégré avec le téléphone de bureau</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>petit entier</p></td>
<td><p>Indique les attributs de l’appel. Les définitions d’attributs suivantes sont autorisées :</p>
<p>0x01 - Nouvelle tentative de session</p>
<p>0x02 - Appel effectué par un agent au nom d’un Response Group</p></td>
</tr>
<tr class="even">
<td><p><strong>Emplacement</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Emplacement de l’appel d’urgence.</p></td>
</tr>
</tbody>
</table>

