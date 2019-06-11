---
title: 'Lync Server 2013: rapport de contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f31159742757b7ef8b6889b7961bad747b1f6d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="dd348-102">Rapport de contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd348-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd348-103">_**Dernière modification de la rubrique:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="dd348-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="dd348-104">Le rapport du contrôle d’admission des appels fournit des informations sur les sessions P2P et de conférence menées avec des restrictions mises en place par le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="dd348-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="dd348-105">Le contrôle d’admission des appels, présenté dans Microsoft Lync Server 2010, permet aux administrateurs d’autoriser (ou non) les sessions de communication en fonction de contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="dd348-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="dd348-106">Par exemple, les administrateurs peuvent créer des stratégies qui imposent une quantité limite de bande passante disponible pour les appels vocaux et vidéo.</span><span class="sxs-lookup"><span data-stu-id="dd348-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="dd348-107">Si cette limite est atteinte, aucun nouvel appel vocal ou vidéo ne peut être effectué tant que l’un des appels en cours n’est pas terminé et que les ressources réseau requises ne sont pas libérées.</span><span class="sxs-lookup"><span data-stu-id="dd348-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="dd348-108">Accès au rapport du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="dd348-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="dd348-p102">Le rapport du contrôle d’admission des appels est accessible à partir de la page d’accueil des Rapports de suivi. De ce rapport, vous pouvez atteindre l’un des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="dd348-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="dd348-111">Rapport détaillé de conférence – Pour accéder à ce rapport, cliquez sur la mesure Détails à partir d’une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="dd348-112">Rapport détaillé de session P2P – Pour accéder à ce rapport, cliquez sur la mesure Détails d’une session P2P.</span><span class="sxs-lookup"><span data-stu-id="dd348-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="dd348-113">Utilisation optimale du rapport du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="dd348-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="dd348-p103">Pour obtenir une liste des appels ayant échoué en raison d’une bande passante insuffisante, sélectionnez Appels rejetés en raison du contrôle d’admission des appels dans la liste déroulante Catégorie d’appel. La plupart des appels renvoyés auront probablement un ID de diagnostic de 5 :</span><span class="sxs-lookup"><span data-stu-id="dd348-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="dd348-p104">Bande passante insuffisante pour établir une session. Essayez le réacheminement RTC.</span><span class="sxs-lookup"><span data-stu-id="dd348-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="dd348-118">Cela indique que les limitations du contrôle d’admission des appels empêchaient l’appel d’être effectué sur le réseau VoIP.</span><span class="sxs-lookup"><span data-stu-id="dd348-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dd348-119">Filtres</span><span class="sxs-lookup"><span data-stu-id="dd348-119">Filters</span></span>

<span data-ttu-id="dd348-p105">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de contrôle d’admission des appels vous permet de filtrer des appels en fonction de l’utilisateur qui les a émis ou qui a été appelé. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="dd348-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="dd348-124">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="dd348-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="dd348-125">Filtres du rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="dd348-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd348-126">Nom</span><span class="sxs-lookup"><span data-stu-id="dd348-126">Name</span></span></th>
<th><span data-ttu-id="dd348-127">Description</span><span class="sxs-lookup"><span data-stu-id="dd348-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd348-128"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-p106">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="dd348-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dd348-131">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dd348-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="dd348-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="dd348-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dd348-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="dd348-134">7/17/12012</span></span></p>
<p><span data-ttu-id="dd348-135">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="dd348-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dd348-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="dd348-136">7/13/2012</span></span></p>
<p><span data-ttu-id="dd348-137">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="dd348-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-138"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-p108">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="dd348-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dd348-141">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dd348-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="dd348-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="dd348-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dd348-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="dd348-144">7/17/12012</span></span></p>
<p><span data-ttu-id="dd348-145">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="dd348-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dd348-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="dd348-146">7/13/2012</span></span></p>
<p><span data-ttu-id="dd348-147">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="dd348-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-p110">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="dd348-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-152"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-p111">Type d’activité. Sélectionnez l’une des activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="dd348-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="dd348-155">[Tous]</span><span class="sxs-lookup"><span data-stu-id="dd348-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="dd348-156">P2P</span><span class="sxs-lookup"><span data-stu-id="dd348-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="dd348-157">Conférence</span><span class="sxs-lookup"><span data-stu-id="dd348-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-158"><strong>Catégorie d’appel</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-p112">Indique la raison pour laquelle le contrôle d’admission des appels a été utilisé pour l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="dd348-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dd348-161">[Tous]</span><span class="sxs-lookup"><span data-stu-id="dd348-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="dd348-162">Appels rejetés en raison du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="dd348-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="dd348-163">Appels réacheminés via RTC en raison du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="dd348-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="dd348-164">Mesures pour les sessions P2P</span><span class="sxs-lookup"><span data-stu-id="dd348-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="dd348-165">Le tableau ci-dessous répertorie les informations fournies par le rapport de contrôle d’admission des appels pour les sessions P2P (c’est-à-dire, les sessions qui n’impliquent que deux participants).</span><span class="sxs-lookup"><span data-stu-id="dd348-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="dd348-166">Mesures pour les sessions P2P</span><span class="sxs-lookup"><span data-stu-id="dd348-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd348-167">Nom</span><span class="sxs-lookup"><span data-stu-id="dd348-167">Name</span></span></th>
<th><span data-ttu-id="dd348-168">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="dd348-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dd348-169">Description</span><span class="sxs-lookup"><span data-stu-id="dd348-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd348-170"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-171">Non</span><span class="sxs-lookup"><span data-stu-id="dd348-171">No</span></span></p></td>
<td><p><span data-ttu-id="dd348-172">Lorsque vous cliquez sur cet élément, le rapport présente un rapport détaillé de session P2P pour la session spécifiée.</span><span class="sxs-lookup"><span data-stu-id="dd348-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-173"><strong>De l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-174">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-175">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="dd348-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-176"><strong>À l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-177">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-178">Adresse SIP de l’utilisateur qui a été invité à participer à la session.</span><span class="sxs-lookup"><span data-stu-id="dd348-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-179"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-180">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-181">Modalités de communication (audio et vidéo) qui ont été utilisées pendant la session.</span><span class="sxs-lookup"><span data-stu-id="dd348-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-182"><strong>Heure d’invitation</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-183">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-184">Date et heure auxquelles l’invitation initiale à la session a été envoyée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dd348-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-185"><strong>Heure de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-186">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-187">Date et heure auxquelles l’acceptation de l’invitation a été reçue.</span><span class="sxs-lookup"><span data-stu-id="dd348-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-188"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-189">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-190">Date et heure auxquelles la session s’est terminée.</span><span class="sxs-lookup"><span data-stu-id="dd348-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-191"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-192">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-p113">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.</span><span class="sxs-lookup"><span data-stu-id="dd348-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="dd348-195">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="dd348-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="dd348-196">Le tableau ci-dessous répertorie les informations fournies par le rapport de contrôle d’admission des appels pour les sessions de conférence (c’est-à-dire, les sessions qui impliquent trois participants ou plus).</span><span class="sxs-lookup"><span data-stu-id="dd348-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="dd348-197">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="dd348-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd348-198">Nom</span><span class="sxs-lookup"><span data-stu-id="dd348-198">Name</span></span></th>
<th><span data-ttu-id="dd348-199">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="dd348-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dd348-200">Description</span><span class="sxs-lookup"><span data-stu-id="dd348-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd348-201"><strong>URI de la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-202">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-p114">Identificateur unique de la conférence. Lorsque vous cliquez sur cet élément, le rapport présente les participants individuels de la conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-205"><strong>Organisateur</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-206">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-207">Adresse SIP de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-209">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-210">Serveur Edge utilisé pour la conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-211"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-212">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-213">Date et heure auxquelles la conférence a commencé.</span><span class="sxs-lookup"><span data-stu-id="dd348-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-214"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-215">Oui</span><span class="sxs-lookup"><span data-stu-id="dd348-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd348-216">Date et heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="dd348-217">Mesures pour les participants individuels de la conférence</span><span class="sxs-lookup"><span data-stu-id="dd348-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="dd348-218">Le tableau qui suit répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour chaque participant d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="dd348-219">Mesures pour les participants individuels de la conférence</span><span class="sxs-lookup"><span data-stu-id="dd348-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd348-220">Nom</span><span class="sxs-lookup"><span data-stu-id="dd348-220">Name</span></span></th>
<th><span data-ttu-id="dd348-221">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="dd348-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dd348-222">Description</span><span class="sxs-lookup"><span data-stu-id="dd348-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd348-223"><strong>Rôle</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-224">Non</span><span class="sxs-lookup"><span data-stu-id="dd348-224">No</span></span></p></td>
<td><p><span data-ttu-id="dd348-225">Rôle (par exemple, présentateur) joué par le participant à la conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-226"><strong>Participant</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-227">Non</span><span class="sxs-lookup"><span data-stu-id="dd348-227">No</span></span></p></td>
<td><p><span data-ttu-id="dd348-228">Adresse SIP du participant à la conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-229"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-230">Non</span><span class="sxs-lookup"><span data-stu-id="dd348-230">No</span></span></p></td>
<td><p><span data-ttu-id="dd348-231">Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</span><span class="sxs-lookup"><span data-stu-id="dd348-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-232"><strong>Modalité</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-233">Non</span><span class="sxs-lookup"><span data-stu-id="dd348-233">No</span></span></p></td>
<td><p><span data-ttu-id="dd348-234">Type de conférence (par exemple, conférence A/V).</span><span class="sxs-lookup"><span data-stu-id="dd348-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-235"><strong>Heure d’arrivée</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-236">Non</span><span class="sxs-lookup"><span data-stu-id="dd348-236">No</span></span></p></td>
<td><p><span data-ttu-id="dd348-237">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd348-238"><strong>Heure de départ</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-239">Non</span><span class="sxs-lookup"><span data-stu-id="dd348-239">No</span></span></p></td>
<td><p><span data-ttu-id="dd348-240">Date et heure auxquelles le participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="dd348-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd348-241"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="dd348-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dd348-242">Non</span><span class="sxs-lookup"><span data-stu-id="dd348-242">No</span></span></p></td>
<td><p><span data-ttu-id="dd348-p115">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.</span><span class="sxs-lookup"><span data-stu-id="dd348-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

