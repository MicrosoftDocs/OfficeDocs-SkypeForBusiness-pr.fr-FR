---
title: 'Lync Server 2013 : rapport de synthèse des activités d’égal à égal'
description: 'Lync Server 2013 : rapport de synthèse des activités P2P.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f081f542a5063ed83be470d3e991c58e458b487
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557300"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="a5bc6-103">Rapport de synthèse des activités P2P dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5bc6-103">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5bc6-104">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a5bc6-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a5bc6-105">Le rapport de synthèse des activités d’égal à égal fournit un aperçu de vos sessions de communication d؊’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-105">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="a5bc6-106">Une session d’égal à égal n’implique généralement que deux utilisateurs et ne nécessite pas l’utilisation des services de conférence Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-106">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="a5bc6-107">Par comparaison, une conférence implique généralement plus de deux utilisateurs et nécessite l’utilisation des services de conférence Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-107">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="a5bc6-108">L’activité de conférence est reportée sur le rapport de synthèse de conférence.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-108">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="a5bc6-109">Le rapport de synthèse des activités d’égal à égal vous aide à répondre à des questions telles que :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-109">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="a5bc6-110">Combien de messages instantanés d’égal à égal mes utilisateurs envoient-ils généralement par jour ?</span><span class="sxs-lookup"><span data-stu-id="a5bc6-110">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="a5bc6-111">Certains de mes utilisateurs tirent-ils réellement parti des fonctionnalités de partage d’application et de transfert de fichiers Lync Server ?</span><span class="sxs-lookup"><span data-stu-id="a5bc6-111">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="a5bc6-p102">Les utilisateurs ont signalé que le réseau semblait lent à certains moments de la journée. Combien de minutes sont consacrées à des sessions audio et vidéo d’égal à égal durant ces périodes ?</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="a5bc6-114">Accès au rapport de synthèse des activités d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-114">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="a5bc6-115">Vous pouvez accéder au rapport de synthèse des activités d’égal à égal à partir de la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-115">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="a5bc6-116">Pour ouvrir le [rapport de messagerie instantanée P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , cliquez sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-116">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="a5bc6-117">Nombre total de sessions de messagerie instantanée d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-117">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="a5bc6-118">Nombre total de messages de messagerie instantanée d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-118">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="a5bc6-119">De même, vous pouvez ouvrir le rapport vocal et vidéo d’égal à égal en cliquant sur l’une de ces mesures :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-119">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="a5bc6-120">Nombre total de sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-120">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="a5bc6-121">Nombre total de minutes par session audio d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-121">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="a5bc6-122">Nombre total de sessions audio d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-122">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="a5bc6-123">Nombre total de minutes par session audio d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-123">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="a5bc6-124">Utilisation optimale du rapport de synthèse des activités d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-124">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="a5bc6-p104">En bas du rapport de synthèse des activités d’égal à égal, vous trouverez les totaux des mesures telles que le Nombre total de sessions de messagerie instantanée d’égal à égal et le Nombre total de messages de messagerie instantanée d’égal à égal. Vous obtenez ainsi un rapide résumé des informations détaillées contenues dans le corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a5bc6-127">Filtres</span><span class="sxs-lookup"><span data-stu-id="a5bc6-127">Filters</span></span>

<span data-ttu-id="a5bc6-p105">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de synthèse des activités d’égal à égal vous permet de choisir le mode de groupement des données. Dans ce cas, les activités sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a5bc6-131">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des activités d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-131">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="a5bc6-132">Filtres du rapport de synthèse des activités d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-132">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5bc6-133">Nom</span><span class="sxs-lookup"><span data-stu-id="a5bc6-133">Name</span></span></th>
<th><span data-ttu-id="a5bc6-134">Description</span><span class="sxs-lookup"><span data-stu-id="a5bc6-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5bc6-135"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-135"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p106">Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a5bc6-138">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a5bc6-138">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="a5bc6-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a5bc6-141">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="a5bc6-141">7/17/12012</span></span></p>
<p><span data-ttu-id="a5bc6-142">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a5bc6-143">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="a5bc6-143">7/13/2012</span></span></p>
<p><span data-ttu-id="a5bc6-144">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5bc6-145"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-145"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p108">Date et heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a5bc6-148">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a5bc6-148">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="a5bc6-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a5bc6-151">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="a5bc6-151">7/17/12012</span></span></p>
<p><span data-ttu-id="a5bc6-152">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-152">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a5bc6-153">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="a5bc6-153">7/13/2012</span></span></p>
<p><span data-ttu-id="a5bc6-154">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-154">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5bc6-155"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-155"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p110">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a5bc6-158">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="a5bc6-158">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a5bc6-159">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="a5bc6-159">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a5bc6-160">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="a5bc6-160">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a5bc6-161">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="a5bc6-161">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="a5bc6-p111">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/17/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a5bc6-164">Mesures</span><span class="sxs-lookup"><span data-stu-id="a5bc6-164">Metrics</span></span>

<span data-ttu-id="a5bc6-165">Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des activités d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-165">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="a5bc6-166">Mesures du rapport de synthèse des activités d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5bc6-166">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5bc6-167">Nom</span><span class="sxs-lookup"><span data-stu-id="a5bc6-167">Name</span></span></th>
<th><span data-ttu-id="a5bc6-168">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="a5bc6-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a5bc6-169">Description</span><span class="sxs-lookup"><span data-stu-id="a5bc6-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5bc6-170"><strong>Toutes les heures</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-170"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="a5bc6-171"><strong>Journalière</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-171"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="a5bc6-172"><strong>Hebdomadaire</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-172"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="a5bc6-173"><strong>Mensuelle</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-173"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-174">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-174">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p112">Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 7/17/2012, la répartition horaire des activités d’enregistrement de l’utilisateur s’affiche pour cette date.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5bc6-178"><strong>Nombre total de sessions d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-178"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-179">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-179">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-180">Nombre total de sessions d’égal à égal menées, quel qu’en soit le type.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-180">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5bc6-181"><strong>Nombre total de sessions de messagerie instantanée d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-181"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-182">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-182">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p113">Nombre total de sessions de messagerie instantanée (IM) d’égal à égal. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée d’égal à égal pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5bc6-185"><strong>Nombre total de messages de messagerie instantanée d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-185"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-186">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-186">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p114">Nombre total de messages instantanés envoyés lors des sessions d’égal à égal. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée d’égal à égal pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5bc6-189"><strong>Nombre total de sessions audio d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-189"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-190">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-190">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p115">Nombre total d’appels audio d’égal à égal. Lorsque vous cliquez sur ce champ, le rapport vous présente le rapport vocal et vidéo d’égal à égal pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5bc6-193"><strong>Nombre total de minutes par session audio d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-193"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-194">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-194">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-195">Temps total passé dans les sessions audio d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-195">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="a5bc6-196">Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo d’égal à égal pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-196">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5bc6-197"><strong>Nombre moyen de minutes par session audio d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-197"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-198">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-198">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p117">Temps moyen passé dans les sessions audio d’égal à égal. Calculé en divisant le temps total des sessions audio par le nombre total de sessions audio.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5bc6-201"><strong>Nombre total de sessions vidéo d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-201"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-202">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-202">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p118">Nombre total d’appels vidéo d’égal à égal. Notez que les sessions vidéo sont également comptées comme des sessions audio : chaque session vidéo est comptée comme une seule session vidéo et une seule session audio. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo d’égal à égal pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5bc6-206"><strong>Nombre total de minutes par session vidéo d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-206"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-207">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-207">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p119">Temps total passé dans les sessions vidéo d’égal à égal. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo d’égal à égal pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5bc6-210"><strong>Nombre moyen de minutes par session vidéo d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-210"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-211">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-211">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-p120">Temps moyen passé dans les sessions vidéo d’égal à égal. Calculé en divisant le temps total des sessions vidéo par le nombre total de sessions vidéo.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5bc6-214"><strong>Nombre total de sessions de transfert de fichiers d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-214"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-215">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-215">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-216">Nombre total de sessions d’égal à égal qui ont inclus des transferts de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-216">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5bc6-217"><strong>Nombre total de sessions de partage d’application d’égal à égal</strong></span><span class="sxs-lookup"><span data-stu-id="a5bc6-217"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a5bc6-218">Non</span><span class="sxs-lookup"><span data-stu-id="a5bc6-218">No</span></span></p></td>
<td><p><span data-ttu-id="a5bc6-219">Nombre total de sessions d’égal à égal qui ont inclus un partage d’application.</span><span class="sxs-lookup"><span data-stu-id="a5bc6-219">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

