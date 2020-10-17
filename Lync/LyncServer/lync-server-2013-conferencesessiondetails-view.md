---
title: 'Lync Server 2013 : vue ConferenceSessionDetails'
description: 'Lync Server 2013 : vue ConferenceSessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566770"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a>Vue ConferenceSessionDetails dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-12_

L’affichage ConferenceSessionDetails stocke les informations relatives aux sessions entre plusieurs participants. Chaque enregistrement représente une session de conférence, laquelle peut être la session ayant le focus ou la session basée sur un serveur de conférence spécifique. Cette vue a été introduite dans Microsoft Lync Server 2013.


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
<td><p>DateHeure</p></td>
<td><p>Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification de la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de la première requête INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Type de l’URI de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>unique</p></td>
<td><p>Identificateur permettant de différencier les instances des conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI du serveur de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Type du serveur de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur impliqué dans la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Type de l’URI de l’utilisateur qui a participé à la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Client de l’utilisateur qui a participé à la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>unique</p></td>
<td><p>Identificateur unique de l’utilisateur qui a participé à la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version du serveur de conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Type du serveur de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie du serveur de conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version du client dont s’est servi l’utilisateur qui a participé à la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client dont s’est servi l’utilisateur qui a participé à la session. Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nom de la catégorie du client dont s’est servi l’utilisateur qui a participé à la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur pour le compte duquel la session a été démarrée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Type de l’URI de l’utilisateur pour le compte duquel la session a été démarrée. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Client de l’utilisateur pour le compte duquel la session a été démarrée. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur qui a référencé la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Type de l’URI de l’utilisateur qui a référencé la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Client de l’utilisateur qui a référencé la session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>ID de dialogue SIP. Le format est le suivant :</p>
<p>:d ialog ; from-tag ; to-tag</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Numéro d’identification permettant d’identifier le dialogue remplacé par la session actuelle. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification de la session. Utilisé conjointement avec ReplacesDialogIdTime pour identifier de manière unique une session remplacée par cette session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ID de dialogue SIP de la session. Le format est le suivant :</p>
<p>boîte de dialogue ; balise ; à-tag</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Indique si la session a été démarrée par le serveur de conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Indique si la session a été terminée par le serveur de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnostic capturé à partir des en-têtes de session SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Type de contenu de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de domaine complet du serveur frontal qui a capturé les données de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de domaine complet du pool qui a capturé les données de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Serveur de médiation dont s’est servi l’utilisateur qui a participé à la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Passerelle</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Passerelle dont s’est servi l’utilisateur qui a participé à la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de domaine complet du serveur Edge dont s’est servi l’utilisateur qui a participé à la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserFlag</strong></p></td>
<td><p>type</p></td>
<td><p>Indique les attributs de l’utilisateur qui a participé à la session. Les définitions d’attributs suivantes sont autorisées :</p>
<p>0x01 - Intégré au téléphone de bureau</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>type</p></td>
<td><p>Indique les attributs de l’appel. Les définitions d’attributs suivantes sont autorisées :</p>
<p>0x01 - Nouvelle tentative de session</p>
<p>0x02 - Appel effectué par un agent pour le compte d’un groupe Response Group</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

