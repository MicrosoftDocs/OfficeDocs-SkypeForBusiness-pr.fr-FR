---
title: 'Lync Server 2013 : Table ErrorReport'
TOCTitle: Table ErrorReport
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412826(v=OCS.15)
ms:contentKeyID: 49298512
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ErrorReport dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-06-22_

La table ErrorReport contient des informations sur les erreurs qui se sont produites. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Principal</p></td>
<td><p>Date et heure de l’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro d’ID identifiant le rapport d’erreur. Utilisé conjointement avec <strong>ErrorTime</strong> pour identifier de manière unique un rapport d’erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID unique du type d’erreur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errordef-table.md">Table ErrorDef dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Utilisateur à l’origine de la demande ayant provoqué l’erreur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Utilisateur de destination de la demande ayant provoqué l’erreur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI de conférence associée à l’erreur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a>. En général, si ConferenceUriId n’est pas null, FromUserId ou ToUserId est null.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Étrangère</p></td>
<td><p>Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur). Pour plus d’informations, reportez-vous à <a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a>.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur). Pour plus d’informations, reportez-vous à <a href="lync-server-2013-application-table.md">Table Application dans Lync Server 2013</a>.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>image</p></td>
<td><p> </p></td>
<td><p>Informations supplémentaires sur l’erreur.</p>
<p>Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Version cliente du point de terminaison qui envoie le rapport d’erreur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si le rapport d’erreur est capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Indicateur</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Réservé à un usage ultérieur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Représente le nom de domaine complet du serveur qui a généré le rapport d’erreurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Représente le nom de domaine complet du pool où le rapport d’erreurs a été généré.</p></td>
</tr>
</tbody>
</table>

