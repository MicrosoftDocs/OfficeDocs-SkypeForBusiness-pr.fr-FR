---
title: 'Lync Server 2013 : rapport de diagnostic des activités d’égal à égal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b72e9caec70a31280001875063cd6b7d233c500
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="856eb-102">Rapport de diagnostic des activités d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856eb-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="856eb-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="856eb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="856eb-104">Le rapport de diagnostic des activités d’égal à égal fournit des informations sur la réussite ou l’échec des sessions de communication d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="856eb-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="856eb-105">Notez que Microsoft Lync Server 2013 différencie les différents types de défaillance :</span><span class="sxs-lookup"><span data-stu-id="856eb-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="856eb-106">**Échec attendu**.</span><span class="sxs-lookup"><span data-stu-id="856eb-106">**Expected failure**.</span></span> <span data-ttu-id="856eb-107">Un échec attendu est en général un échec considéré comme strictement technique.</span><span class="sxs-lookup"><span data-stu-id="856eb-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="856eb-108">Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit absente de son bureau et ne puisse donc répondre à votre appel.</span><span class="sxs-lookup"><span data-stu-id="856eb-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="856eb-109">Étant donné que l’appel n’a pas été répondu, il est techniquement considéré comme un échec.</span><span class="sxs-lookup"><span data-stu-id="856eb-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="856eb-110">En revanche, il s’agit d’un échec attendu : Microsoft Lync Server 2013 ne s’attend pas à ce que vous répondiez au téléphone si vous n’êtes pas disponible pour répondre au téléphone.</span><span class="sxs-lookup"><span data-stu-id="856eb-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="856eb-111">De même, un échec attendu se produira si vous tentez d’envoyer un message instantané à un utilisateur qui est hors ligne ou qui est connecté à un téléphone qui ne prend pas les messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="856eb-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="856eb-112">**Échec inattendu**.</span><span class="sxs-lookup"><span data-stu-id="856eb-112">**Unexpected failure**.</span></span> <span data-ttu-id="856eb-113">Comme son nom l’indique, une erreur inattendue est une erreur que vous  n’attendiez pas selon les circonstances.</span><span class="sxs-lookup"><span data-stu-id="856eb-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="856eb-114">Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit disponible pour répondre à l’appel ; Toutefois, lorsque Lync Server 2013 tente d’acheminer votre appel vers la messagerie vocale, l’appel échoue car la connectivité à la messagerie unifiée Exchange a été perdue.</span><span class="sxs-lookup"><span data-stu-id="856eb-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="856eb-115">Il s’agit d’une erreur inattendue : car vous vous attendiez à ce que les appels soient toujours dirigés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="856eb-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="856eb-116">En règle générale, les échecs inattendus sont de vrais échecs : ce sont des problèmes auxquels il n’est pas possible de remédier en formant les utilisateurs ou à l’aide de mesures similaires.</span><span class="sxs-lookup"><span data-stu-id="856eb-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="856eb-p104">Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions. Par exemple, l’illustration précédente indique les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="856eb-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="856eb-119">Réussites</span><span class="sxs-lookup"><span data-stu-id="856eb-119">Successes</span></span></th>
<th><span data-ttu-id="856eb-120">Échecs attendus</span><span class="sxs-lookup"><span data-stu-id="856eb-120">Expected failures</span></span></th>
<th><span data-ttu-id="856eb-121">Échecs inattendus</span><span class="sxs-lookup"><span data-stu-id="856eb-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="856eb-122">Total des sessions</span><span class="sxs-lookup"><span data-stu-id="856eb-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="856eb-123">2024</span><span class="sxs-lookup"><span data-stu-id="856eb-123">2024</span></span></p></td>
<td><p><span data-ttu-id="856eb-124">469</span><span class="sxs-lookup"><span data-stu-id="856eb-124">469</span></span></p></td>
<td><p><span data-ttu-id="856eb-125">16 </span><span class="sxs-lookup"><span data-stu-id="856eb-125">16</span></span></p></td>
<td><p><span data-ttu-id="856eb-126">2521</span><span class="sxs-lookup"><span data-stu-id="856eb-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="856eb-127">Si vous additionnez 2024 + 469 + 16 vous obtenez un total de 2 509 sessions alors que la colonne du total des sessions indique 2 521 sessions.</span><span class="sxs-lookup"><span data-stu-id="856eb-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="856eb-128">Les 12 sessions « manquantes » sont des sessions que le système n’est pas parvenu à classer comme des succès ou des échecs.</span><span class="sxs-lookup"><span data-stu-id="856eb-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="856eb-129">C’est parfois le cas lorsqu’un produit tiers introduit un nouveau code de diagnostic qui n’est pas familier à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="856eb-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="856eb-130">Lorsque cela arrive, les appels effectués à l’aide de ce produit, et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.</span><span class="sxs-lookup"><span data-stu-id="856eb-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="856eb-131">Accès au rapport de diagnostic des activités d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="856eb-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="856eb-132">Le rapport de diagnostic des activités d’égal à égal est accessible à partir de la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="856eb-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="856eb-133">Vous pouvez accéder au [rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="856eb-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="856eb-134">Volume d’échecs inattendus</span><span class="sxs-lookup"><span data-stu-id="856eb-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="856eb-135">Volume d’échecs attendus</span><span class="sxs-lookup"><span data-stu-id="856eb-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="856eb-136">Utilisation optimale du rapport de diagnostic des activités d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="856eb-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="856eb-p107">Il existe plusieurs manières de filtrer le rapport de diagnostic des activités d’égal à égal mais, par défaut, les options de filtrage sont masquées. Pour les afficher, cliquez sur le bouton Afficher/Masquer les paramètres dans le coin supérieur droit de la fenêtre des rapports. Les options de filtrage s’affichent alors.</span><span class="sxs-lookup"><span data-stu-id="856eb-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="856eb-140">Filtres</span><span class="sxs-lookup"><span data-stu-id="856eb-140">Filters</span></span>

<span data-ttu-id="856eb-p108">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de diagnostic des activités d’égal à égal vous permet de filtrer selon des éléments précis, tels que la modalité de session (à savoir messagerie instantanée, transfert de fichiers ou partage d’application). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="856eb-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="856eb-145">Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic des activités d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="856eb-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="856eb-146">Filtres du rapport de diagnostic des activités d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="856eb-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="856eb-147">Nom</span><span class="sxs-lookup"><span data-stu-id="856eb-147">Name</span></span></th>
<th><span data-ttu-id="856eb-148">Description</span><span class="sxs-lookup"><span data-stu-id="856eb-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="856eb-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-p109">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="856eb-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="856eb-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="856eb-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="856eb-p110">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="856eb-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="856eb-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="856eb-155">7/7/2012</span></span></p>
<p><span data-ttu-id="856eb-156">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="856eb-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="856eb-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="856eb-157">7/3/2012</span></span></p>
<p><span data-ttu-id="856eb-158">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="856eb-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856eb-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-p111">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="856eb-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="856eb-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="856eb-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="856eb-p112">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="856eb-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="856eb-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="856eb-165">7/7/2012</span></span></p>
<p><span data-ttu-id="856eb-166">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="856eb-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="856eb-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="856eb-167">7/3/2012</span></span></p>
<p><span data-ttu-id="856eb-168">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="856eb-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856eb-169"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-p113">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="856eb-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="856eb-172">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="856eb-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="856eb-173">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="856eb-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="856eb-174">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="856eb-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="856eb-175">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="856eb-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="856eb-p114">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="856eb-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856eb-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-p115">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez soit sélectionner un pool individuel soit cliquer sur <strong>[Tous]</strong> pour afficher les données pour tous les pools. La liste déroulante est automatiquement renseignée en fonction des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="856eb-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856eb-182"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-p116">Indique le type d’activité de communication qui a eu lieu. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="856eb-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="856eb-185">Tous les</span><span class="sxs-lookup"><span data-stu-id="856eb-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="856eb-186">Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="856eb-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="856eb-187">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="856eb-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="856eb-188">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="856eb-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="856eb-189">Audio</span><span class="sxs-lookup"><span data-stu-id="856eb-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="856eb-190">Vidéo</span><span class="sxs-lookup"><span data-stu-id="856eb-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="856eb-191">Mesures (par modalité)</span><span class="sxs-lookup"><span data-stu-id="856eb-191">Metrics (per modality)</span></span>

<span data-ttu-id="856eb-192">Le tableau suivant dresse la liste des informations fournies dans le rapport de diagnostic des activités d’égal à égal pour chaque modalité.</span><span class="sxs-lookup"><span data-stu-id="856eb-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="856eb-193">Mesures (par modalité)</span><span class="sxs-lookup"><span data-stu-id="856eb-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="856eb-194">Nom</span><span class="sxs-lookup"><span data-stu-id="856eb-194">Name</span></span></th>
<th><span data-ttu-id="856eb-195">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="856eb-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="856eb-196">Description</span><span class="sxs-lookup"><span data-stu-id="856eb-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="856eb-197"><strong>Volume d’opération réussie</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-198">Non</span><span class="sxs-lookup"><span data-stu-id="856eb-198">No</span></span></p></td>
<td><p><span data-ttu-id="856eb-199">Nombre total des sessions d’égal à égal réussies.</span><span class="sxs-lookup"><span data-stu-id="856eb-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856eb-200"><strong>Pourcentage d’opération réussie</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-201">Non</span><span class="sxs-lookup"><span data-stu-id="856eb-201">No</span></span></p></td>
<td><p><span data-ttu-id="856eb-p117">Pourcentage des sessions d’égal à égal qui se sont terminées avec des problèmes importants. Calculé en divisant le volume des opérations réussies par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="856eb-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856eb-204"><strong>Volume d’échec attendu</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-205">Non</span><span class="sxs-lookup"><span data-stu-id="856eb-205">No</span></span></p></td>
<td><p><span data-ttu-id="856eb-206">Nombre total de sessions où une &quot;défaillance&quot; attendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="856eb-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="856eb-p118">Un échec attendu est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent.</span><span class="sxs-lookup"><span data-stu-id="856eb-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856eb-209"><strong>Pourcentage d’échec attendu</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-210">Non</span><span class="sxs-lookup"><span data-stu-id="856eb-210">No</span></span></p></td>
<td><p><span data-ttu-id="856eb-p119">Pourcentage de sessions d’égal à égal lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="856eb-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856eb-213"><strong>Volume d’échec inattendu</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-214">Non</span><span class="sxs-lookup"><span data-stu-id="856eb-214">No</span></span></p></td>
<td><p><span data-ttu-id="856eb-215">Nombre total de sessions où une &quot;défaillance&quot; inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="856eb-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="856eb-p120">Un échec inattendu se produit dans un système sain. Par exemple, un appel ne doit pas se terminer si l’appelant l’a mis en attente. Le cas échéant, cela serait marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="856eb-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856eb-219"><strong>Pourcentage d’échec inattendu</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-220">Non</span><span class="sxs-lookup"><span data-stu-id="856eb-220">No</span></span></p></td>
<td><p><span data-ttu-id="856eb-p121">Pourcentage de sessions d’égal à égal lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="856eb-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856eb-223"><strong>Nombre total de sessions</strong></span><span class="sxs-lookup"><span data-stu-id="856eb-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="856eb-224">Non</span><span class="sxs-lookup"><span data-stu-id="856eb-224">No</span></span></p></td>
<td><p><span data-ttu-id="856eb-225">Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</span><span class="sxs-lookup"><span data-stu-id="856eb-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

