---
title: 'Affichage Lync Server 2013 : ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Affichage ErrorReport dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-22_

Le mode ErrorReport stocke les informations sur les erreurs signalées. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR exécuté sur le serveur frontal ou envoyées par le client. Cet affichage a été présenté dans Microsoft Lync Server 2013.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>L’heure de l’erreur s’est produite. Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique une erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification pour identifier l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnostic du rapport d’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur à l’origine de l’erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur à l’origine de l’erreur. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Client de l’utilisateur à l’origine de l’erreur. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Visite guidée</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur qui a été la cible du rapport d’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur qui a ciblé le rapport d’erreur. Pour plus d’informations, voir la table UriTypes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Client de l’utilisateur qui cible le rapport d’erreur. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la Conférence qui était la cible du rapport d’erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de la Conférence qui était la cible du rapport d’erreur. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Durée de la demande de session à l’origine du rapport d’erreur. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification identifiant la demande de session à l’origine du rapport d’erreur. Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (LGA775)</p></td>
<td><p>ID de boîte de dialogue SIP de session à l’origine de l’erreur. Le format est le suivant :</p>
<p>boîte de dialogue ; à partir d’une balise</p>
<p>Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante :</p>
<p>Cast (Cast (ExternalId) en tant que varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version du client utilisée par l’utilisateur à l’origine de l’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>TypeClient</strong></p></td>
<td><p>int</p></td>
<td><p>Client utilisé par l’utilisateur à l’origine de l’erreur. Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nom de la catégorie du client utilisée par l’utilisateur à l’origine de l’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Code de réponse SIP à la session du message SIP contenant le rapport d’erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Type de requête ayant échoué.</p></td>
</tr>
<tr class="even">
<td><p><strong>Indiquez</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Type de contenu de la requête qui a échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type de session. Pour plus d’informations, voir la <a href="lync-server-2013-calltype-table.md">table CallType dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>identificateur</p></td>
<td><p>Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si le rapport d’erreur a été capturé par l’agent CDR exécuté sur le serveur frontal ou envoyé par le client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Indication</strong></p></td>
<td><p>type</p></td>
<td><p>Réservé pour une utilisation ultérieure.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Informations supplémentaires sur l’erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Nom de domaine complet du serveur frontal qui a soumis le rapport.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Nom de domaine complet du pool contenant le serveur frontal qui a soumis le rapport.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

