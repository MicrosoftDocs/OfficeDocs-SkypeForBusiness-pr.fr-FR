---
title: 'Lync Server 2013 : Table ProgressReport'
TOCTitle: Table ProgressReport
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425864(v=OCS.15)
ms:contentKeyID: 49296897
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ProgressReport dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les rapports d’avancement sont basés sur les données téléchargées par le client dans la base de données à l’issue d’un appel ou d’une session. Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic.

Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages.


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
<td><p>Primaire, étrangère</p></td>
<td><p>Date et heure du rapport d’erreurs d’avancement qui contient ce rapport d’avancement. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">Table ErrorReport dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’identification utilisé conjointement avec ErrorTime et ProgressReportSeq pour identifier de manière unique un rapport d’avancement. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">Table ErrorReport dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’identification qui identifie le rapport d’erreurs. ErrorReportSeq est utilisé conjointement avec ErrorTime pour identifier de manière unique un rapport d’erreurs. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">Table ErrorReport dans Lync Server 2013</a>.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro d’identification utilisé pour identifier le rapport d’avancement. Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de manière unique un rapport d’avancement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>ID de diagnostic du rapport d’avancement.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur qui a envoyé le rapport d’erreurs (si le rapport a été envoyé à partir d’un composant serveur). Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a>. Ce champ est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Processus Lync Server sur lequel porte le rapport. Pour plus d’informations, reportez-vous à la Table Application.</p></td>
</tr>
<tr class="even">
<td><p><strong>Détails</strong></p></td>
<td><p>image</p></td>
<td><p></p></td>
<td><p>Détails du rapport d’avancement, stockés dans un format binaire pour économiser de l’espace. Ces données peuvent être converties au format texte en utilisant la syntaxe suivante :</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Identificateur unique qui met en corrélation des informations d’heure d’arrivée pour les différents composants impliqués dans la conférence.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Durée (en millisecondes) nécessaire à un composant spécifique pour se joindre à une conférence.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

