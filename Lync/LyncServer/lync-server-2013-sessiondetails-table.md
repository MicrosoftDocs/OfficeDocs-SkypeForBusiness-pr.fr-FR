---
title: 'Lync Server 2013 : Table SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a>Table SessionDetails dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Chaque enregistrement représente une session d’égal à égal, qui peut être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux parties ou tout autre type de session. Vous pouvez effectuer une jointure de tableau avec le [tableau multimédia dans Lync Server 2013](lync-server-2013-media-table.md) pour trouver les détails de chaque média impliqué dans cette session.

Notez que les champs IsUser1IntegratedWithDeskPhone et IsUser2IntegratedWithDeskPhone ont été déplacés de la table SessionDetails utilisée dans Microsoft Lync Server 2013.


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
<td><p>Etranger principal</p></td>
<td><p>Durée de la demande de session. Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger principal</p></td>
<td><p>IDENTIFIant de la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique. * pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Corrélation</strong></p></td>
<td><p>identificateur</p></td>
<td></td>
<td><p>Un GUID pour corréler plusieurs sessions.</p></td>
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
<td><p><strong>User1Id</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID d’un utilisateur dans la session. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID de l’autre utilisateur de la session. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>Identificateur</p></td>
<td></td>
<td><p>GUID identifiant le point de terminaison utilisé par le premier utilisateur de la session.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>Identificateur</p></td>
<td></td>
<td><p>GUID identifiant le point de terminaison utilisé par le second utilisateur de la session.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>URI de l’utilisateur à l’origine de la demande SIP. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID de l’utilisateur qui a démarré la session. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
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
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID du serveur frontal utilisé pour cette session. Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID du pool dans lequel la session a été capturée. Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Type de contenu utilisé dans la session. Pour plus d’informations, voir la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Version du client utilisée par user1. Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Version du client utilisée par utilisateur2. Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Serveur Edge utilisé par user1. Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Serveur Edge utilisé par utilisateur2. Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Si User1 est connecté à partir d’une connexion interne ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>L’état d’une connexion interne ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure de la première demande d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations). Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure de la réponse au premier message d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Code de réponse SIP à l’invitation de la session. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnostic capturé à partir de l’en-tête SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Priorité de l’appel. Pour plus d’informations, voir la <a href="lync-server-2013-callpriorities-table.md">table CallPriorities dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre de messages envoyés par user1 lors de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre de messages envoyés par utilisateur2 lors de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure à la fin de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Un ensemble de bits qui indique le type de média de cette session. Voici les définitions des types:</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>MI</p></td>
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
<td><p>version8</p></td>
</tr>
<tr class="odd">
<td><p>AUDIO</p></td>
<td><p>Seiz</p></td>
</tr>
<tr class="even">
<td><p>CAMÉSCOPE</p></td>
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
<td><p>type</p></td>
<td></td>
<td><p>Un ensemble de bits qui indique les attributs User1. Les définitions d’attribut suivantes apparaissent:</p>
<ul>
<li><p>0x01-intégré sur le téléphone de bureau</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Un ensemble de bits qui indique les attributs utilisateur2. Les définitions d’attribut suivantes apparaissent:</p>
<ul>
<li><p>0x01-intégré sur le téléphone de bureau</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Un ensemble de bits qui indique les attributs d’appel. Les définitions d’attribut suivantes apparaissent:</p>
<ul>
<li><p>0x01-nouvelle tentative de session</p></li>
<li><p>0x02-appel émis par l’agent pour le compte d’un groupe de réponse</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Formé</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Pour une utilisation interne par le service de surveillance.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1. S’il s’agit d’une session à partir de la même heure, le SessionIdSeq de l’une sera 1, et ainsi de suite.

</div>

<span> </span>

</div>

</div>

</div>

