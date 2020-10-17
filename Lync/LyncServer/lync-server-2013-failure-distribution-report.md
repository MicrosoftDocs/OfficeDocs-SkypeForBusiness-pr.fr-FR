---
title: 'Lync Server 2013 : rapport de répartition des défaillances'
description: 'Lync Server 2013 : rapport de répartition des défaillances.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5a87f779f87d6b7002fa108f1969c33739eed9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564730"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="c3fcd-103">Rapport de répartition des défaillances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3fcd-103">Failure Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3fcd-104">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c3fcd-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c3fcd-105">Le rapport de répartition des défaillances classe les sessions ayant échoué selon les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="c3fcd-106">Principales raisons de diagnostic</span><span class="sxs-lookup"><span data-stu-id="c3fcd-106">Top diagnostic reasons</span></span>

  - <span data-ttu-id="c3fcd-107">Modalités principales</span><span class="sxs-lookup"><span data-stu-id="c3fcd-107">Top modalities</span></span>

  - <span data-ttu-id="c3fcd-108">Pools principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-108">Top pools</span></span>

  - <span data-ttu-id="c3fcd-109">Principales sources</span><span class="sxs-lookup"><span data-stu-id="c3fcd-109">Top sources</span></span>

  - <span data-ttu-id="c3fcd-110">Composants principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-110">Top components</span></span>

  - <span data-ttu-id="c3fcd-111">Utilisateurs principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-111">Top from users</span></span>

  - <span data-ttu-id="c3fcd-112">Principaux pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c3fcd-112">Top to users</span></span>

  - <span data-ttu-id="c3fcd-113">Principaux des agents utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c3fcd-113">Top from user agents</span></span>

<span data-ttu-id="c3fcd-114">Vous pouvez utiliser ces catégories pour déterminer exactement où un problème se produit et, dans certains cas, pourquoi le problème se produit.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-114">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring.</span></span> <span data-ttu-id="c3fcd-115">Par exemple, supposons que vous avez enregistré 242 sessions audio/vidéo ayant échoué au cours d’une journée donnée.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-115">For example, suppose you recorded 242 failed audio/video sessions during a given day.</span></span> <span data-ttu-id="c3fcd-116">Si vous examinez le rapport de répartition des défaillances, il peut indiquer que 237 de ces échecs de session ont eu lieu dans votre pool Dublin.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-116">If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool.</span></span> <span data-ttu-id="c3fcd-117">Cela vous permet de commencer quand il s’agit d’effectuer un suivi et de diagnostiquer les causes de ces échecs.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-117">That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures.</span></span> <span data-ttu-id="c3fcd-118">Si vous cliquez sur le pool Dublin sous la catégorie **Pools supérieur** , un rapport de répartition des défaillances s’affiche uniquement pour ce pool.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-118">If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool.</span></span> <span data-ttu-id="c3fcd-119">Vous pouvez ensuite commencer à analyser la raison pour laquelle le pool de Dublin rencontrait tellement de difficultés.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-119">You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="c3fcd-120">Affichage du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="c3fcd-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="c3fcd-121">Vous pouvez accéder au rapport de répartition des défaillances à partir de l’un des rapports suivants en cliquant sur le **volume d’échec attendu** ou la mesure de **volume d’échec inattendu** :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="c3fcd-122">Rapport des principales défaillances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3fcd-122">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="c3fcd-123">Rapport de diagnostic de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3fcd-123">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="c3fcd-124">Rapport de diagnostic des activités d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3fcd-124">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="c3fcd-125">Dans le rapport de répartition des défaillances, vous pouvez cliquer sur l’une des mesures suivantes pour afficher le [rapport de liste des échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="c3fcd-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="c3fcd-126">Motifs de diagnostic principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="c3fcd-126">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="c3fcd-127">Modalités principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="c3fcd-127">Top modalities (sessions)</span></span>

  - <span data-ttu-id="c3fcd-128">Pools principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="c3fcd-128">Top pools (sessions)</span></span>

  - <span data-ttu-id="c3fcd-129">Sources principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="c3fcd-129">Top sources (sessions)</span></span>

  - <span data-ttu-id="c3fcd-130">Composants principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="c3fcd-130">Top components (sessions)</span></span>

  - <span data-ttu-id="c3fcd-131">Utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="c3fcd-131">Top from users (sessions)</span></span>

  - <span data-ttu-id="c3fcd-132">Utilisateurs destinataires principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="c3fcd-132">Top to users (sessions)</span></span>

  - <span data-ttu-id="c3fcd-133">Agents utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="c3fcd-133">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="c3fcd-134">Utilisation du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="c3fcd-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="c3fcd-135">En fonction de la taille de votre moniteur et de la résolution de l’écran, il est possible que certaines données affichées dans le rapport de répartition des défaillances soient tronquées lors de l’affichage à l’écran.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-135">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen.</span></span> <span data-ttu-id="c3fcd-136">Cela est particulièrement vrai pour les mesures telles que les agents utilisateur, qui peuvent avoir des étiquettes très longues.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-136">This is especially true for metrics such as user agents, which can have very long labels.</span></span> <span data-ttu-id="c3fcd-137">Par exemple, un agent utilisateur dont le nom est « UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) » peut seulement partiellement apparaître à l’écran :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-137">For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="c3fcd-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft EP...</span><span class="sxs-lookup"><span data-stu-id="c3fcd-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="c3fcd-139">Heureusement, vous pouvez voir l’intégralité de l’étiquette en maintenant votre souris au-dessus de la valeur tronquée.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="c3fcd-140">L’ID de diagnostic est une mesure intéressante que vous pouvez filtrer à l’aide du rapport de répartition des défaillances.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-140">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID.</span></span> <span data-ttu-id="c3fcd-141">Si vous voyez le même ID de diagnostic découpé dans d’autres rapports, vous pouvez filtrer cet ID dans le rapport de répartition des défaillances et obtenir un aperçu très détaillé de l’emplacement exact, et de la fréquence à laquelle cet ID a été signalé pendant une session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-141">If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c3fcd-142">Filtres</span><span class="sxs-lookup"><span data-stu-id="c3fcd-142">Filters</span></span>

<span data-ttu-id="c3fcd-143">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-143">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="c3fcd-144">Par exemple, le rapport de distribution en échec vous permet de filtrer des éléments tels que le type d’activité (session P2P ou session de conférence) ou par l’ID de diagnostic qui accompagnait chaque session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-144">For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="c3fcd-145">Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de répartition des défaillances.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="c3fcd-146">Filtres du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="c3fcd-146">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-147">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-147">Name</span></span></th>
<th><span data-ttu-id="c3fcd-148">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-p105">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c3fcd-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c3fcd-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c3fcd-p106">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c3fcd-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c3fcd-155">7/7/2012</span></span></p>
<p><span data-ttu-id="c3fcd-156">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c3fcd-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c3fcd-157">7/3/2012</span></span></p>
<p><span data-ttu-id="c3fcd-158">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-p107">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c3fcd-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c3fcd-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c3fcd-p108">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c3fcd-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c3fcd-165">7/7/2012</span></span></p>
<p><span data-ttu-id="c3fcd-166">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c3fcd-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c3fcd-167">7/3/2012</span></span></p>
<p><span data-ttu-id="c3fcd-168">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-169"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-169"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-p109">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-173"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-173"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-174">Type d’activité à filtrer.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-174">Type of activity to filter on.</span></span> <span data-ttu-id="c3fcd-175">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-175">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3fcd-176">Tous les</span><span class="sxs-lookup"><span data-stu-id="c3fcd-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="c3fcd-177">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="c3fcd-177">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="c3fcd-178">Conférence</span><span class="sxs-lookup"><span data-stu-id="c3fcd-178">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-179"><strong>Catégorie de session</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-179"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-p111">Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3fcd-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3fcd-182">Tous les</span><span class="sxs-lookup"><span data-stu-id="c3fcd-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="c3fcd-183">Opération réussie</span><span class="sxs-lookup"><span data-stu-id="c3fcd-183">Success</span></span></p></li>
<li><p><span data-ttu-id="c3fcd-184">Échec attendu</span><span class="sxs-lookup"><span data-stu-id="c3fcd-184">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="c3fcd-185">Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="c3fcd-185">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="c3fcd-186">Un &quot; échec attendu &quot; est un échec qui est attendu.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-186">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="c3fcd-187">Par exemple, si un utilisateur a défini son statut en Ne pas déranger, vous attendez que tout appel à cette personne échoue.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-187">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="c3fcd-188">Un &quot; échec inattendu &quot; est un échec qui se produit dans le cas d’un système sain.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-188">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="c3fcd-189">Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-189">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="c3fcd-190">Si cela se produit, l’incident est marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-190">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-191"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-p113">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="c3fcd-194">Mesures pour les principaux motifs de diagnostic</span><span class="sxs-lookup"><span data-stu-id="c3fcd-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="c3fcd-195">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base de l’ID de diagnostic le plus fréquemment signalé.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="c3fcd-196">Mesures pour les principaux motifs de diagnostic</span><span class="sxs-lookup"><span data-stu-id="c3fcd-196">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-197">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-197">Name</span></span></th>
<th><span data-ttu-id="c3fcd-198">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c3fcd-198">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3fcd-199">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-200"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-200"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-201">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-201">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-202">Classement relatif des sessions ayant échoué sur la base des ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-202">Relative ranking of failed sessions based on diagnostic IDs.</span></span> <span data-ttu-id="c3fcd-203">L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête MS-Diagnostics) joint à un message SIP qui fournit souvent des informations utiles pour résoudre les erreurs.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-203">The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-204"><strong>Principales raisons de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-204"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-205">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-205">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-206">ID de diagnostic généré dans une session.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-206">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-207"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-207"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-208">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-208">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-209">Nombre total de sessions ayant échoué où l’ID de diagnostic spécifié a été généré.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="c3fcd-210">Mesures pour les modalités principales</span><span class="sxs-lookup"><span data-stu-id="c3fcd-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="c3fcd-211">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des modalités de session ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="c3fcd-212">Mesures pour les modalités principales</span><span class="sxs-lookup"><span data-stu-id="c3fcd-212">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-213">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-213">Name</span></span></th>
<th><span data-ttu-id="c3fcd-214">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c3fcd-214">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3fcd-215">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-216"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-216"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-217">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-217">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-218">Classement relatif en fonction de l’échec d’une session en fonction du type de session (par exemple, une conférence audio/vidéo ou une session de transfert de fichiers P2P).</span><span class="sxs-lookup"><span data-stu-id="c3fcd-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-219"><strong>Modalités principales</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-219"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-220">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-220">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-221">Type de session.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-221">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-222"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-222"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-223">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-223">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-224">Nombre total de sessions ayant échoué impliquant la modalité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-224">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="c3fcd-225">Mesures pour les pools principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-225">Metrics for Top Pools</span></span>

<span data-ttu-id="c3fcd-226">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des pools ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="c3fcd-227">Mesures pour les pools principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-227">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-228">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-228">Name</span></span></th>
<th><span data-ttu-id="c3fcd-229">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c3fcd-229">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3fcd-230">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-230">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-231"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-231"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-232">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-232">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-233">Classement relatif des sessions ayant échoué sur la base du pool de serveurs d’inscriptions ou du serveur Edge sur lequel la session a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-234"><strong>Pools principaux</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-234"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-235">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-235">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-236">Nom du pool de serveurs d’inscriptions ou du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-236">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-237"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-237"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-238">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-238">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-239">Nombre total de sessions ayant échoué par pool de serveurs d’inscriptions ou serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="c3fcd-240">Mesures pour les principales sources</span><span class="sxs-lookup"><span data-stu-id="c3fcd-240">Metrics for Top Sources</span></span>

<span data-ttu-id="c3fcd-241">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des ordinateurs ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="c3fcd-242">Mesures pour les principales sources</span><span class="sxs-lookup"><span data-stu-id="c3fcd-242">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-243">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-243">Name</span></span></th>
<th><span data-ttu-id="c3fcd-244">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c3fcd-244">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3fcd-245">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-245">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-246"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-246"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-247">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-247">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-248">Classement relatif des sessions ayant échoué par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-248">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-249"><strong>Principales sources</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-249"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-250">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-250">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-251">Nom de l’ordinateur impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-251">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-252"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-252"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-253">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-253">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-254">Nombre total de sessions ayant échoué par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-254">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="c3fcd-255">Mesures pour les composants principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-255">Metrics for Top Components</span></span>

<span data-ttu-id="c3fcd-256">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances basé sur les composants Microsoft Lync Server 2010 ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-256">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="c3fcd-257">Mesures pour les composants principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-257">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-258">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-258">Name</span></span></th>
<th><span data-ttu-id="c3fcd-259">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c3fcd-259">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3fcd-260">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-260">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-261"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-261"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-262">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-262">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-263">Classement relatif des sessions ayant échoué sur la base du composant Lync Server 2010 (par exemple, ExumRouting, GroupChat ou MediationServer).</span><span class="sxs-lookup"><span data-stu-id="c3fcd-263">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-264"><strong>Composants principaux</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-264"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-265">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-265">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-266">Nom du composant impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-266">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-267"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-267"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-268">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-268">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-269">Nombre total de sessions ayant échoué par composant.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-269">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="c3fcd-270">Mesures pour les utilisateurs principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-270">Metrics for Top From Users</span></span>

<span data-ttu-id="c3fcd-271">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant rencontré le plus d’échecs lorsqu’ils essaient d’appeler quelqu’un d’autre (appelé « depuis »).</span><span class="sxs-lookup"><span data-stu-id="c3fcd-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="c3fcd-272">Mesures pour les utilisateurs principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-272">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-273">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-273">Name</span></span></th>
<th><span data-ttu-id="c3fcd-274">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c3fcd-274">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3fcd-275">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-276"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-276"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-277">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-277">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-278">Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a été invité à rejoindre la session.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-279"><strong>Utilisateurs principaux</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-279"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-280">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-280">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-281">Adresse SIP de l’utilisateur invité à rejoindre la session.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-281">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-282"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-282"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-283">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-283">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-284">Nombre total de sessions ayant échoué par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-284">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="c3fcd-285">Mesures pour les utilisateurs principaux</span><span class="sxs-lookup"><span data-stu-id="c3fcd-285">Metrics for Top To Users</span></span>

<span data-ttu-id="c3fcd-286">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant rencontré le plus d’échecs lorsqu’un autre utilisateur a essayé de les appeler (appelés utilisateurs « à »).</span><span class="sxs-lookup"><span data-stu-id="c3fcd-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-287">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-287">Name</span></span></th>
<th><span data-ttu-id="c3fcd-288">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c3fcd-288">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3fcd-289">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-289">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-290"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-290"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-291">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-291">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-292">Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-293"><strong>Principaux pour les utilisateurs</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-293"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-294">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-294">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-295">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-295">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-296"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-296"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-297">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-297">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-298">Nombre total de sessions ayant échoué par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-298">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="c3fcd-299">Mesures pour les principaux agents utilisateur</span><span class="sxs-lookup"><span data-stu-id="c3fcd-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="c3fcd-300">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base du logiciel de point de terminaison ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="c3fcd-301">Mesures pour les principaux agents utilisateur</span><span class="sxs-lookup"><span data-stu-id="c3fcd-301">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3fcd-302">Nom</span><span class="sxs-lookup"><span data-stu-id="c3fcd-302">Name</span></span></th>
<th><span data-ttu-id="c3fcd-303">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c3fcd-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3fcd-304">Description</span><span class="sxs-lookup"><span data-stu-id="c3fcd-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-305"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-305"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-306">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-306">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-307">Classement relatif des sessions ayant échoué sur la base de l’agent utilisateur (logiciel) impliqué dans la session.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-307">Relative ranking of failed sessions based on the user agent (software) involved in the session.</span></span> <span data-ttu-id="c3fcd-308">Par exemple : RTCC/4.0.0.0/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-308">For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3fcd-309"><strong>Principaux agents utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-309"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-310">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-310">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-311">Nom de l’agent utilisateur impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-311">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3fcd-312"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c3fcd-312"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3fcd-313">Non</span><span class="sxs-lookup"><span data-stu-id="c3fcd-313">No</span></span></p></td>
<td><p><span data-ttu-id="c3fcd-314">Nombre total de sessions ayant échoué par agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3fcd-314">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

