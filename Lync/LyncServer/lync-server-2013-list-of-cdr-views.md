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

# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="55ec8-102">Liste des affichages CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55ec8-102">List of CDR views in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55ec8-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="55ec8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="55ec8-104">Les affichages offrent un moyen facile d’accéder à des informations sur les cas les plus courants utilisés pour renvoyer des données à partir de la base de données CDR.</span><span class="sxs-lookup"><span data-stu-id="55ec8-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="55ec8-105">Nous vous recommandons d’utiliser des affichages pour créer des rapports personnalisés au lieu d’utiliser les tables de la base de données CDR réelle. en effet, les vues de base de données sont plus susceptibles de garantir la compatibilité descendante avec les versions ultérieures de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55ec8-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55ec8-106">Nom de la vue</span><span class="sxs-lookup"><span data-stu-id="55ec8-106">View Name</span></span></th>
<th><span data-ttu-id="55ec8-107">Description</span><span class="sxs-lookup"><span data-stu-id="55ec8-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55ec8-108"><a href="lync-server-2013-clientversions-view.md">Affichage ClientVersions dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-109">Renvoie des informations sur le ou les logiciels client utilisés dans une session de communication.</span><span class="sxs-lookup"><span data-stu-id="55ec8-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55ec8-110"><a href="lync-server-2013-conferencemessagecount-view.md">Affichage ConferenceMessageCount dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-111">Renvoie des informations sur le nombre de messages envoyés par les utilisateurs en conférence.</span><span class="sxs-lookup"><span data-stu-id="55ec8-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55ec8-112"><a href="lync-server-2013-conferences-view.md">Affichage conférences dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-113">Renvoie les informations de la Conférence, y compris l’heure de début, l’heure de fin et l’organisateur de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="55ec8-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55ec8-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Affichage ConferenceSessionDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-115">Renvoie les détails de la session pour toutes les sessions de conférence, y compris l’heure de début et de fin, les ID utilisateur, les codes de réponse et les ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="55ec8-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55ec8-116"><a href="lync-server-2013-conferenceuris-view.md">Affichage ConferenceUris dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-117">Renvoie des informations sur les URI de conférence utilisés dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="55ec8-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55ec8-118"><a href="lync-server-2013-errorreport-view.md">Affichage ErrorReport dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-119">Renvoie des informations sur les erreurs qui se sont produites pendant une session.</span><span class="sxs-lookup"><span data-stu-id="55ec8-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55ec8-120"><a href="lync-server-2013-filetransfers-view.md">Affichage FileTransfers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-121">Renvoie des informations sur les sessions de transfert de fichiers, notamment le nom du fichier et si le transfert a été accepté, rejeté ou annulé.</span><span class="sxs-lookup"><span data-stu-id="55ec8-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55ec8-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Affichage FocusJoinsAndLeaves dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-123">Renvoie des informations sur les activités de réunion et de congés.</span><span class="sxs-lookup"><span data-stu-id="55ec8-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55ec8-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Affichage McuJoinsAndLeaves dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-125">Renvoie des informations combinées sur les activités de conférence et de congés (chaque conférence est associée au départ de la Conférence correspondante).</span><span class="sxs-lookup"><span data-stu-id="55ec8-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55ec8-126"><a href="lync-server-2013-mcus-view.md">Affichage MCU dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-127">Renvoie des informations sur les serveurs de conférence.</span><span class="sxs-lookup"><span data-stu-id="55ec8-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55ec8-128"><a href="lync-server-2013-media-view.md">Vue multimédia dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-129">Renvoie des informations sur les types de média utilisés dans les sessions d’égal à égal de communication.</span><span class="sxs-lookup"><span data-stu-id="55ec8-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55ec8-130"><a href="lync-server-2013-progressreport-view.md">Affichage ProgressReport dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-131">Renvoie des informations sur les sessions terminées.</span><span class="sxs-lookup"><span data-stu-id="55ec8-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55ec8-132"><a href="lync-server-2013-registration-view.md">Affichage inscription dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-133">Renvoie des informations sur les inscriptions avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55ec8-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55ec8-134"><a href="lync-server-2013-sessiondetails-view.md">Affichage SessionDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-135">Renvoie des informations sur les sessions d’égal à égal, notamment les appels de téléphone VoIP et VoIP, des sessions de messagerie instantanée à deux parties ou d’autres sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="55ec8-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55ec8-136"><a href="lync-server-2013-user-view.md">Affichage utilisateur dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-137">Renvoie des informations sur les utilisateurs ayant participé à des sessions de communication.</span><span class="sxs-lookup"><span data-stu-id="55ec8-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55ec8-138"><a href="lync-server-2013-voipdetails-view.md">Affichage VoIPDetails dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="55ec8-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="55ec8-139">Renvoie des informations pour les sessions d’égal à égal impliquant au moins un utilisateur de VoIP (Voice over IO).</span><span class="sxs-lookup"><span data-stu-id="55ec8-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

