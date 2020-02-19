---
title: 'Lync Server 2013 : rapport de répartition des défaillances'
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
ms.openlocfilehash: 73f7b590732b1b6f2c5010382c7c8f61038d756b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="1f1d7-102">Rapport de répartition des défaillances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1d7-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f1d7-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1f1d7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1f1d7-104">Le rapport de répartition des défaillances classe les sessions ayant échoué selon les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="1f1d7-105">Principales raisons de diagnostic</span><span class="sxs-lookup"><span data-stu-id="1f1d7-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="1f1d7-106">Modalités principales</span><span class="sxs-lookup"><span data-stu-id="1f1d7-106">Top modalities</span></span>

  - <span data-ttu-id="1f1d7-107">Pools principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-107">Top pools</span></span>

  - <span data-ttu-id="1f1d7-108">Principales sources</span><span class="sxs-lookup"><span data-stu-id="1f1d7-108">Top sources</span></span>

  - <span data-ttu-id="1f1d7-109">Composants principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-109">Top components</span></span>

  - <span data-ttu-id="1f1d7-110">Utilisateurs principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-110">Top from users</span></span>

  - <span data-ttu-id="1f1d7-111">Principaux pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1f1d7-111">Top to users</span></span>

  - <span data-ttu-id="1f1d7-112">Principaux des agents utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1f1d7-112">Top from user agents</span></span>

<span data-ttu-id="1f1d7-113">Vous pouvez utiliser ces catégories pour déterminer exactement où un problème se produit et, dans certains cas, pourquoi le problème se produit.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-113">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring.</span></span> <span data-ttu-id="1f1d7-114">Par exemple, supposons que vous avez enregistré 242 sessions audio/vidéo ayant échoué au cours d’une journée donnée.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-114">For example, suppose you recorded 242 failed audio/video sessions during a given day.</span></span> <span data-ttu-id="1f1d7-115">Si vous examinez le rapport de répartition des défaillances, il peut indiquer que 237 de ces échecs de session ont eu lieu dans votre pool Dublin.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-115">If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool.</span></span> <span data-ttu-id="1f1d7-116">Cela vous permet de commencer quand il s’agit d’effectuer un suivi et de diagnostiquer les causes de ces échecs.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-116">That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures.</span></span> <span data-ttu-id="1f1d7-117">Si vous cliquez sur le pool Dublin sous la catégorie **Pools supérieur** , un rapport de répartition des défaillances s’affiche uniquement pour ce pool.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-117">If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool.</span></span> <span data-ttu-id="1f1d7-118">Vous pouvez ensuite commencer à analyser la raison pour laquelle le pool de Dublin rencontrait tellement de difficultés.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-118">You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="1f1d7-119">Affichage du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="1f1d7-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="1f1d7-120">Vous pouvez accéder au rapport de répartition des défaillances à partir de l’un des rapports suivants en cliquant sur le **volume d’échec attendu** ou la mesure de **volume d’échec inattendu** :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="1f1d7-121">Rapport des principales défaillances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1d7-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="1f1d7-122">Rapport de diagnostic de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1d7-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="1f1d7-123">Rapport de diagnostic des activités d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1d7-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="1f1d7-124">Dans le rapport de répartition des défaillances, vous pouvez cliquer sur l’une des mesures suivantes pour afficher le [rapport de liste des échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="1f1d7-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="1f1d7-125">Motifs de diagnostic principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1f1d7-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="1f1d7-126">Modalités principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="1f1d7-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="1f1d7-127">Pools principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1f1d7-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="1f1d7-128">Sources principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="1f1d7-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="1f1d7-129">Composants principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1f1d7-129">Top components (sessions)</span></span>

  - <span data-ttu-id="1f1d7-130">Utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1f1d7-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="1f1d7-131">Utilisateurs destinataires principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1f1d7-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="1f1d7-132">Agents utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1f1d7-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="1f1d7-133">Utilisation du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="1f1d7-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="1f1d7-134">En fonction de la taille de votre moniteur et de la résolution de l’écran, il est possible que certaines données affichées dans le rapport de répartition des défaillances soient tronquées lors de l’affichage à l’écran.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-134">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen.</span></span> <span data-ttu-id="1f1d7-135">Cela est particulièrement vrai pour les mesures telles que les agents utilisateur, qui peuvent avoir des étiquettes très longues.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-135">This is especially true for metrics such as user agents, which can have very long labels.</span></span> <span data-ttu-id="1f1d7-136">Par exemple, un agent utilisateur dont le nom est « UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) » peut seulement partiellement apparaître à l’écran :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-136">For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="1f1d7-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft EP...</span><span class="sxs-lookup"><span data-stu-id="1f1d7-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="1f1d7-138">Heureusement, vous pouvez voir l’intégralité de l’étiquette en maintenant votre souris au-dessus de la valeur tronquée.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="1f1d7-139">L’ID de diagnostic est une mesure intéressante que vous pouvez filtrer à l’aide du rapport de répartition des défaillances.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-139">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID.</span></span> <span data-ttu-id="1f1d7-140">Si vous voyez le même ID de diagnostic découpé dans d’autres rapports, vous pouvez filtrer cet ID dans le rapport de répartition des défaillances et obtenir un aperçu très détaillé de l’emplacement exact, et de la fréquence à laquelle cet ID a été signalé pendant une session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-140">If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1f1d7-141">Filtres</span><span class="sxs-lookup"><span data-stu-id="1f1d7-141">Filters</span></span>

<span data-ttu-id="1f1d7-142">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-142">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="1f1d7-143">Par exemple, le rapport de distribution en échec vous permet de filtrer des éléments tels que le type d’activité (session P2P ou session de conférence) ou par l’ID de diagnostic qui accompagnait chaque session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-143">For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="1f1d7-144">Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de répartition des défaillances.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="1f1d7-145">Filtres du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="1f1d7-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-146">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-146">Name</span></span></th>
<th><span data-ttu-id="1f1d7-147">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-p105">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1f1d7-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1f1d7-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1f1d7-p106">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1f1d7-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1f1d7-154">7/7/2012</span></span></p>
<p><span data-ttu-id="1f1d7-155">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1f1d7-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1f1d7-156">7/3/2012</span></span></p>
<p><span data-ttu-id="1f1d7-157">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-p107">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1f1d7-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1f1d7-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1f1d7-p108">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1f1d7-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1f1d7-164">7/7/2012</span></span></p>
<p><span data-ttu-id="1f1d7-165">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1f1d7-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1f1d7-166">7/3/2012</span></span></p>
<p><span data-ttu-id="1f1d7-167">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-p109">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-172"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-173">Type d’activité à filtrer.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-173">Type of activity to filter on.</span></span> <span data-ttu-id="1f1d7-174">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f1d7-175">Tous les</span><span class="sxs-lookup"><span data-stu-id="1f1d7-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="1f1d7-176">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="1f1d7-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="1f1d7-177">Salle</span><span class="sxs-lookup"><span data-stu-id="1f1d7-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-178"><strong>Catégorie de session</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-p111">Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f1d7-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f1d7-181">Tous les</span><span class="sxs-lookup"><span data-stu-id="1f1d7-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="1f1d7-182">Opération réussie</span><span class="sxs-lookup"><span data-stu-id="1f1d7-182">Success</span></span></p></li>
<li><p><span data-ttu-id="1f1d7-183">Échec attendu</span><span class="sxs-lookup"><span data-stu-id="1f1d7-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="1f1d7-184">Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="1f1d7-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="1f1d7-185">Un &quot;échec&quot; attendu est un échec qui est attendu.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="1f1d7-186">Par exemple, si un utilisateur a défini son statut en Ne pas déranger, vous attendez que tout appel à cette personne échoue.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="1f1d7-187">Un &quot;échec&quot; inattendu est un échec qui se produit dans le cas d’un système sain.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="1f1d7-188">Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="1f1d7-189">Si cela se produit, l’incident est marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-190"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-p113">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="1f1d7-193">Mesures pour les principaux motifs de diagnostic</span><span class="sxs-lookup"><span data-stu-id="1f1d7-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="1f1d7-194">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base de l’ID de diagnostic le plus fréquemment signalé.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="1f1d7-195">Mesures pour les principaux motifs de diagnostic</span><span class="sxs-lookup"><span data-stu-id="1f1d7-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-196">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-196">Name</span></span></th>
<th><span data-ttu-id="1f1d7-197">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f1d7-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f1d7-198">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-199"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-200">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-200">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-201">Classement relatif des sessions ayant échoué sur la base des ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-201">Relative ranking of failed sessions based on diagnostic IDs.</span></span> <span data-ttu-id="1f1d7-202">L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête MS-Diagnostics) joint à un message SIP qui fournit souvent des informations utiles pour résoudre les erreurs.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-202">The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-203"><strong>Principales raisons de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-204">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-204">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-205">ID de diagnostic généré dans une session.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-206"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-207">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-207">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-208">Nombre total de sessions ayant échoué où l’ID de diagnostic spécifié a été généré.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="1f1d7-209">Mesures pour les modalités principales</span><span class="sxs-lookup"><span data-stu-id="1f1d7-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="1f1d7-210">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des modalités de session ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="1f1d7-211">Mesures pour les modalités principales</span><span class="sxs-lookup"><span data-stu-id="1f1d7-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-212">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-212">Name</span></span></th>
<th><span data-ttu-id="1f1d7-213">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f1d7-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f1d7-214">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-215"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-216">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-216">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-217">Classement relatif en fonction de l’échec d’une session en fonction du type de session (par exemple, une conférence audio/vidéo ou une session de transfert de fichiers P2P).</span><span class="sxs-lookup"><span data-stu-id="1f1d7-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-218"><strong>Modalités principales</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-219">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-219">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-220">Type de session.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-221"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-222">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-222">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-223">Nombre total de sessions ayant échoué impliquant la modalité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="1f1d7-224">Mesures pour les pools principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-224">Metrics for Top Pools</span></span>

<span data-ttu-id="1f1d7-225">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des pools ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="1f1d7-226">Mesures pour les pools principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-227">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-227">Name</span></span></th>
<th><span data-ttu-id="1f1d7-228">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f1d7-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f1d7-229">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-230"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-231">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-231">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-232">Classement relatif des sessions ayant échoué sur la base du pool de serveurs d’inscriptions ou du serveur Edge sur lequel la session a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-233"><strong>Pools principaux</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-234">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-234">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-235">Nom du pool de serveurs d’inscriptions ou du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-236"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-237">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-237">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-238">Nombre total de sessions ayant échoué par pool de serveurs d’inscriptions ou serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="1f1d7-239">Mesures pour les principales sources</span><span class="sxs-lookup"><span data-stu-id="1f1d7-239">Metrics for Top Sources</span></span>

<span data-ttu-id="1f1d7-240">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des ordinateurs ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="1f1d7-241">Mesures pour les principales sources</span><span class="sxs-lookup"><span data-stu-id="1f1d7-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-242">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-242">Name</span></span></th>
<th><span data-ttu-id="1f1d7-243">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f1d7-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f1d7-244">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-245"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-246">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-246">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-247">Classement relatif des sessions ayant échoué par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-248"><strong>Principales sources</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-249">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-249">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-250">Nom de l’ordinateur impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-251"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-252">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-252">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-253">Nombre total de sessions ayant échoué par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="1f1d7-254">Mesures pour les composants principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-254">Metrics for Top Components</span></span>

<span data-ttu-id="1f1d7-255">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances basé sur les composants Microsoft Lync Server 2010 ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="1f1d7-256">Mesures pour les composants principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-257">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-257">Name</span></span></th>
<th><span data-ttu-id="1f1d7-258">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f1d7-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f1d7-259">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-260"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-261">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-261">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-262">Classement relatif des sessions ayant échoué sur la base du composant Lync Server 2010 (par exemple, ExumRouting, GroupChat ou MediationServer).</span><span class="sxs-lookup"><span data-stu-id="1f1d7-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-263"><strong>Composants principaux</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-264">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-264">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-265">Nom du composant impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-266"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-267">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-267">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-268">Nombre total de sessions ayant échoué par composant.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="1f1d7-269">Mesures pour les utilisateurs principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-269">Metrics for Top From Users</span></span>

<span data-ttu-id="1f1d7-270">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant rencontré le plus d’échecs lorsqu’ils essaient d’appeler quelqu’un d’autre (appelé « depuis »).</span><span class="sxs-lookup"><span data-stu-id="1f1d7-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="1f1d7-271">Mesures pour les utilisateurs principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-272">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-272">Name</span></span></th>
<th><span data-ttu-id="1f1d7-273">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f1d7-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f1d7-274">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-275"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-276">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-276">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-277">Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a été invité à rejoindre la session.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-278"><strong>Utilisateurs principaux</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-279">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-279">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-280">Adresse SIP de l’utilisateur invité à rejoindre la session.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-281"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-282">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-282">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-283">Nombre total de sessions ayant échoué par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="1f1d7-284">Mesures pour les utilisateurs principaux</span><span class="sxs-lookup"><span data-stu-id="1f1d7-284">Metrics for Top To Users</span></span>

<span data-ttu-id="1f1d7-285">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant rencontré le plus d’échecs lorsqu’un autre utilisateur a essayé de les appeler (appelés utilisateurs « à »).</span><span class="sxs-lookup"><span data-stu-id="1f1d7-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-286">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-286">Name</span></span></th>
<th><span data-ttu-id="1f1d7-287">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f1d7-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f1d7-288">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-289"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-290">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-290">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-291">Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-292"><strong>Principaux pour les utilisateurs</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-293">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-293">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-294">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-295"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-296">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-296">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-297">Nombre total de sessions ayant échoué par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="1f1d7-298">Mesures pour les principaux agents utilisateur</span><span class="sxs-lookup"><span data-stu-id="1f1d7-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="1f1d7-299">Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base du logiciel de point de terminaison ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="1f1d7-300">Mesures pour les principaux agents utilisateur</span><span class="sxs-lookup"><span data-stu-id="1f1d7-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1d7-301">Nom</span><span class="sxs-lookup"><span data-stu-id="1f1d7-301">Name</span></span></th>
<th><span data-ttu-id="1f1d7-302">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f1d7-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f1d7-303">Description</span><span class="sxs-lookup"><span data-stu-id="1f1d7-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-304"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-305">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-305">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-306">Classement relatif des sessions ayant échoué sur la base de l’agent utilisateur (logiciel) impliqué dans la session.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-306">Relative ranking of failed sessions based on the user agent (software) involved in the session.</span></span> <span data-ttu-id="1f1d7-307">Par exemple : RTCC/4.0.0.0/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-307">For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1d7-308"><strong>Principaux agents utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-309">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-309">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-310">Nom de l’agent utilisateur impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1d7-311"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1f1d7-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1f1d7-312">Non</span><span class="sxs-lookup"><span data-stu-id="1f1d7-312">No</span></span></p></td>
<td><p><span data-ttu-id="1f1d7-313">Nombre total de sessions ayant échoué par agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1f1d7-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

