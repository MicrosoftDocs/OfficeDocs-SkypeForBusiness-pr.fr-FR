---
title: 'Rapport de distribution d’échec Lync Server 2013:'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06481be824f6c51975431aeea2efe27e41eadabc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="1ef94-102">Rapport de distribution des échecs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ef94-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ef94-103">_**Dernière modification de la rubrique:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1ef94-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1ef94-104">Le rapport de répartition des défaillances classe les sessions ayant échoué selon les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ef94-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="1ef94-105">Motifs de diagnostic principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="1ef94-106">Modalités principales</span><span class="sxs-lookup"><span data-stu-id="1ef94-106">Top modalities</span></span>

  - <span data-ttu-id="1ef94-107">Pools principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-107">Top pools</span></span>

  - <span data-ttu-id="1ef94-108">Sources principales</span><span class="sxs-lookup"><span data-stu-id="1ef94-108">Top sources</span></span>

  - <span data-ttu-id="1ef94-109">Composants principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-109">Top components</span></span>

  - <span data-ttu-id="1ef94-110">Utilisateurs émetteurs principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-110">Top from users</span></span>

  - <span data-ttu-id="1ef94-111">Utilisateurs destinataires principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-111">Top to users</span></span>

  - <span data-ttu-id="1ef94-112">Agents utilisateurs émetteurs principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-112">Top from user agents</span></span>

<span data-ttu-id="1ef94-p101">Vous pouvez utiliser ces catégories pour rechercher exactement le problème et, dans certains cas, déterminer la raison de ce problème. Par exemple, supposons que vous avez enregistré 242 sessions audio/vidéo ayant échoué au cours d’une journée donnée. Si vous examinez le rapport de répartition des défaillances, il peut indiquer que 237 de ces sessions ont eu lieu dans le pool Dublin. C’est un bon point de départ pour rechercher et diagnostiquer les causes à l’origine de ces défaillances. Si vous cliquez sur le pool Dublin sous la catégorie **Pools principaux**, vous y trouverez un rapport de répartition des défaillances spécifique à ce pool. Vous pouvez ensuite commencer à analyser les raisons qui ont entraîné autant de difficultés dans le pool.</span><span class="sxs-lookup"><span data-stu-id="1ef94-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="1ef94-119">Affichage du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="1ef94-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="1ef94-120">Vous pouvez accéder au rapport de répartition des défaillances à partir de n’importe lequel des rapports suivants en cliquant sur la mesure **Nombre d’échecs attendus** ou **Nombre d’échecs inattendus** :</span><span class="sxs-lookup"><span data-stu-id="1ef94-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="1ef94-121">Rapport sur les principaux échecs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ef94-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="1ef94-122">Rapport de diagnostic de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ef94-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="1ef94-123">Rapport de diagnostic d’activité d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ef94-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="1ef94-124">Dans le rapport de distribution des échecs, vous pouvez cliquer sur l’une des mesures suivantes pour afficher le [rapport de liste d’échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="1ef94-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="1ef94-125">Motifs de diagnostic principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1ef94-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="1ef94-126">Modalités principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="1ef94-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="1ef94-127">Pools principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1ef94-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="1ef94-128">Sources principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="1ef94-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="1ef94-129">Composants principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1ef94-129">Top components (sessions)</span></span>

  - <span data-ttu-id="1ef94-130">Utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1ef94-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="1ef94-131">Utilisateurs destinataires principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1ef94-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="1ef94-132">Agents utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="1ef94-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="1ef94-133">Utilisation du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="1ef94-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="1ef94-p102">Selon la taille de votre moniteur et sa résolution d’écran, il est possible que certaines des données indiquées dans le rapport de répartition des défaillances soient tronquées à l’écran. Cela se vérifie en particulier pour les mesures comme les agents utilisateurs qui ont des libellés très longs. Par exemple, un agent utilisateur dont le nom est « UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) » peut ne s’afficher que partiellement à l’écran :</span><span class="sxs-lookup"><span data-stu-id="1ef94-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="1ef94-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="1ef94-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="1ef94-138">Fort heureusement, vous pouvez voir le libellé en entier en maintenant votre souris au-dessus de la valeur tronquée.</span><span class="sxs-lookup"><span data-stu-id="1ef94-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="1ef94-p103">L’ID de diagnostic est une mesure intéressante sur laquelle vous pouvez filtrer dans le rapport de répartition des défaillances. Si le même ID de diagnostic s’affiche dans d’autres rapports, vous pouvez filtrer sur cet ID dans le rapport de répartition des défaillances et obtenir des informations très détaillées sur l’emplacement exact où a été signalé cet ID pendant une session ayant échoué et sa fréquence.</span><span class="sxs-lookup"><span data-stu-id="1ef94-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1ef94-141">Filtres</span><span class="sxs-lookup"><span data-stu-id="1ef94-141">Filters</span></span>

<span data-ttu-id="1ef94-p104">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de répartition des défaillances vous permet de filtrer sur des critères tels que le type d’activité (session entre homologues ou session de conférence) ou à l’aide de l’ID de diagnostic qui a accompagné chaque session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1ef94-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="1ef94-144">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de répartition des défaillances.</span><span class="sxs-lookup"><span data-stu-id="1ef94-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="1ef94-145">Filtres du rapport de répartition des défaillances</span><span class="sxs-lookup"><span data-stu-id="1ef94-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-146">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-146">Name</span></span></th>
<th><span data-ttu-id="1ef94-147">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-148"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-p105">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="1ef94-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1ef94-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1ef94-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1ef94-p106">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1ef94-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1ef94-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1ef94-154">7/7/2012</span></span></p>
<p><span data-ttu-id="1ef94-155">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1ef94-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1ef94-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1ef94-156">7/3/2012</span></span></p>
<p><span data-ttu-id="1ef94-157">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1ef94-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-158"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-p107">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="1ef94-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1ef94-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1ef94-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1ef94-p108">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1ef94-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1ef94-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1ef94-164">7/7/2012</span></span></p>
<p><span data-ttu-id="1ef94-165">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1ef94-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1ef94-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1ef94-166">7/3/2012</span></span></p>
<p><span data-ttu-id="1ef94-167">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1ef94-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-p109">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="1ef94-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-172"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-p110">Type d’activité sur laquelle filtrer. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ef94-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ef94-175">[Tous]</span><span class="sxs-lookup"><span data-stu-id="1ef94-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="1ef94-176">Égal à égal</span><span class="sxs-lookup"><span data-stu-id="1ef94-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="1ef94-177">Conférence</span><span class="sxs-lookup"><span data-stu-id="1ef94-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-178"><strong>Catégorie de session</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-p111">Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ef94-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ef94-181">[Tous]</span><span class="sxs-lookup"><span data-stu-id="1ef94-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="1ef94-182">Opération réussie</span><span class="sxs-lookup"><span data-stu-id="1ef94-182">Success</span></span></p></li>
<li><p><span data-ttu-id="1ef94-183">Échec attendu</span><span class="sxs-lookup"><span data-stu-id="1ef94-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="1ef94-184">Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="1ef94-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="1ef94-185">Un &quot;échec&quot; attendu est un échec censé se produire.</span><span class="sxs-lookup"><span data-stu-id="1ef94-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="1ef94-186">Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent.</span><span class="sxs-lookup"><span data-stu-id="1ef94-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="1ef94-187">Un &quot;échec&quot; inattendu est une défaillance qui peut se produire dans un système de bon fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="1ef94-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="1ef94-188">Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="1ef94-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="1ef94-189">Si cela se produit, l’incident est marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="1ef94-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-190"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-p113">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.</span><span class="sxs-lookup"><span data-stu-id="1ef94-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="1ef94-193">Mesures pour les motifs de diagnostic principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="1ef94-194">Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base de l’ID de diagnostic le plus fréquemment signalé.</span><span class="sxs-lookup"><span data-stu-id="1ef94-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="1ef94-195">Mesures pour les motifs de diagnostic principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-196">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-196">Name</span></span></th>
<th><span data-ttu-id="1ef94-197">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1ef94-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ef94-198">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-199"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-200">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-200">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-p114">Classement relatif des sessions ayant échoué sur la base des ID de diagnostic. Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles à l’identification et à la résolution des erreurs.</span><span class="sxs-lookup"><span data-stu-id="1ef94-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-203"><strong>Motifs de diagnostic principaux</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-204">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-204">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-205">ID de diagnostic généré dans une session.</span><span class="sxs-lookup"><span data-stu-id="1ef94-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-206"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-207">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-207">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-208">Nombre total de sessions ayant échoué où l’ID de diagnostic spécifié a été généré.</span><span class="sxs-lookup"><span data-stu-id="1ef94-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="1ef94-209">Mesures pour les modalités principales</span><span class="sxs-lookup"><span data-stu-id="1ef94-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="1ef94-210">Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des modalités de session ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1ef94-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="1ef94-211">Mesures pour les modalités principales</span><span class="sxs-lookup"><span data-stu-id="1ef94-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-212">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-212">Name</span></span></th>
<th><span data-ttu-id="1ef94-213">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1ef94-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ef94-214">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-215"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-216">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-216">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-217">Classement relatif des sessions ayant échoué sur la base du type de session (par exemple, une conférence audio/vidéo ou une session de transfert de fichiers entre homologues).</span><span class="sxs-lookup"><span data-stu-id="1ef94-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-218"><strong>Modalités principales</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-219">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-219">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-220">Type de session.</span><span class="sxs-lookup"><span data-stu-id="1ef94-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-221"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-222">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-222">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-223">Nombre total de sessions ayant échoué impliquant la modalité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1ef94-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="1ef94-224">Mesures pour les pools principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-224">Metrics for Top Pools</span></span>

<span data-ttu-id="1ef94-225">Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des pools ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1ef94-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="1ef94-226">Mesures pour les pools principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-227">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-227">Name</span></span></th>
<th><span data-ttu-id="1ef94-228">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1ef94-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ef94-229">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-230"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-231">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-231">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-232">Classement relatif de sessions ayant échoué en fonction du pool d’inscriptions ou du serveur Edge sur lequel la session a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="1ef94-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-233"><strong>Pools principaux</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-234">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-234">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-235">Nom du pool d’inscriptions ou du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="1ef94-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-236"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-237">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-237">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-238">Nombre total de sessions ayant échoué par pool d’inscriptions ou serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="1ef94-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="1ef94-239">Mesures pour les sources principales</span><span class="sxs-lookup"><span data-stu-id="1ef94-239">Metrics for Top Sources</span></span>

<span data-ttu-id="1ef94-240">Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des ordinateurs ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1ef94-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="1ef94-241">Mesures pour les sources principales</span><span class="sxs-lookup"><span data-stu-id="1ef94-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-242">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-242">Name</span></span></th>
<th><span data-ttu-id="1ef94-243">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1ef94-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ef94-244">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-245"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-246">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-246">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-247">Classement relatif des sessions ayant échoué par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1ef94-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-248"><strong>Sources principales</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-249">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-249">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-250">Nom de l’ordinateur impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1ef94-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-251"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-252">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-252">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-253">Nombre total de sessions ayant échoué par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1ef94-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="1ef94-254">Mesures pour les composants principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-254">Metrics for Top Components</span></span>

<span data-ttu-id="1ef94-255">Le tableau suivant répertorie les informations fournies dans le rapport de distribution d’échec basées sur les composants Microsoft Lync Server 2010 ayant rencontré le plus de problèmes.</span><span class="sxs-lookup"><span data-stu-id="1ef94-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="1ef94-256">Mesures pour les composants principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-257">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-257">Name</span></span></th>
<th><span data-ttu-id="1ef94-258">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1ef94-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ef94-259">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-260"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-261">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-261">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-262">Classement relatif de sessions ayant échoué en fonction du composant Lync Server 2010 (par exemple, ExumRouting, GroupChat ou MediationServer).</span><span class="sxs-lookup"><span data-stu-id="1ef94-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-263"><strong>Composants principaux</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-264">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-264">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-265">Nom du composant impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1ef94-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-266"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-267">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-267">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-268">Nombre total de sessions ayant échoué par composant.</span><span class="sxs-lookup"><span data-stu-id="1ef94-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="1ef94-269">Mesures pour les utilisateurs émetteurs principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-269">Metrics for Top From Users</span></span>

<span data-ttu-id="1ef94-270">Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant connu le plus d’échecs en essayant d’appeler quelqu’un d’autre (dénommés utilisateurs « De »).</span><span class="sxs-lookup"><span data-stu-id="1ef94-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="1ef94-271">Mesures pour les utilisateurs émetteurs principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-272">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-272">Name</span></span></th>
<th><span data-ttu-id="1ef94-273">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1ef94-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ef94-274">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-275"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-276">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-276">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-277">Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a été invité à se joindre à la session.</span><span class="sxs-lookup"><span data-stu-id="1ef94-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-278"><strong>Utilisateurs émetteurs principaux</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-279">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-279">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-280">Adresse SIP de l’utilisateur invité à se joindre à la session.</span><span class="sxs-lookup"><span data-stu-id="1ef94-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-281"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-282">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-282">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-283">Nombre total de sessions ayant échoué par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1ef94-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="1ef94-284">Mesures pour les utilisateurs destinataires principaux</span><span class="sxs-lookup"><span data-stu-id="1ef94-284">Metrics for Top To Users</span></span>

<span data-ttu-id="1ef94-285">Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant connu le plus d’échecs après avoir été appelés par quelqu’un d’autre (dénommés utilisateurs « À »).</span><span class="sxs-lookup"><span data-stu-id="1ef94-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-286">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-286">Name</span></span></th>
<th><span data-ttu-id="1ef94-287">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1ef94-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ef94-288">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-289"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-290">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-290">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-291">Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="1ef94-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-292"><strong>Utilisateurs destinataires principaux</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-293">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-293">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-294">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="1ef94-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-295"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-296">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-296">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-297">Nombre total de sessions ayant échoué par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1ef94-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="1ef94-298">Mesures pour les principaux agents d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ef94-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="1ef94-299">Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base du logiciel de point de terminaison ayant rencontré le plus d’échecs.</span><span class="sxs-lookup"><span data-stu-id="1ef94-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="1ef94-300">Mesures pour les principaux agents d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ef94-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef94-301">Nom</span><span class="sxs-lookup"><span data-stu-id="1ef94-301">Name</span></span></th>
<th><span data-ttu-id="1ef94-302">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1ef94-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ef94-303">Description</span><span class="sxs-lookup"><span data-stu-id="1ef94-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-304"><strong>Classement</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-305">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-305">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-p115">Classement relatif des sessions ayant échoué sur la base de l’agent d’utilisateur (logiciel) impliqué dans la session. Par exemple : RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="1ef94-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef94-308"><strong>Principaux agents d’utilisateurs</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-309">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-309">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-310">Nom de l’agent d’utilisateur impliqué dans la session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="1ef94-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ef94-311"><strong>Sessions</strong></span><span class="sxs-lookup"><span data-stu-id="1ef94-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1ef94-312">Non</span><span class="sxs-lookup"><span data-stu-id="1ef94-312">No</span></span></p></td>
<td><p><span data-ttu-id="1ef94-313">Nombre total de sessions ayant échoué par agent.</span><span class="sxs-lookup"><span data-stu-id="1ef94-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

