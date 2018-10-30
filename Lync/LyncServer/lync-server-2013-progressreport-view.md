---
title: Vue ProgressReport
TOCTitle: Vue ProgressReport
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49891503
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue ProgressReport

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’affichage ProgressReport stocke les informations relatives aux sessions terminées. Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic. Cette vue est une nouveauté de Microsoft Lync Server 2013.

> [!NOTE]  
> Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages.


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
<td><p>Heure à laquelle l’erreur est survenue. Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique un erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification de l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID utilisé pour identifier le rapport d’avancement. Utilisé pour distinguer des rapports d’avancement du même rapport d’erreurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnostic pour le rapport d’erreurs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificateur unique mettant en corrélation des informations d’heure d’arrivée pour les différents composants impliqués dans la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Durée (en millisecondes) requise pour qu’un composant spécifique rejoigne une conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Informations supplémentaires sur l’erreur.</p></td>
</tr>
</tbody>
</table>

