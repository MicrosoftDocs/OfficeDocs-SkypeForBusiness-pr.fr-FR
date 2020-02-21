---
title: 'Lync Server 2013 : liste des affichages des enregistrements des détails des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8903edb911168bfe80a6eed8b0e7e78842e43a0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Liste des affichages des enregistrements des détails des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Les affichages permettent d’accéder facilement aux informations sur les scénarios les plus courants utilisés pour renvoyer des données à partir de la base de données CDR. Il est recommandé d’utiliser les vues pour créer des rapports personnalisés au lieu d’utiliser les tables de base de données des enregistrements des détails des appels. en effet, les vues de base de données sont plus susceptibles de conserver une compatibilité descendante avec les versions ultérieures de Lync Server.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la vue</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Vue ClientVersions dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur le logiciel client/les appareils utilisés dans une session de communication.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Vue ConferenceMessageCount dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur le nombre de messages envoyés par des utilisateurs pendant une conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Vue des conférences dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur la conférence, notamment l’heure de début, l’heure de fin et l’organisateur de la conférence.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Vue ConferenceSessionDetails dans Lync Server 2013</a></p></td>
<td><p>Renvoie des détails sur la session pour toutes les sessions de conférence, notamment les heures de début et de fin, les ID utilisateurs, les codes de réponse et les ID de diagnostic.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Vue ConferenceUris dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les URI de conférence utilisés pendant la conférence.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Vue ErrorReport dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les erreurs qui se sont produites pendant une session.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Vue FileTransfers dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les sessions de transfert de fichier, notamment le nom du fichier et si le transfert a été accepté, refusé ou annulé.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Vue FocusJoinsAndLeaves dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les activités de participation et de fin de participation à une conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Vue McuJoinsAndLeaves dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations combinées sur les activités de participation et de fin de participation à une conférence (chaque activité de participation à une conférence est associée à l’activité de fin de participation correspondante).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Vue des MCU dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les serveurs de conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Vue multimédia dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les types de média utilisés dans les sessions de communication d’égal à égal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Vue ProgressReport dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les sessions terminées.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Vue d’enregistrement dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les inscriptions avec Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Vue SessionDetails dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les sessions d’égal à égal, notamment les appels téléphoniques VoIP-VoIP, les sessions de messagerie instantanée à deux groupes ou d’autres sessions de communication d’égal à égal.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Affichage utilisateur dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les utilisateurs qui ont participé à des sessions de communication.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Vue VoIPDetails dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les sessions d’égal à égal impliquant au moins un utilisateur de VoIP (Voix sur IP).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

