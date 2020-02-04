---
title: 'Lync Server 2013 : rapport de diagnostic d’activité d’égal à égal'
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
ms.openlocfilehash: dc98f1c81f79605da2de2b06397d8a23d8086861
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="c0ce8-102">Rapport de diagnostic d’activité d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0ce8-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0ce8-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c0ce8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c0ce8-104">Le rapport de diagnostic des activités P2P fournit des informations sur la réussite ou l’échec des sessions de communication P2P.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="c0ce8-105">Notez que Microsoft Lync Server 2013 distingue différentes sortes d’échecs :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="c0ce8-106">**échec attendu**.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-106">**Expected failure**.</span></span> <span data-ttu-id="c0ce8-107">Un échec attendu est en général un échec considéré comme strictement technique.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="c0ce8-108">Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit absente de son bureau et ne puisse donc répondre à votre appel.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="c0ce8-109">Étant donné que l’appel n’a pas été répondu, il est techniquement considéré comme un échec.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="c0ce8-110">En revanche, il s’agissait d’un échec attendu : Microsoft Lync Server 2013 ne vous attend pas à répondre au téléphone si vous n’êtes pas disponible pour répondre au téléphone.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="c0ce8-111">De même, un échec attendu se produira si vous tentez d’envoyer un message instantané à un utilisateur qui est hors ligne ou qui est connecté à un téléphone qui ne prend pas les messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="c0ce8-112">**Échec inattendu**.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-112">**Unexpected failure**.</span></span> <span data-ttu-id="c0ce8-113">Un échec inattendu constitue exactement ce que son nom indique : une erreur à laquelle on ne s’attend pas, compte tenu des circonstances.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="c0ce8-114">Par exemple, supposons que vous appelez une personne et qu’elle soit disponible pour répondre à un appel. Toutefois, lorsque Lync Server 2013 tente d’acheminer votre appel vers la boîte vocale, l’appel échoue car la connectivité à la messagerie unifiée Exchange a été perdue.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="c0ce8-115">Il s’agit d’une erreur inattendue : il est possible que les appels soient toujours acheminés vers la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="c0ce8-116">En règle générale, les échecs inattendus sont de vrais échecs : ce sont des problèmes auxquels il n’est pas possible de remédier en formant les utilisateurs ou à l’aide de mesures similaires.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="c0ce8-p104">Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions. Par exemple, l’illustration précédente indique les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0ce8-119">Réussites</span><span class="sxs-lookup"><span data-stu-id="c0ce8-119">Successes</span></span></th>
<th><span data-ttu-id="c0ce8-120">Échecs attendus</span><span class="sxs-lookup"><span data-stu-id="c0ce8-120">Expected failures</span></span></th>
<th><span data-ttu-id="c0ce8-121">Échecs inattendus</span><span class="sxs-lookup"><span data-stu-id="c0ce8-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="c0ce8-122">Nombre total de sessions</span><span class="sxs-lookup"><span data-stu-id="c0ce8-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0ce8-123">2024</span><span class="sxs-lookup"><span data-stu-id="c0ce8-123">2024</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-124">469</span><span class="sxs-lookup"><span data-stu-id="c0ce8-124">469</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-125">Seiz</span><span class="sxs-lookup"><span data-stu-id="c0ce8-125">16</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-126">2521</span><span class="sxs-lookup"><span data-stu-id="c0ce8-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c0ce8-127">Si vous additionnez 2 024 + 469 + 16, vous obtenez un total de 2 509 sessions alors que la colonne du total des sessions indique 2 521 sessions.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="c0ce8-128">Les 12 sessions « manquantes » sont des sessions que le système n’est pas parvenu à classer comme des succès ou des échecs.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="c0ce8-129">Ce peut arriver dans le cas où un produit tiers introduit un nouveau code de diagnostic qui n’est pas familier à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="c0ce8-130">Lorsque cela arrive, les appels effectués à l’aide de ce produit et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="c0ce8-131">Accès au rapport de diagnostic des activités P2P</span><span class="sxs-lookup"><span data-stu-id="c0ce8-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="c0ce8-132">Le rapport de diagnostic des activités P2P est accessible à partir de la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="c0ce8-133">Vous pouvez accéder au [rapport de distribution des échecs dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c0ce8-134">Nombre d’échecs inattendus</span><span class="sxs-lookup"><span data-stu-id="c0ce8-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="c0ce8-135">Nombre d’échecs attendus</span><span class="sxs-lookup"><span data-stu-id="c0ce8-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="c0ce8-136">Utilisation optimale du rapport de diagnostic des activités P2P</span><span class="sxs-lookup"><span data-stu-id="c0ce8-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="c0ce8-p107">Il existe plusieurs manières de filtrer le rapport de diagnostic des activités P2P mais, par défaut, les options de filtrage sont masquées. Pour les afficher, cliquez sur le bouton Afficher/Masquer les paramètres dans le coin supérieur droit de la fenêtre des rapports. Les options de filtrage s’affichent alors.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c0ce8-140">Filtres</span><span class="sxs-lookup"><span data-stu-id="c0ce8-140">Filters</span></span>

<span data-ttu-id="c0ce8-p108">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de diagnostic des activités P2P vous permet de filtrer selon des éléments précis, tels que la modalité de session (à savoir messagerie instantanée, transfert de fichiers ou partage d’application). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c0ce8-145">Le tableau ci-dessous dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic des activités P2P.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="c0ce8-146">Filtres du rapport de diagnostic des activités P2P</span><span class="sxs-lookup"><span data-stu-id="c0ce8-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0ce8-147">Nom</span><span class="sxs-lookup"><span data-stu-id="c0ce8-147">Name</span></span></th>
<th><span data-ttu-id="c0ce8-148">Description</span><span class="sxs-lookup"><span data-stu-id="c0ce8-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0ce8-149"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-p109">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c0ce8-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c0ce8-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c0ce8-p110">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c0ce8-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c0ce8-155">7/7/2012</span></span></p>
<p><span data-ttu-id="c0ce8-156">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c0ce8-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c0ce8-157">7/3/2012</span></span></p>
<p><span data-ttu-id="c0ce8-158">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0ce8-159"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-p111">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c0ce8-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c0ce8-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c0ce8-p112">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c0ce8-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c0ce8-165">7/7/2012</span></span></p>
<p><span data-ttu-id="c0ce8-166">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c0ce8-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c0ce8-167">7/3/2012</span></span></p>
<p><span data-ttu-id="c0ce8-168">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0ce8-169"><strong>Intervalle</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-p113">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0ce8-172">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="c0ce8-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c0ce8-173">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="c0ce8-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c0ce8-174">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="c0ce8-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c0ce8-175">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="c0ce8-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c0ce8-176">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-176">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="c0ce8-177">Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="c0ce8-177">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0ce8-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-p115">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0ce8-182"><strong>Modalité</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-p116">Indique le type d’activité de communication qui a eu lieu. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0ce8-185">[Tous]</span><span class="sxs-lookup"><span data-stu-id="c0ce8-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="c0ce8-186">Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="c0ce8-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="c0ce8-187">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="c0ce8-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="c0ce8-188">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="c0ce8-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="c0ce8-189">Audio</span><span class="sxs-lookup"><span data-stu-id="c0ce8-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="c0ce8-190">Vidéo</span><span class="sxs-lookup"><span data-stu-id="c0ce8-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="c0ce8-191">Mesures (par modalité)</span><span class="sxs-lookup"><span data-stu-id="c0ce8-191">Metrics (per modality)</span></span>

<span data-ttu-id="c0ce8-192">Le tableau ci-dessous dresse la liste des informations fournies dans le rapport de diagnostic des activités P2P pour chaque modalité.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="c0ce8-193">Mesures (par modalité)</span><span class="sxs-lookup"><span data-stu-id="c0ce8-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0ce8-194">Nom</span><span class="sxs-lookup"><span data-stu-id="c0ce8-194">Name</span></span></th>
<th><span data-ttu-id="c0ce8-195">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c0ce8-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c0ce8-196">Description</span><span class="sxs-lookup"><span data-stu-id="c0ce8-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0ce8-197"><strong>Nombre de réussites</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-198">Non</span><span class="sxs-lookup"><span data-stu-id="c0ce8-198">No</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-199">Nombre total des sessions P2P réussies.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0ce8-200"><strong>Pourcentage de réussite</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-201">Non</span><span class="sxs-lookup"><span data-stu-id="c0ce8-201">No</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-p117">Pourcentage des sessions P2P qui se sont terminées avec des problèmes importants. Calculé en divisant le volume des opérations réussies par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0ce8-204"><strong>Nombre d’échecs attendus</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-205">Non</span><span class="sxs-lookup"><span data-stu-id="c0ce8-205">No</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-206">Nombre total de sessions pour lesquelles &quot;un échec&quot; inattendu s’est produit.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="c0ce8-p118">Un échec attendu est un échec auquel il faut s’attendre. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, il faut s’attendre à ce que tout appel émis vers cet utilisateur échoue.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0ce8-209"><strong>Pourcentage d’échec attendu</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-210">Non</span><span class="sxs-lookup"><span data-stu-id="c0ce8-210">No</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-p119">Pourcentage de sessions P2P lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0ce8-213"><strong>Nombre d’échecs inattendus</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-214">Non</span><span class="sxs-lookup"><span data-stu-id="c0ce8-214">No</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-215">Nombre total de sessions pour lesquelles &quot;un échec&quot; inattendu s’est produit.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="c0ce8-p120">Un échec inattendu est un échec qui se produit alors que le système semble intègre. Par exemple, un appel ne doit pas être coupé si l’appelant est mis en attente. Dans le cas contraire, ce problème est considéré comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0ce8-219"><strong>Pourcentage d’échec inattendu</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-220">Non</span><span class="sxs-lookup"><span data-stu-id="c0ce8-220">No</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-p121">Pourcentage de sessions P2P lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0ce8-223"><strong>Nombre total de sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce8-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c0ce8-224">Non</span><span class="sxs-lookup"><span data-stu-id="c0ce8-224">No</span></span></p></td>
<td><p><span data-ttu-id="c0ce8-225">Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</span><span class="sxs-lookup"><span data-stu-id="c0ce8-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

