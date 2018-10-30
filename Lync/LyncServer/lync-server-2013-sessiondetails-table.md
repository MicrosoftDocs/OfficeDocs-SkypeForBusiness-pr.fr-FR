---
title: 'Lync Server 2013 : Table SessionDetails'
TOCTitle: Table SessionDetails
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398589(v=OCS.15)
ms:contentKeyID: 49297798
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table SessionDetails dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente une session P2P ; il peut s’agir d’un appel téléphonique VoIP-VoIP, d’une session de messagerie instantanée à deux participants ou de tout autre type de session. Vous pouvez effectuer une jointure de table avec la [Table Media dans Lync Server 2013](lync-server-2013-media-table.md) pour rechercher les détails de chaque média impliqué dans cette session.

Notez que les champs IsUser1IntegratedWithDeskPhone et IsUser2IntegratedWithDeskPhone ont été supprimés de la table SessionDetails utilisée dans Microsoft Lync Server 2013.


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
<td><p>DateHeure</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de la demande de session. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. * Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID permettant de corréler plusieurs sessions.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>DateHeure</p></td>
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
<td><p><strong>User1Id</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID d’un utilisateur dans la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID de l’autre utilisateur dans la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID qui identifie le point de terminaison utilisé par le premier utilisateur dans la session.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID qui identifie le point de terminaison utilisé par le deuxième utilisateur dans la session.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI de l’utilisateur « À » d’origine dans la demande SIP. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID de l’utilisateur ayant démarré la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
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
<td><p><strong>ServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID du serveur frontal utilisé pour cette session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID du pool dans lequel la session a été capturée. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-pools-table.md">Table Pools dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Type de contenu utilisé dans la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-contenttypes-table.md">Table ContentTypes dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Version de client utilisée par User1. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Version de client utilisée par User2. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur Edge utilisé par User1. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">Table EdgeServers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur Edge utilisé par User2. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">Table EdgeServers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si User1 est connecté en interne.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si User2 est connecté en interne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p></p></td>
<td><p>Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO). Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p></p></td>
<td><p>Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données générées à partir du message INVITE initial de la session. S’il n’y a aucun message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE, ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>ID de diagnostic capturé à partir de l’en-tête SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Priorité de l’appel. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-callpriorities-table.md">Table CallPriorities dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nombre de messages envoyés par User1 durant la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nombre de messages envoyés par User2 durant la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p></p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Ensemble de bits qui indique le type de média de cette session. Voici les définitions des types :</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>IM (Messagerie instantanée)</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>AUDIO</p></td>
<td><p>16</p></td>
</tr>
<tr class="even">
<td><p>VIDEO</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ensemble de bits qui indique les attributs de User1. Les définitions d’attributs suivantes sont répertoriées :</p>
<ul>
<li><p>0x01 - Intégré au téléphone de bureau</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ensemble de bits qui indique les attributs de User2. Les définitions d’attributs suivantes sont répertoriées :</p>
<ul>
<li><p>0x01 - Intégré au téléphone de bureau</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ensemble de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :</p>
<ul>
<li><p>0x01 - Nouvelle tentative de session</p></li>
<li><p>0x02 - Appel effectué par un agent pour le compte d’un groupe de réponse</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Traité</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Réservé à un usage interne par le service de surveillance.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\* Pour la plupart des sessions, SessionIdSeq a la valeur 1. Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.

