---
title: 'Affichage Lync Server 2013: ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 423d99211a89ef328bc62aca89a9b65141e128ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a>Affichage ProgressReport dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

L’affichage ProgressReport stocke les informations sur les sessions terminées. Les rapports de progression seront écrits uniquement pour les appels et les sessions que Lync Server 2013 détermine peut être utile à des fins de diagnostic. Cet affichage a été présenté dans Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs, mais aux messages indiquant l’état des appels ou des messages.



</div>


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
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID pour identifier le rapport de progression. Permet de distinguer les rapports de progression d’un même rapport d’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnostic du rapport d’erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>identificateur</p></td>
<td><p>Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Informations supplémentaires sur l’erreur.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

