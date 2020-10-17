---
title: 'Lync Server 2013 : rapport des principales défaillances'
description: 'Lync Server 2013 : rapport des principales défaillances.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 768c9a99916dece9eb76877b0cd65b057697ff95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561270"
---
# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="f702b-103">Rapport des principales défaillances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f702b-103">Top Failures Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f702b-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f702b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f702b-p101">Le rapport des principales défaillances expose les défaillances les plus fréquentes et leur évolution dans le temps. Les défaillances sont basées sur une combinaison des deux métriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f702b-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="f702b-p102">**ID de diagnostic**. Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP. Les ID de diagnostic fournissent des informations utiles pour résoudre les problèmes liés aux appels.</span><span class="sxs-lookup"><span data-stu-id="f702b-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="f702b-110">**Code de réponse**.</span><span class="sxs-lookup"><span data-stu-id="f702b-110">**Response code**.</span></span> <span data-ttu-id="f702b-111">Les codes de réponse sont utilisés dans les sessions de communication SIP pour répondre aux demandes SIP.</span><span class="sxs-lookup"><span data-stu-id="f702b-111">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="f702b-112">Par exemple, supposons que Ken envoie la demande INVITE à Pilar Ackerman (en d’autres points, supposons que Ken Myer appelle Pilar Ackerman).</span><span class="sxs-lookup"><span data-stu-id="f702b-112">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="f702b-113">Si Pilar répond, son téléphone envoie le code de réponse 200 (OK), en indiquant que le téléphone de Ken indique que Pilar a répondu.</span><span class="sxs-lookup"><span data-stu-id="f702b-113">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="f702b-114">Le rapport des principales défaillances inclut uniquement les codes de réponse qui ont été envoyés en réponse à un échec de l’appel ; Lync Server n’effectue pas le suivi de tous les codes de réponse émis au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="f702b-114">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="f702b-115">Les informations sont signalées pour le nombre total de sessions où une défaillance s’est produite, ainsi que pour le nombre total d’utilisateurs affectés par la panne.</span><span class="sxs-lookup"><span data-stu-id="f702b-115">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="f702b-116">Accès au rapport des principales défaillances</span><span class="sxs-lookup"><span data-stu-id="f702b-116">Accessing the Top Failures Report</span></span>

<span data-ttu-id="f702b-117">Le rapport des principales défaillances est accessible à partir de la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="f702b-117">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="f702b-118">Si vous cliquez sur la mesure sessions signalées, vous accédez au [rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="f702b-118">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="f702b-119">Optimisation de l’utilisation du rapport des principales défaillances</span><span class="sxs-lookup"><span data-stu-id="f702b-119">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="f702b-p105">Le rapport des principales défaillances est particulier : il vous permet de filtrer jusqu’à 5 ID de diagnostic à la fois. En règle générale, vous ne pouvez filtrer qu’un élément (par exemple, une adresse SIP d’utilisateur) à la fois. Pour filtrer plusieurs ID de diagnostic, il vous suffit d’entrer chaque ID dans la zone ID de diagnostic, en séparant les ID par des virgules. Si vous le souhaitez, vous pouvez laisser un espace vide après chaque virgule. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f702b-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="f702b-123">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="f702b-123">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="f702b-124">Procédez ainsi pour afficher uniquement les appels défaillants qui correspondent à l’un de ces cinq ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="f702b-124">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="f702b-p106">Si vous pointez le curseur de la souris sur un code de réponse, vous voyez s’afficher une info-bulle qui vous indique la signification de ce code de réponse. Par exemple, si vous pointez sur le code de réponse 486, vous voyez s’afficher le message suivant :</span><span class="sxs-lookup"><span data-stu-id="f702b-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="f702b-127">Occupé ici.</span><span class="sxs-lookup"><span data-stu-id="f702b-127">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f702b-128">Filtres</span><span class="sxs-lookup"><span data-stu-id="f702b-128">Filters</span></span>

<span data-ttu-id="f702b-p107">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’activité de l’utilisateur vous permet de filtrer les données retournées sur la base d’éléments tels que le type d’activité (session d’égal à égal ou session de conférence) ou le code de réponse SIP qui accompagnait la session en échec. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="f702b-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f702b-133">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport des principales défaillances.</span><span class="sxs-lookup"><span data-stu-id="f702b-133">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="f702b-134">Filtres du rapport des principales défaillances</span><span class="sxs-lookup"><span data-stu-id="f702b-134">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f702b-135">Nom</span><span class="sxs-lookup"><span data-stu-id="f702b-135">Name</span></span></th>
<th><span data-ttu-id="f702b-136">Description</span><span class="sxs-lookup"><span data-stu-id="f702b-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f702b-137"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-137"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-p108">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="f702b-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f702b-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f702b-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f702b-p109">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="f702b-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f702b-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f702b-143">7/7/2012</span></span></p>
<p><span data-ttu-id="f702b-144">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="f702b-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f702b-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f702b-145">7/3/2012</span></span></p>
<p><span data-ttu-id="f702b-146">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="f702b-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f702b-147"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-147"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-p110">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="f702b-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f702b-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f702b-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f702b-p111">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="f702b-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f702b-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f702b-153">7/7/2012</span></span></p>
<p><span data-ttu-id="f702b-154">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="f702b-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f702b-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f702b-155">7/3/2012</span></span></p>
<p><span data-ttu-id="f702b-156">Les semaines commencent le dimanche et se terminent le samedi.</span><span class="sxs-lookup"><span data-stu-id="f702b-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f702b-157"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-157"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-p112">Type d’activité. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f702b-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f702b-160">Tous les</span><span class="sxs-lookup"><span data-stu-id="f702b-160">[All]</span></span></p></li>
<li><p><span data-ttu-id="f702b-161">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="f702b-161">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="f702b-162">Conférence</span><span class="sxs-lookup"><span data-stu-id="f702b-162">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f702b-163"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-163"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-164">À ce stade, la seule option disponible est <strong>[Tous]</strong>.</span><span class="sxs-lookup"><span data-stu-id="f702b-164">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f702b-165"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-165"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-p113">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge. Vous pouvez sélectionner un pool donné ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement pour vous sur la base des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f702b-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f702b-169"><strong>Catégorie</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-169"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-p114">Type de défaillance rencontrée. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f702b-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f702b-172">Échecs attendus et inattendus</span><span class="sxs-lookup"><span data-stu-id="f702b-172">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="f702b-173">Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="f702b-173">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="f702b-174">Un &quot; échec attendu &quot; est un échec qui est attendu.</span><span class="sxs-lookup"><span data-stu-id="f702b-174">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="f702b-175">Par exemple, si un utilisateur a défini son statut en Ne pas déranger, vous attendez que tout appel à cette personne échoue.</span><span class="sxs-lookup"><span data-stu-id="f702b-175">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="f702b-176">Un &quot; échec inattendu &quot; est un échec qui se produit dans le cas d’un système sain.</span><span class="sxs-lookup"><span data-stu-id="f702b-176">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="f702b-177">Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="f702b-177">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="f702b-178">Si cela se produit, l’incident est marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="f702b-178">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f702b-179"><strong>Code de réponse </strong>.</span><span class="sxs-lookup"><span data-stu-id="f702b-179"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-p116">Code de réponse SIP envoyé lors de l’échec de la conférence. Entrez le code de réponse entier. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f702b-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="f702b-182">400</span><span class="sxs-lookup"><span data-stu-id="f702b-182">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f702b-183"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-183"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-p117">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="f702b-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f702b-186">Mesures</span><span class="sxs-lookup"><span data-stu-id="f702b-186">Metrics</span></span>

<span data-ttu-id="f702b-187">Le tableau qui suit répertorie les informations fournies dans le rapport des principales défaillances.</span><span class="sxs-lookup"><span data-stu-id="f702b-187">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="f702b-188">Mesures du rapport des principales défaillances</span><span class="sxs-lookup"><span data-stu-id="f702b-188">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f702b-189">Nom</span><span class="sxs-lookup"><span data-stu-id="f702b-189">Name</span></span></th>
<th><span data-ttu-id="f702b-190">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="f702b-190">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f702b-191">Description</span><span class="sxs-lookup"><span data-stu-id="f702b-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f702b-192"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-192"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-193">Oui</span><span class="sxs-lookup"><span data-stu-id="f702b-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="f702b-194">Classement relatif sur la base du nombre de sessions signalées.</span><span class="sxs-lookup"><span data-stu-id="f702b-194">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f702b-195"><strong>Sessions signalées</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-195"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-196">Oui</span><span class="sxs-lookup"><span data-stu-id="f702b-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="f702b-197">Nombre total de sessions en échec sur la base de l’ID de diagnostic et du code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="f702b-197">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f702b-198"><strong>Utilisateurs affectés</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-198"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-199">Oui</span><span class="sxs-lookup"><span data-stu-id="f702b-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="f702b-200">Nombre total d’utilisateurs affectés par l’échec de la session.</span><span class="sxs-lookup"><span data-stu-id="f702b-200">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f702b-201"><strong>Informations sur l’échec</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-201"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-202">Non</span><span class="sxs-lookup"><span data-stu-id="f702b-202">No</span></span></p></td>
<td><p><span data-ttu-id="f702b-203">Informations détaillées sur l’échec, notamment ID de diagnostic, code de réponse SIP et description de la cause de l’échec de la session.</span><span class="sxs-lookup"><span data-stu-id="f702b-203">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f702b-204"><strong>Tendance dans le passé</strong></span><span class="sxs-lookup"><span data-stu-id="f702b-204"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="f702b-205">Non</span><span class="sxs-lookup"><span data-stu-id="f702b-205">No</span></span></p></td>
<td><p><span data-ttu-id="f702b-206">Propose un graphique des échecs de session dans le temps.</span><span class="sxs-lookup"><span data-stu-id="f702b-206">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

