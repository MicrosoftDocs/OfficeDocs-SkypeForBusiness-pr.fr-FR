---
title: 'Lync Server 2013: rapport sur les principaux échecs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 094f5034951e20d48b05c8772698ae2983492509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="ff1a0-102">Rapport sur les principaux échecs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff1a0-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff1a0-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ff1a0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ff1a0-p101">Le rapport des principales défaillances expose les défaillances les plus fréquentes et leur évolution dans le temps. Les défaillances sont basées sur une combinaison des deux métriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="ff1a0-p102">**ID de diagnostic**. Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP. Les ID de diagnostic fournissent des informations utiles pour résoudre les problèmes liés aux appels.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="ff1a0-109">**Code de réponse**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-109">**Response code**.</span></span> <span data-ttu-id="ff1a0-110">Les codes de réponse sont utilisés dans les sessions de communication SIP pour répondre aux demandes SIP.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="ff1a0-111">Par exemple, supposons que Ken envoie la demande d’invitation à Pilar Arès (autrement dit, il appelle Ken Myer Pilar Arès).</span><span class="sxs-lookup"><span data-stu-id="ff1a0-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="ff1a0-112">Si Pilar répond, son numéro envoie le code de réponse 200 (OK), en laissant le téléphone de Ken savoir que Pilar a répondu.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="ff1a0-113">Le rapport pannes principales inclut uniquement les codes de réponse envoyés en réponse à un échec de l’appel. Le serveur Lync n’effectue pas le suivi de tous les codes de réponse émis pendant un appel.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="ff1a0-114">Les informations sont signalées pour le nombre total de sessions où une défaillance s’est produite, ainsi que pour le nombre total d’utilisateurs affectés par la panne.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="ff1a0-115">Accès au rapport des principales défaillances</span><span class="sxs-lookup"><span data-stu-id="ff1a0-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="ff1a0-116">Le rapport des principales défaillances est accessible à partir de la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="ff1a0-117">Le fait de cliquer sur la métrique de sessions signalées vous permet d’atteindre le [rapport de distribution des échecs dans Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="ff1a0-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="ff1a0-118">Optimisation de l’utilisation du rapport des principales défaillances</span><span class="sxs-lookup"><span data-stu-id="ff1a0-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="ff1a0-p105">Le rapport des principales défaillances est particulier : il vous permet de filtrer jusqu’à 5 ID de diagnostic à la fois. En règle générale, vous ne pouvez filtrer qu’un élément (par exemple, une adresse SIP d’utilisateur) à la fois. Pour filtrer plusieurs ID de diagnostic, il suffit d’entrer chaque ID dans la zone ID de diagnostic, en séparant les ID par des virgules. Si vous le souhaitez, vous pouvez laisser un espace vide après chaque virgule. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="ff1a0-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="ff1a0-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="ff1a0-123">Procédez ainsi pour afficher uniquement les appels défaillants qui correspondent à l’un de ces cinq ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="ff1a0-p106">Si vous pointez le curseur de la souris sur un code de réponse, vous voyez s’afficher une info-bulle qui vous indique la signification de ce code de réponse. Par exemple, si vous pointez sur le code de réponse 486, vous voyez s’afficher le message suivant :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="ff1a0-126">Occupé ici.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ff1a0-127">Filtres</span><span class="sxs-lookup"><span data-stu-id="ff1a0-127">Filters</span></span>

<span data-ttu-id="ff1a0-p107">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport d’activité de l’utilisateur vous permet de filtrer les données renvoyées sur la base d’éléments tels que le type d’activité (session P2P ou session de conférence) ou le code de réponse SIP qui accompagnait la session en échec. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ff1a0-132">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport des principales défaillances.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="ff1a0-133">Filtres du rapport des principales défaillances</span><span class="sxs-lookup"><span data-stu-id="ff1a0-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff1a0-134">Nom</span><span class="sxs-lookup"><span data-stu-id="ff1a0-134">Name</span></span></th>
<th><span data-ttu-id="ff1a0-135">Description</span><span class="sxs-lookup"><span data-stu-id="ff1a0-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff1a0-136"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-p108">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ff1a0-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ff1a0-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ff1a0-p109">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ff1a0-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ff1a0-142">7/7/2012</span></span></p>
<p><span data-ttu-id="ff1a0-143">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ff1a0-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ff1a0-144">7/3/2012</span></span></p>
<p><span data-ttu-id="ff1a0-145">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff1a0-146"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-p110">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ff1a0-149">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ff1a0-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ff1a0-p111">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ff1a0-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ff1a0-152">7/7/2012</span></span></p>
<p><span data-ttu-id="ff1a0-153">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ff1a0-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ff1a0-154">7/3/2012</span></span></p>
<p><span data-ttu-id="ff1a0-155">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff1a0-156"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-p112">Type d’activité. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff1a0-159">[Tous]</span><span class="sxs-lookup"><span data-stu-id="ff1a0-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="ff1a0-160">Égal à égal</span><span class="sxs-lookup"><span data-stu-id="ff1a0-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="ff1a0-161">Conférence</span><span class="sxs-lookup"><span data-stu-id="ff1a0-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff1a0-162"><strong>Modalité</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-163">À ce stade, la seule option disponible est <strong>[Tous]</strong>.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff1a0-164"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-p113">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff1a0-168"><strong>Catégorie</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-p114">Type de défaillance rencontrée. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff1a0-171">Échecs attendus et inattendus</span><span class="sxs-lookup"><span data-stu-id="ff1a0-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="ff1a0-172">Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="ff1a0-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="ff1a0-173">Un &quot;échec&quot; attendu est un échec censé se produire.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="ff1a0-174">Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="ff1a0-175">Un &quot;échec&quot; inattendu est une défaillance qui peut se produire dans un système de bon fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="ff1a0-176">Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="ff1a0-177">Si cela se produit, l’incident est marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff1a0-178"><strong>Code de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-p116">Code de réponse SIP envoyé lors de l’échec de la conférence. Entrez le code de réponse entier. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="ff1a0-181">400</span><span class="sxs-lookup"><span data-stu-id="ff1a0-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff1a0-182"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-p117">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ff1a0-185">Mesures</span><span class="sxs-lookup"><span data-stu-id="ff1a0-185">Metrics</span></span>

<span data-ttu-id="ff1a0-186">Le tableau qui suit répertorie les informations fournies dans le rapport des principales défaillances.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="ff1a0-187">Mesures du rapport des principales défaillances</span><span class="sxs-lookup"><span data-stu-id="ff1a0-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff1a0-188">Nom</span><span class="sxs-lookup"><span data-stu-id="ff1a0-188">Name</span></span></th>
<th><span data-ttu-id="ff1a0-189">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="ff1a0-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ff1a0-190">Description</span><span class="sxs-lookup"><span data-stu-id="ff1a0-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff1a0-191"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-192">Oui</span><span class="sxs-lookup"><span data-stu-id="ff1a0-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="ff1a0-193">Classement relatif sur la base du nombre de sessions signalées.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff1a0-194"><strong>Sessions signalées</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-195">Oui</span><span class="sxs-lookup"><span data-stu-id="ff1a0-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="ff1a0-196">Nombre total de sessions en échec sur la base de l’ID de diagnostic et du code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff1a0-197"><strong>Utilisateurs affectés</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-198">Oui</span><span class="sxs-lookup"><span data-stu-id="ff1a0-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="ff1a0-199">Nombre total d’utilisateurs affectés par l’échec de la session.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff1a0-200"><strong>Informations sur l’échec</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-201">Non</span><span class="sxs-lookup"><span data-stu-id="ff1a0-201">No</span></span></p></td>
<td><p><span data-ttu-id="ff1a0-202">Informations détaillées sur l’échec, notamment ID de diagnostic, code de réponse SIP et description de la cause de l’échec de la session.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff1a0-203"><strong>Tendance dans le passé</strong></span><span class="sxs-lookup"><span data-stu-id="ff1a0-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="ff1a0-204">Non</span><span class="sxs-lookup"><span data-stu-id="ff1a0-204">No</span></span></p></td>
<td><p><span data-ttu-id="ff1a0-205">Propose un graphique des échecs de session dans le temps.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

