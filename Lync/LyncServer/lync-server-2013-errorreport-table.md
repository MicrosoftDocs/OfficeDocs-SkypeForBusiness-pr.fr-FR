---
title: 'Lync Server 2013 : table ErrorReport'
description: 'Lync Server 2013 : table ErrorReport.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572010"
---
# <a name="errorreport-table-in-lync-server-2013"></a>Table ErrorReport dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

La table ErrorReport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client.


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
<th>Clé/index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Primaire</p></td>
<td><p>Date et heure de l’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Numéro d’identification permettant d’identifier le rapport d’erreurs. Utilisé conjointement avec <strong>ErrorTime</strong> pour identifier un rapport d’erreur de manière unique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>ID unique du type d’erreur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errordef-table.md">table table errordef dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Utilisateur à l’origine de la demande à l’origine de l’erreur. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Utilisateur de destination pour la demande à l’origine de l’erreur. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>URI de conférence lié à l’erreur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> . En règle générale, si ConferenceUriId n’est pas null, FromUserId ou ToUserId sera null.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Etranger</p></td>
<td><p>Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Numéro d’ID pour identifier la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur). Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur). Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-application-table.md">table application dans Lync Server 2013</a> .</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>image</p></td>
<td><p> </p></td>
<td><p>Plus d’informations sur l’erreur.</p>
<p>Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Version client du point de terminaison qui envoie le rapport d’erreurs. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Est le rapport d’erreurs capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Indicateur</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Réservé à un usage ultérieur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>Unique</p></td>
<td></td>
<td><p>Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Représente le nom de domaine complet du serveur qui a généré le rapport d’erreurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Représente le nom de domaine complet du pool où le rapport d’erreurs a été généré.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

