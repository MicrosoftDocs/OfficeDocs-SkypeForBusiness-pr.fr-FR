---
title: 'Lync Server 2013 : rapport de contrôle d’admission des appels'
description: 'Lync Server 2013 : rapport de contrôle d’admission des appels.'
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
ms.openlocfilehash: 8764e51603e7097095894bc1230c2a2bb1126b9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572360"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="4d1c7-103">Rapport de contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d1c7-103">Call Admission Control Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d1c7-104">_**Dernière modification de la rubrique :** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="4d1c7-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="4d1c7-105">Le rapport de contrôle d’admission des appels fournit des informations sur les sessions d’égal à égal et de conférence menées sous restrictions définies en place par le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-105">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="4d1c7-106">Le contrôle d’admission des appels, introduit dans Microsoft Lync Server 2010, permet aux administrateurs d’autoriser (ou non) les sessions de communication en fonction des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-106">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="4d1c7-107">Par exemple, les administrateurs peuvent créer des stratégies qui imposent une limite sur la quantité de bande passante disponible pour les appels vocaux et vidéo.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-107">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="4d1c7-108">Si cette limite de bande passante a été atteinte, aucun nouvel appel vocal ou vidéo ne peut être passé tant que l’un des appels en cours n’a pas terminé et libéré les ressources réseau requises.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-108">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="4d1c7-109">Accès au rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="4d1c7-109">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="4d1c7-110">Le rapport de contrôle d’admission des appels est accessible à partir de la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-110">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4d1c7-111">À partir du rapport de contrôle d’admission des appels, vous pouvez accéder à l’un des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-111">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="4d1c7-112">Rapport détaillé de conférence : pour accéder à ce rapport, cliquez sur la mesure détails à partir d’une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-112">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="4d1c7-113">Rapport détaillé de session P2P : pour accéder à ce rapport, cliquez sur la mesure détails d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-113">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="4d1c7-114">Utilisation optimale du rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="4d1c7-114">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="4d1c7-115">Pour obtenir la liste des appels ayant échoué en raison d’une bande passante insuffisante, sélectionnez appels rejetés en raison du contrôle d’admission des appels dans la liste déroulante catégorie d’appel.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-115">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="4d1c7-116">La plupart des appels renvoyés auront probablement l’ID de diagnostic 5 :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-116">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="4d1c7-117">Bande passante insuffisante pour établir une session.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-117">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="4d1c7-118">Tentez un nouveau routage PSTN.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-118">Attempt PSTN re-route.</span></span>

<span data-ttu-id="4d1c7-119">Cela indique que les limitations du contrôle d’admission des appels empêchaient l’appel d’être effectué sur le réseau VoIP.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-119">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4d1c7-120">Filtres</span><span class="sxs-lookup"><span data-stu-id="4d1c7-120">Filters</span></span>

<span data-ttu-id="4d1c7-121">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-121">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="4d1c7-122">Par exemple, le rapport de contrôle d’admission des appels vous permet de filtrer les appels par l’utilisateur qui a initié l’appel ou par l’utilisateur qui a été appelé.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-122">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="4d1c7-123">Vous pouvez également choisir le mode de groupement des données.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-123">You can also choose how data should be grouped.</span></span> <span data-ttu-id="4d1c7-124">Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-124">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4d1c7-125">Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-125">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="4d1c7-126">Filtres du rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="4d1c7-126">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1c7-127">Nom</span><span class="sxs-lookup"><span data-stu-id="4d1c7-127">Name</span></span></th>
<th><span data-ttu-id="4d1c7-128">Description</span><span class="sxs-lookup"><span data-stu-id="4d1c7-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-129"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-129"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-p106">Date/heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4d1c7-132">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4d1c7-132">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="4d1c7-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4d1c7-135">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="4d1c7-135">7/17/12012</span></span></p>
<p><span data-ttu-id="4d1c7-136">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-136">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4d1c7-137">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="4d1c7-137">7/13/2012</span></span></p>
<p><span data-ttu-id="4d1c7-138">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-138">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-139"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-139"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-p108">Date/heure de fin de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4d1c7-142">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4d1c7-142">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="4d1c7-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4d1c7-145">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="4d1c7-145">7/17/12012</span></span></p>
<p><span data-ttu-id="4d1c7-146">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4d1c7-147">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="4d1c7-147">7/13/2012</span></span></p>
<p><span data-ttu-id="4d1c7-148">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-149"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-149"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-p110">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-153"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-153"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-154">Type d’activité.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-154">Type of activity.</span></span> <span data-ttu-id="4d1c7-155">Sélectionnez l’une des activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-155">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d1c7-156">Tous les</span><span class="sxs-lookup"><span data-stu-id="4d1c7-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="4d1c7-157">Égal à égal</span><span class="sxs-lookup"><span data-stu-id="4d1c7-157">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="4d1c7-158">Conférence</span><span class="sxs-lookup"><span data-stu-id="4d1c7-158">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-159"><strong>Catégorie d’appel</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-159"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-160">Indique la raison pour laquelle le contrôle d’admission des appels a été utilisé pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-160">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="4d1c7-161">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4d1c7-161">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d1c7-162">Tous les</span><span class="sxs-lookup"><span data-stu-id="4d1c7-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="4d1c7-163">Appel rejeté en raison du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="4d1c7-163">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="4d1c7-164">Appels réacheminés via PSTN en raison du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="4d1c7-164">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="4d1c7-165">Mesures pour les sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="4d1c7-165">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="4d1c7-166">Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les sessions P2P (c’est-à-dire, les sessions qui n’impliquent que deux participants).</span><span class="sxs-lookup"><span data-stu-id="4d1c7-166">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="4d1c7-167">Mesures pour les sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="4d1c7-167">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1c7-168">Nom</span><span class="sxs-lookup"><span data-stu-id="4d1c7-168">Name</span></span></th>
<th><span data-ttu-id="4d1c7-169">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4d1c7-169">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4d1c7-170">Description</span><span class="sxs-lookup"><span data-stu-id="4d1c7-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-171"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-171"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-172">Non</span><span class="sxs-lookup"><span data-stu-id="4d1c7-172">No</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-173">Lorsque vous cliquez sur cet élément, le rapport vous montre un rapport détaillé de session P2P pour la session spécifiée.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-173">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-174"><strong>De l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-174"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-175">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-176">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-176">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-177"><strong>À l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-177"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-178">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-179">Adresse SIP de l’utilisateur qui a été invité à rejoindre la session.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-179">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-180"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-180"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-181">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-181">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-182">Modalités de communication (audio et vidéo, par exemple) qui ont été utilisées pendant la session.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-182">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-183"><strong>Heure d’invitation</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-183"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-184">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-185">Date et heure auxquelles l’invitation initiale à la session a été envoyée à l’utilisateur de.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-185">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-186"><strong>Heure de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-186"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-187">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-188">Date et heure auxquelles l’acceptation de l’invitation a été reçue.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-188">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-189"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-189"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-190">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-190">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-191">Date et heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-191">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-192"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-192"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-193">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-p113">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="4d1c7-196">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="4d1c7-196">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="4d1c7-197">Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les sessions de conférence (c’est-à-dire, les sessions qui impliquent trois participants ou plus).</span><span class="sxs-lookup"><span data-stu-id="4d1c7-197">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="4d1c7-198">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="4d1c7-198">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1c7-199">Nom</span><span class="sxs-lookup"><span data-stu-id="4d1c7-199">Name</span></span></th>
<th><span data-ttu-id="4d1c7-200">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4d1c7-200">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4d1c7-201">Description</span><span class="sxs-lookup"><span data-stu-id="4d1c7-201">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-202"><strong>URI de la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-202"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-203">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-204">Identificateur unique de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-204">Unique identifier for the conference.</span></span> <span data-ttu-id="4d1c7-205">Lorsque vous cliquez sur cet élément, le rapport affiche les participants individuels de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-205">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-206"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-206"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-207">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-208">Adresse SIP de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-208">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-209"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-209"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-210">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-211">Serveur Edge utilisé dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-211">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-212"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-212"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-213">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-214">Date et heure auxquelles la conférence a commencé.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-214">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-215"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-215"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-216">Oui</span><span class="sxs-lookup"><span data-stu-id="4d1c7-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-217">Date et heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-217">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="4d1c7-218">Mesures pour les participants à la Conférence individuelle</span><span class="sxs-lookup"><span data-stu-id="4d1c7-218">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="4d1c7-219">Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour chaque participant d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-219">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="4d1c7-220">Mesures pour les participants à la Conférence individuelle</span><span class="sxs-lookup"><span data-stu-id="4d1c7-220">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1c7-221">Nom</span><span class="sxs-lookup"><span data-stu-id="4d1c7-221">Name</span></span></th>
<th><span data-ttu-id="4d1c7-222">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4d1c7-222">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4d1c7-223">Description</span><span class="sxs-lookup"><span data-stu-id="4d1c7-223">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-224"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-224"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-225">Non</span><span class="sxs-lookup"><span data-stu-id="4d1c7-225">No</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-226">Rôle (par exemple, présentateur) joué par le participant à la conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-226">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-227"><strong>Participant</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-227"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-228">Non</span><span class="sxs-lookup"><span data-stu-id="4d1c7-228">No</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-229">Adresse SIP du participant à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-229">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-230"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-230"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-231">Non</span><span class="sxs-lookup"><span data-stu-id="4d1c7-231">No</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-232">Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-232">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-233"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-233"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-234">Non</span><span class="sxs-lookup"><span data-stu-id="4d1c7-234">No</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-235">Type de conférence (par exemple, conférence A/V).</span><span class="sxs-lookup"><span data-stu-id="4d1c7-235">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-236"><strong>Heure d’arrivée</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-236"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-237">Non</span><span class="sxs-lookup"><span data-stu-id="4d1c7-237">No</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-238">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-238">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1c7-239"><strong>Heure de départ</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-239"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-240">Non</span><span class="sxs-lookup"><span data-stu-id="4d1c7-240">No</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-241">Date et heure auxquelles le participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-241">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1c7-242"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="4d1c7-242"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1c7-243">Non</span><span class="sxs-lookup"><span data-stu-id="4d1c7-243">No</span></span></p></td>
<td><p><span data-ttu-id="4d1c7-p115">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="4d1c7-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

