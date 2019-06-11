---
title: 'Lync Server 2013: rapport de synthèse des activités d’égal à égal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="cc62d-102">Rapport de synthèse des activités d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc62d-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc62d-103">_**Dernière modification de la rubrique:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="cc62d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="cc62d-104">Le rapport de synthèse des activités P2P fournit un aperçu de vos sessions de communication d?’P2P.</span><span class="sxs-lookup"><span data-stu-id="cc62d-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="cc62d-105">Une session d’égal à égal implique généralement deux utilisateurs uniquement et ne nécessite pas l’utilisation des services de conférence Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc62d-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="cc62d-106">En comparaison, une conférence implique généralement plus de deux utilisateurs et nécessite l’utilisation de Microsoft Lync Server 2013 Conferencing services.</span><span class="sxs-lookup"><span data-stu-id="cc62d-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="cc62d-107">L’activité de conférence est reportée sur le rapport de synthèse de conférence.</span><span class="sxs-lookup"><span data-stu-id="cc62d-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="cc62d-108">Le rapport de synthèse des activités P2P vous aide à répondre à des questions telles que :</span><span class="sxs-lookup"><span data-stu-id="cc62d-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="cc62d-109">Combien de messages instantanés P2P mes utilisateurs envoient-ils généralement par jour ?</span><span class="sxs-lookup"><span data-stu-id="cc62d-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="cc62d-110">L’un de mes utilisateurs tire-t-il réellement parti des capacités de partage d’application et de transfert de fichiers de Lync Server?</span><span class="sxs-lookup"><span data-stu-id="cc62d-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="cc62d-p102">Les utilisateurs ont signalé que le réseau semblait lent à certains moments de la journée. Combien de minutes sont consacrées à des sessions audio et vidéo P2P durant ces périodes ?</span><span class="sxs-lookup"><span data-stu-id="cc62d-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="cc62d-113">Accès au rapport de synthèse des activités P2P</span><span class="sxs-lookup"><span data-stu-id="cc62d-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="cc62d-114">Vous pouvez accéder au rapport de synthèse des activités P2P à partir de la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="cc62d-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="cc62d-115">Pour ouvrir le [rapport de messagerie instantanée d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , cliquez sur l’une des mesures suivantes:</span><span class="sxs-lookup"><span data-stu-id="cc62d-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="cc62d-116">Nombre total de sessions d'égal à égal de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="cc62d-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="cc62d-117">Nombre total de messages de messagerie instantanée P2P</span><span class="sxs-lookup"><span data-stu-id="cc62d-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="cc62d-118">De même, vous pouvez ouvrir le rapport vocal et vidéo P2P en cliquant sur l’une de ces mesures :</span><span class="sxs-lookup"><span data-stu-id="cc62d-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="cc62d-119">Nombre total de sessions d'égal à égal audio</span><span class="sxs-lookup"><span data-stu-id="cc62d-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="cc62d-120">Nombre total de minutes par session audio P2P</span><span class="sxs-lookup"><span data-stu-id="cc62d-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="cc62d-121">Nombre total de sessions audio P2P</span><span class="sxs-lookup"><span data-stu-id="cc62d-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="cc62d-122">Nombre total de minutes par session audio P2P</span><span class="sxs-lookup"><span data-stu-id="cc62d-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="cc62d-123">Utilisation optimale du rapport de synthèse des activités P2P</span><span class="sxs-lookup"><span data-stu-id="cc62d-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="cc62d-p104">En bas du rapport de synthèse des activités P2P, vous trouverez les totaux des mesures telles que le Nombre total de sessions de messagerie instantanée P2P et le Nombre total de messages de messagerie instantanée P2P. Vous obtenez ainsi un rapide résumé des informations détaillées contenues dans le corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="cc62d-126">Filtres</span><span class="sxs-lookup"><span data-stu-id="cc62d-126">Filters</span></span>

<span data-ttu-id="cc62d-p105">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de synthèse des activités P2P vous permet de choisir le mode de groupement des données. Dans ce cas, les activités sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="cc62d-130">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des activités P2P.</span><span class="sxs-lookup"><span data-stu-id="cc62d-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="cc62d-131">Filtres du rapport de synthèse des activités P2P</span><span class="sxs-lookup"><span data-stu-id="cc62d-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc62d-132">Nom</span><span class="sxs-lookup"><span data-stu-id="cc62d-132">Name</span></span></th>
<th><span data-ttu-id="cc62d-133">Description</span><span class="sxs-lookup"><span data-stu-id="cc62d-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc62d-134"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-p106">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="cc62d-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cc62d-137">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cc62d-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="cc62d-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="cc62d-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cc62d-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="cc62d-140">7/17/12012</span></span></p>
<p><span data-ttu-id="cc62d-141">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="cc62d-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cc62d-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="cc62d-142">7/13/2012</span></span></p>
<p><span data-ttu-id="cc62d-143">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="cc62d-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc62d-144"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-p108">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="cc62d-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cc62d-147">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cc62d-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="cc62d-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="cc62d-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cc62d-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="cc62d-150">7/17/12012</span></span></p>
<p><span data-ttu-id="cc62d-151">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="cc62d-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cc62d-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="cc62d-152">7/13/2012</span></span></p>
<p><span data-ttu-id="cc62d-153">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="cc62d-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc62d-154"><strong>Intervalle</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-p110">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="cc62d-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc62d-157">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="cc62d-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cc62d-158">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="cc62d-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cc62d-159">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="cc62d-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cc62d-160">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="cc62d-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="cc62d-161">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche.</span><span class="sxs-lookup"><span data-stu-id="cc62d-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="cc62d-162">Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/17/12012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/12012 12:00 AM à 9/7/12012 12:00 AM (c’est-à-dire un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="cc62d-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="cc62d-163">Mesures</span><span class="sxs-lookup"><span data-stu-id="cc62d-163">Metrics</span></span>

<span data-ttu-id="cc62d-164">Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des activités P2P.</span><span class="sxs-lookup"><span data-stu-id="cc62d-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="cc62d-165">Mesures du rapport de synthèse des activités P2P</span><span class="sxs-lookup"><span data-stu-id="cc62d-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc62d-166">Nom</span><span class="sxs-lookup"><span data-stu-id="cc62d-166">Name</span></span></th>
<th><span data-ttu-id="cc62d-167">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="cc62d-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cc62d-168">Description</span><span class="sxs-lookup"><span data-stu-id="cc62d-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc62d-169"><strong>Toutes les heures</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="cc62d-170"><strong>Jour</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="cc62d-171"><strong>Toutes les semaines</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="cc62d-172"><strong>Mois</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-173">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-173">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-174">Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres.</span><span class="sxs-lookup"><span data-stu-id="cc62d-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="cc62d-175">Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle.</span><span class="sxs-lookup"><span data-stu-id="cc62d-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="cc62d-176">Par exemple, si vous utilisez l’intervalle quotidien et que vous cliquez sur 7/17/12012, vous pouvez voir une répartition horaire de l’activité d’inscription des utilisateurs à cette date.</span><span class="sxs-lookup"><span data-stu-id="cc62d-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc62d-177"><strong>Nombre total de sessions P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-178">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-178">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-179">Nombre total de sessions P2P menées, quel qu’en soit le type.</span><span class="sxs-lookup"><span data-stu-id="cc62d-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc62d-180"><strong>Nombre total de sessions de messagerie instantanée P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-181">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-181">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-p113">Nombre total de sessions de messagerie instantanée (IM) P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée P2P pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc62d-184"><strong>Nombre total de messages de messagerie instantanée P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-185">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-185">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-p114">Nombre total de messages instantanés envoyés lors des sessions P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée P2P pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc62d-188"><strong>Nombre total de sessions audio P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-189">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-189">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-p115">Nombre total d’appels audio P2P. Lorsque vous cliquez sur ce champ, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc62d-192"><strong>Nombre total de minutes par session audio P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-193">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-193">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-194">Temps total passé dans les sessions audio P2P.</span><span class="sxs-lookup"><span data-stu-id="cc62d-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="cc62d-195">Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc62d-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc62d-196"><strong>Nombre moyen de minutes par session audio P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-197">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-197">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-p117">Temps moyen passé dans les sessions audio P2P. Calculé en divisant le temps total des sessions audio par le nombre total de sessions audio.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc62d-200"><strong>Nombre total de sessions vidéo P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-201">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-201">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-p118">Nombre total d’appels vidéo P2P. Notez que les sessions vidéo sont également comptées comme des sessions audio : chaque session vidéo est comptée comme une seule session vidéo et une seule session audio. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc62d-205"><strong>Nombre total de minutes par session vidéo P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-206">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-206">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-p119">Temps total passé dans les sessions vidéo P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc62d-209"><strong>Nombre moyen de minutes par session vidéo P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-210">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-210">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-p120">Temps moyen passé dans les sessions vidéo P2P. Calculé en divisant le temps total des sessions vidéo par le nombre total de sessions vidéo.</span><span class="sxs-lookup"><span data-stu-id="cc62d-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc62d-213"><strong>Nombre total de sessions de transfert de fichiers P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-214">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-214">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-215">Nombre total de sessions P2P qui ont inclus des transferts de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cc62d-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc62d-216"><strong>Nombre total de sessions de partage d’application P2P</strong></span><span class="sxs-lookup"><span data-stu-id="cc62d-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cc62d-217">Non</span><span class="sxs-lookup"><span data-stu-id="cc62d-217">No</span></span></p></td>
<td><p><span data-ttu-id="cc62d-218">Nombre total de sessions P2P qui ont inclus un partage d’application.</span><span class="sxs-lookup"><span data-stu-id="cc62d-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

