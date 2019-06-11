---
title: 'Lync Server 2013: vue de session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a>Affichage de session dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Le mode session stocke les informations sur les sessions contenant des enregistrements dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.


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
<td><p>ConferenceDateTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Fait référence à partir de la table MediaLine.</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</p></td>
</tr>
<tr class="odd">
<td><p>Correspondance</p></td>
<td><p>varchar (max)</p></td>
<td><p>ID de corrélation de la session.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Catégorie de boîte de dialogue. 0 est Lync Server to Mediation Server leg; 1 est un serveur de médiation en tronçon de passerelle PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appel a été ignoré.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Ce champ, s’il est présent, indique pourquoi un appel n’a pas été ignoré, même si les ID de contournement correspondent. Pour Lync Server, une seule valeur est définie:</p>
<p>0x0001-ID de contournement inconnu pour la carte réseau par défaut</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de début de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de fin de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet du pool d’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du pool d’appel.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI d’identité ayant une assertion p d’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI d’identité affirmée de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Chaîne de l’agent utilisateur de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>type</p></td>
<td><p>Type de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Chaîne de l’agent utilisateur de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>type</p></td>
<td><p>Type d’agent utilisateur pour l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>Priorité de l’appel.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

