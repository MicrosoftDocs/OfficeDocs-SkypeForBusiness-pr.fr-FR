---
title: 'Lync Server 2013 : Table ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Table ProgressReport dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Les rapports de progression sont basés sur les données chargées par le client dans la base de données une fois l’appel ou la session terminée. Les rapports de progression seront écrits uniquement pour les appels et les sessions que Lync Server 2013 détermine peut être utile à des fins de diagnostic.

Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs, mais aux messages indiquant l’état des appels ou des messages.


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
<td><p>Etranger principal</p></td>
<td><p>Date et heure du rapport d’erreur de progression contenant ce rapport de progression. Pour plus d’informations, voir la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger principal</p></td>
<td><p>Numéro d’identification utilisé conjointement avec ErrorTime, ProgressReportSeq pour identifier de façon unique un rapport de progression. Pour plus d’informations, voir la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger principal</p></td>
<td><p>Numéro identifiant le rapport d’erreur. ErrorReporSeq est utilisé en conjonction avec ErrorTime pour identifier de manière unique un rapport d’erreur. Pour plus d’informations, voir la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro d’identification pour identifier le rapport de progression. Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de manière unique un rapport de progression.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnostic du rapport de progression.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Serveur ayant envoyé le rapport d’erreur (si le rapport a été envoyé à partir d’un composant serveur). Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> . Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Le processus serveur Lync dont le rapport est sujet. Pour plus d’informations, consultez le tableau de l’application.</p></td>
</tr>
<tr class="even">
<td><p><strong>Détails</strong></p></td>
<td><p>image</p></td>
<td></td>
<td><p>Détails du rapport de progression, enregistrés au format binaire pour économiser de l’espace. Il est possible de convertir les données au format texte à l’aide de la syntaxe suivante :</p>
<p>Cast (de type « detail ») As varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>Identificateur</p></td>
<td></td>
<td><p>Identificateur unique qui met en corrélation les informations de connexion aux différents composants impliqués dans une conférence.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Durée (en millisecondes) d’un composant spécifique pour participer à une conférence.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

