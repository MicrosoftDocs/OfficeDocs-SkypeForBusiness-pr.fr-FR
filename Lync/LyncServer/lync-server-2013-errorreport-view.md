---
title: Vue ErrorReport
TOCTitle: Vue ErrorReport
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49891541
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue ErrorReport

 

_**Dernière rubrique modifiée :** 2015-03-09_

La vue ErrorReport stocke les informations sur les erreurs signalées. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client. Cette vue a été introduite dans Microsoft Lync Server 2013.


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
<td><p>datetime</p></td>
<td><p>Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’ID identifiant l’erreur. Utilisé conjointement à ErrorTime pour identifier une erreur de manière unique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnostic pour le rapport d’erreurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur à l’origine de l’erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur à l’origine de l’erreur. Voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Client de l’utilisateur à l’origine de l’erreur. Voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur cible du rapport d’erreurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur cible du rapport d’erreurs. Voir la table UriTypes pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Client de l’utilisateur cible du rapport d’erreurs. Voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de la conférence cible du rapport d’erreurs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de la conférence cible du rapport d’erreurs. Voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Heure de la demande de session à l’origine du rapport d’erreurs. Utilisé conjointement à SessionIdSeq pour identifier une session de manière unique. Voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’ID identifiant la demande de session à l’origine du rapport d’erreurs. Utilisé conjointement à SessionIdTime pour identifier une session de manière unique. Voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring(775)</p></td>
<td><p>ID de dialogue SIP de la session à l’origine de l’erreur. Le format est :</p>
<p>dialogue;de-balise;à-balise</p>
<p>Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</p>
<p>cast(cast(ExternalId as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version du client utilisé par l’utilisateur à l’origine de l’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client utilisé par l’utilisateur à l’origine de l’erreur. Voir la <a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Nom de la catégorie du client utilisé par l’utilisateur à l’origine de l’erreur.</p></td>
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
<td><p>Code de réponse SIP à la session du message SIP contenant le rapport d’erreurs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Type de la demande ayant échoué.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Type de contenu de la demande ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type de session. Voir la <a href="lync-server-2013-calltype-table.md">Table CallType dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si le rapport d’erreurs a été capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Réservé à un usage ultérieur.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Informations supplémentaires sur l’erreur.</p></td>
</tr>
</tbody>
</table>

