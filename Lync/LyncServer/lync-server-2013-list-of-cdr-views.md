---
title: 'Lync Server 2013: liste des affichages CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112e565c07c685c1ecdf5db1d8a2de8717ba959e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Liste des affichages CDR dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Les affichages offrent un moyen facile d’accéder à des informations sur les cas les plus courants utilisés pour renvoyer des données à partir de la base de données CDR. Nous vous recommandons d’utiliser des affichages pour créer des rapports personnalisés au lieu d’utiliser les tables de la base de données CDR réelle. en effet, les vues de base de données sont plus susceptibles de garantir la compatibilité descendante avec les versions ultérieures de Lync Server.


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
<td><p><a href="lync-server-2013-clientversions-view.md">Affichage ClientVersions dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur le ou les logiciels client utilisés dans une session de communication.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Affichage ConferenceMessageCount dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur le nombre de messages envoyés par les utilisateurs en conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Affichage conférences dans Lync Server 2013</a></p></td>
<td><p>Renvoie les informations de la Conférence, y compris l’heure de début, l’heure de fin et l’organisateur de la Conférence.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Affichage ConferenceSessionDetails dans Lync Server 2013</a></p></td>
<td><p>Renvoie les détails de la session pour toutes les sessions de conférence, y compris l’heure de début et de fin, les ID utilisateur, les codes de réponse et les ID de diagnostic.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Affichage ConferenceUris dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les URI de conférence utilisés dans une conférence.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Affichage ErrorReport dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les erreurs qui se sont produites pendant une session.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Affichage FileTransfers dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les sessions de transfert de fichiers, notamment le nom du fichier et si le transfert a été accepté, rejeté ou annulé.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Affichage FocusJoinsAndLeaves dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les activités de réunion et de congés.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Affichage McuJoinsAndLeaves dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations combinées sur les activités de conférence et de congés (chaque conférence est associée au départ de la Conférence correspondante).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Affichage MCU dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les serveurs de conférence.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Vue multimédia dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les types de média utilisés dans les sessions d’égal à égal de communication.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Affichage ProgressReport dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les sessions terminées.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Affichage inscription dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les inscriptions avec Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Affichage SessionDetails dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les sessions d’égal à égal, notamment les appels de téléphone VoIP et VoIP, des sessions de messagerie instantanée à deux parties ou d’autres sessions d’égal à égal.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Affichage utilisateur dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations sur les utilisateurs ayant participé à des sessions de communication.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Affichage VoIPDetails dans Lync Server 2013</a></p></td>
<td><p>Renvoie des informations pour les sessions d’égal à égal impliquant au moins un utilisateur de VoIP (Voice over IO).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

