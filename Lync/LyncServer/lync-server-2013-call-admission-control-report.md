---
title: 'Lync Server 2013 : rapport de contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5b643adf6a8208285aeba66304ddd1657afdfa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="351ac-102">Rapport de contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="351ac-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="351ac-103">_**Dernière modification de la rubrique :** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="351ac-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="351ac-104">Le rapport de contrôle d’admission des appels fournit des informations sur les sessions d’égal à égal et de conférence menées sous restrictions définies en place par le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="351ac-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="351ac-105">Le contrôle d’admission des appels, introduit dans Microsoft Lync Server 2010, permet aux administrateurs d’autoriser (ou non) les sessions de communication en fonction des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="351ac-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="351ac-106">Par exemple, les administrateurs peuvent créer des stratégies qui imposent une limite sur la quantité de bande passante disponible pour les appels vocaux et vidéo.</span><span class="sxs-lookup"><span data-stu-id="351ac-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="351ac-107">Si cette limite de bande passante a été atteinte, aucun nouvel appel vocal ou vidéo ne peut être passé tant que l’un des appels en cours n’a pas terminé et libéré les ressources réseau requises.</span><span class="sxs-lookup"><span data-stu-id="351ac-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="351ac-108">Accès au rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="351ac-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="351ac-109">Le rapport de contrôle d’admission des appels est accessible à partir de la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="351ac-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="351ac-110">À partir du rapport de contrôle d’admission des appels, vous pouvez accéder à l’un des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="351ac-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="351ac-111">Rapport détaillé de conférence : pour accéder à ce rapport, cliquez sur la mesure détails à partir d’une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="351ac-112">Rapport détaillé de session P2P : pour accéder à ce rapport, cliquez sur la mesure détails d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="351ac-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="351ac-113">Utilisation optimale du rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="351ac-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="351ac-114">Pour obtenir la liste des appels ayant échoué en raison d’une bande passante insuffisante, sélectionnez appels rejetés en raison du contrôle d’admission des appels dans la liste déroulante catégorie d’appel.</span><span class="sxs-lookup"><span data-stu-id="351ac-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="351ac-115">La plupart des appels renvoyés auront probablement l’ID de diagnostic 5 :</span><span class="sxs-lookup"><span data-stu-id="351ac-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="351ac-116">Bande passante insuffisante pour établir une session.</span><span class="sxs-lookup"><span data-stu-id="351ac-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="351ac-117">Tentez un nouveau routage PSTN.</span><span class="sxs-lookup"><span data-stu-id="351ac-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="351ac-118">Cela indique que les limitations du contrôle d’admission des appels empêchaient l’appel d’être effectué sur le réseau VoIP.</span><span class="sxs-lookup"><span data-stu-id="351ac-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="351ac-119">Filtres</span><span class="sxs-lookup"><span data-stu-id="351ac-119">Filters</span></span>

<span data-ttu-id="351ac-120">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="351ac-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="351ac-121">Par exemple, le rapport de contrôle d’admission des appels vous permet de filtrer les appels par l’utilisateur qui a initié l’appel ou par l’utilisateur qui a été appelé.</span><span class="sxs-lookup"><span data-stu-id="351ac-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="351ac-122">Vous pouvez également choisir le mode de groupement des données.</span><span class="sxs-lookup"><span data-stu-id="351ac-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="351ac-123">Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="351ac-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="351ac-124">Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="351ac-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="351ac-125">Filtres du rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="351ac-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="351ac-126">Nom</span><span class="sxs-lookup"><span data-stu-id="351ac-126">Name</span></span></th>
<th><span data-ttu-id="351ac-127">Description</span><span class="sxs-lookup"><span data-stu-id="351ac-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="351ac-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-p106">Date/heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="351ac-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="351ac-131">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="351ac-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="351ac-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="351ac-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="351ac-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="351ac-134">7/17/12012</span></span></p>
<p><span data-ttu-id="351ac-135">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="351ac-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="351ac-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="351ac-136">7/13/2012</span></span></p>
<p><span data-ttu-id="351ac-137">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="351ac-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-p108">Date/heure de fin de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="351ac-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="351ac-141">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="351ac-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="351ac-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="351ac-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="351ac-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="351ac-144">7/17/12012</span></span></p>
<p><span data-ttu-id="351ac-145">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="351ac-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="351ac-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="351ac-146">7/13/2012</span></span></p>
<p><span data-ttu-id="351ac-147">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="351ac-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-p110">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="351ac-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-152"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-153">Type d’activité.</span><span class="sxs-lookup"><span data-stu-id="351ac-153">Type of activity.</span></span> <span data-ttu-id="351ac-154">Sélectionnez l’une des activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="351ac-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="351ac-155">Tous les</span><span class="sxs-lookup"><span data-stu-id="351ac-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="351ac-156">Égal à égal</span><span class="sxs-lookup"><span data-stu-id="351ac-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="351ac-157">Salle</span><span class="sxs-lookup"><span data-stu-id="351ac-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-158"><strong>Catégorie d’appel</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-159">Indique la raison pour laquelle le contrôle d’admission des appels a été utilisé pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="351ac-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="351ac-160">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="351ac-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="351ac-161">Tous les</span><span class="sxs-lookup"><span data-stu-id="351ac-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="351ac-162">Appel rejeté en raison du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="351ac-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="351ac-163">Appels réacheminés via PSTN en raison du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="351ac-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="351ac-164">Mesures pour les sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="351ac-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="351ac-165">Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les sessions P2P (c’est-à-dire, les sessions qui n’impliquent que deux participants).</span><span class="sxs-lookup"><span data-stu-id="351ac-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="351ac-166">Mesures pour les sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="351ac-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="351ac-167">Nom</span><span class="sxs-lookup"><span data-stu-id="351ac-167">Name</span></span></th>
<th><span data-ttu-id="351ac-168">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="351ac-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="351ac-169">Description</span><span class="sxs-lookup"><span data-stu-id="351ac-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="351ac-170"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-171">Non</span><span class="sxs-lookup"><span data-stu-id="351ac-171">No</span></span></p></td>
<td><p><span data-ttu-id="351ac-172">Lorsque vous cliquez sur cet élément, le rapport vous montre un rapport détaillé de session P2P pour la session spécifiée.</span><span class="sxs-lookup"><span data-stu-id="351ac-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-173"><strong>De l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-174">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-175">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="351ac-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-176"><strong>À l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-177">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-178">Adresse SIP de l’utilisateur qui a été invité à rejoindre la session.</span><span class="sxs-lookup"><span data-stu-id="351ac-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-179"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-180">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-181">Modalités de communication (audio et vidéo, par exemple) qui ont été utilisées pendant la session.</span><span class="sxs-lookup"><span data-stu-id="351ac-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-182"><strong>Heure d’invitation</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-183">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-184">Date et heure auxquelles l’invitation initiale à la session a été envoyée à l’utilisateur de.</span><span class="sxs-lookup"><span data-stu-id="351ac-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-185"><strong>Heure de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-186">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-187">Date et heure auxquelles l’acceptation de l’invitation a été reçue.</span><span class="sxs-lookup"><span data-stu-id="351ac-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-188"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-189">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-190">Date et heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="351ac-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-191"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-192">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-p113">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="351ac-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="351ac-195">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="351ac-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="351ac-196">Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les sessions de conférence (c’est-à-dire, les sessions qui impliquent trois participants ou plus).</span><span class="sxs-lookup"><span data-stu-id="351ac-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="351ac-197">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="351ac-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="351ac-198">Nom</span><span class="sxs-lookup"><span data-stu-id="351ac-198">Name</span></span></th>
<th><span data-ttu-id="351ac-199">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="351ac-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="351ac-200">Description</span><span class="sxs-lookup"><span data-stu-id="351ac-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="351ac-201"><strong>URI de la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-202">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-203">Identificateur unique de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-203">Unique identifier for the conference.</span></span> <span data-ttu-id="351ac-204">Lorsque vous cliquez sur cet élément, le rapport affiche les participants individuels de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-205"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-206">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-207">Adresse SIP de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-209">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-210">Serveur Edge utilisé dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-211"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-212">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-213">Date et heure auxquelles la conférence a commencé.</span><span class="sxs-lookup"><span data-stu-id="351ac-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-214"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-215">Oui</span><span class="sxs-lookup"><span data-stu-id="351ac-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="351ac-216">Date et heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="351ac-217">Mesures pour les participants à la Conférence individuelle</span><span class="sxs-lookup"><span data-stu-id="351ac-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="351ac-218">Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour chaque participant d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="351ac-219">Mesures pour les participants à la Conférence individuelle</span><span class="sxs-lookup"><span data-stu-id="351ac-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="351ac-220">Nom</span><span class="sxs-lookup"><span data-stu-id="351ac-220">Name</span></span></th>
<th><span data-ttu-id="351ac-221">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="351ac-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="351ac-222">Description</span><span class="sxs-lookup"><span data-stu-id="351ac-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="351ac-223"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-224">Non</span><span class="sxs-lookup"><span data-stu-id="351ac-224">No</span></span></p></td>
<td><p><span data-ttu-id="351ac-225">Rôle (par exemple, présentateur) joué par le participant à la conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-226"><strong>Participant</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-227">Non</span><span class="sxs-lookup"><span data-stu-id="351ac-227">No</span></span></p></td>
<td><p><span data-ttu-id="351ac-228">Adresse SIP du participant à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-229"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-230">Non</span><span class="sxs-lookup"><span data-stu-id="351ac-230">No</span></span></p></td>
<td><p><span data-ttu-id="351ac-231">Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</span><span class="sxs-lookup"><span data-stu-id="351ac-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-232"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-233">Non</span><span class="sxs-lookup"><span data-stu-id="351ac-233">No</span></span></p></td>
<td><p><span data-ttu-id="351ac-234">Type de conférence (par exemple, conférence A/V).</span><span class="sxs-lookup"><span data-stu-id="351ac-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-235"><strong>Heure d’arrivée</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-236">Non</span><span class="sxs-lookup"><span data-stu-id="351ac-236">No</span></span></p></td>
<td><p><span data-ttu-id="351ac-237">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351ac-238"><strong>Heure de départ</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-239">Non</span><span class="sxs-lookup"><span data-stu-id="351ac-239">No</span></span></p></td>
<td><p><span data-ttu-id="351ac-240">Date et heure auxquelles le participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="351ac-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351ac-241"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="351ac-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="351ac-242">Non</span><span class="sxs-lookup"><span data-stu-id="351ac-242">No</span></span></p></td>
<td><p><span data-ttu-id="351ac-p115">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="351ac-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

