---
title: 'Lync Server 2013 : rapport détaillé de session P2P'
description: 'Lync Server 2013 : rapport détaillé de session d’égal à égal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e712225fddabb646cc3b862f59601857a7df8eff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557280"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="12f6f-103">Rapport détaillé de session d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f6f-103">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12f6f-104">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="12f6f-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="12f6f-p101">Le rapport détaillé de session d’égal à égal retourne des informations détaillées sur une session d’égal à égal. Par exemple, si vous sélectionnez une session de messagerie instantanée, le rapport indique le nombre de messages envoyés par chacun des deux utilisateurs dans la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="12f6f-107">Accès au rapport détaillé de session d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="12f6f-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="12f6f-108">Vous pouvez accéder au rapport de détails de session d’égal à égal à partir de l’un des rapports suivants (disponibles en totalité dans la page d’accueil Rapports de surveillance) :</span><span class="sxs-lookup"><span data-stu-id="12f6f-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="12f6f-109">Rapport d’inventaire de téléphonie IP</span><span class="sxs-lookup"><span data-stu-id="12f6f-109">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="12f6f-110">Rapport d’activité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="12f6f-110">User Activity Report</span></span>

  - <span data-ttu-id="12f6f-111">Rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="12f6f-111">Call Admission Control Report</span></span>

  - <span data-ttu-id="12f6f-112">Rapport de liste des échecs</span><span class="sxs-lookup"><span data-stu-id="12f6f-112">Failure List Report</span></span>

<span data-ttu-id="12f6f-113">À partir du rapport détaillé de session P2P, vous pouvez accéder au [rapport de diagnostic dans Lync Server 2013](lync-server-2013-diagnostic-report.md) en cliquant sur la mesure rapport de diagnostic (détails).</span><span class="sxs-lookup"><span data-stu-id="12f6f-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="12f6f-114">Vous pouvez aussi accéder au rapport des principales défaillances en cliquant sur l’une de ces deux mesures :</span><span class="sxs-lookup"><span data-stu-id="12f6f-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="12f6f-115">Réponse</span><span class="sxs-lookup"><span data-stu-id="12f6f-115">Response</span></span>

  - <span data-ttu-id="12f6f-116">ID de diagnostic</span><span class="sxs-lookup"><span data-stu-id="12f6f-116">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="12f6f-117">Exploiter au mieux le rapport détaillé de session d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="12f6f-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="12f6f-p103">Le rapport détaillé de session d’égal à égal comprend un grand nombre de mesures, dont bon nombre peuvent être inconnues des administrateurs système. Toutefois, dans bien des cas, vous pouvez afficher une info-bulle qui offre une brève description de cette mesure en maintenant simplement votre souris sur l’étiquette de la mesure.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="12f6f-p104">Note que les mesures qui apparaissent sur un rapport donné dépendent du type de session d’égal à égal que vous avez sélectionné. Une session audio/vidéo et une session de messagerie instantanée n’affichent pas le même ensemble de mesures.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="12f6f-122">Vous pouvez également pointer votre souris sur les mesures Code de réponse et ID de diagnostic pour obtenir une description de ces valeurs :</span><span class="sxs-lookup"><span data-stu-id="12f6f-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="12f6f-123">Filtres</span><span class="sxs-lookup"><span data-stu-id="12f6f-123">Filters</span></span>

<span data-ttu-id="12f6f-p105">Aucun. Vous ne pouvez pas filtrer le Rapport détaillé de session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="12f6f-126">Mesures des informations de session</span><span class="sxs-lookup"><span data-stu-id="12f6f-126">Session Information Metrics</span></span>

<span data-ttu-id="12f6f-127">Le tableau suivant liste les informations fournies dans le Rapport détaillé de session d’égal à égal de chaque session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="12f6f-128">Mesures des informations de session</span><span class="sxs-lookup"><span data-stu-id="12f6f-128">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12f6f-129">Nom</span><span class="sxs-lookup"><span data-stu-id="12f6f-129">Name</span></span></th>
<th><span data-ttu-id="12f6f-130">Description</span><span class="sxs-lookup"><span data-stu-id="12f6f-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-131"><strong>FQDN du pool</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-131"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-132">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge impliqué dans la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-133"><strong>Heure d’invitation</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-133"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-134">Date et heure auxquelles l’invitation a été envoyée à l’origine.</span><span class="sxs-lookup"><span data-stu-id="12f6f-134">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-135"><strong>Heure de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-135"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-136">Date et heure auxquelles l’acceptation de l’invitation a été reçue.</span><span class="sxs-lookup"><span data-stu-id="12f6f-136">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-137"><strong>De l’utilisateur </strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-137"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-138">Adresse SIP de l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-138">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-139"><strong>Agent utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-139"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-140">Logiciel utilisé par le système d’extrémité de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-140">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-141"><strong>Interne à l’utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-141"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-142">Indique si l’utilisateur qui a initié la session était connecté au réseau interne.</span><span class="sxs-lookup"><span data-stu-id="12f6f-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-143"><strong>Utilisateur d’origine intégré au téléphone de bureau</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-143"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-144">Indique si le système d’extrémité utilisé par l’utilisateur qui a démarré la session est intégré avec son téléphone de bureau.</span><span class="sxs-lookup"><span data-stu-id="12f6f-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-145"><strong>Priorité de la session</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-145"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-p106">Priorité assignée à la session. Les priorités valides sont : Inconnu, Non urgent, Normal, Urgent et Urgence.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-148"><strong>Code de réponse </strong>.</span><span class="sxs-lookup"><span data-stu-id="12f6f-148"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-149">Code de réponse SIP envoyé lors de l’échec de la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-149">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-150"><strong>Frontal</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-150"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-151">Nom du serveur frontal utilisé dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="12f6f-151">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-152"><strong>Délai de capture</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-152"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-153">Date et heure auxquelles les informations de session ont été enregistrées.</span><span class="sxs-lookup"><span data-stu-id="12f6f-153">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-154"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-154"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-155">Date et heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-155">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-156"><strong>À l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-156"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-157">Adresse SIP de l’utilisateur invité à la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-157">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-158"><strong>Agent utilisateur de destination</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-158"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-159">Logiciel utilisé par le système d’extrémité de l’utilisateur qui a été invité à la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-159">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-160"><strong>Interne à l’utilisateur de destination</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-160"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-161">Indique si l’utilisateur qui a été invité à la session était connecté au réseau interne.</span><span class="sxs-lookup"><span data-stu-id="12f6f-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-162"><strong>Utilisateur de destination intégré au téléphone de bureau</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-162"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-163">Indique si le système d’extrémité utilisé par l’utilisateur qui a été invité à la session est intégré avec son téléphone de bureau.</span><span class="sxs-lookup"><span data-stu-id="12f6f-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-164"><strong>Nouvelle tentative de session</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-164"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-165">Indique si la session est une nouvelle tentative de session qui a précédemment échoué.</span><span class="sxs-lookup"><span data-stu-id="12f6f-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-166"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-166"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-p107">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Placez la souris au-dessus du numéro d’ID pour afficher des informations supplémentaires sur cet ID.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="12f6f-169">Mesures des modalités</span><span class="sxs-lookup"><span data-stu-id="12f6f-169">Metrics for Modalities</span></span>

<span data-ttu-id="12f6f-170">Le tableau suivant liste les informations fournies dans le Rapport détaillé de session d’égal à égal de chaque modalité de session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="12f6f-171">Mesures des modalités</span><span class="sxs-lookup"><span data-stu-id="12f6f-171">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12f6f-172">Nom</span><span class="sxs-lookup"><span data-stu-id="12f6f-172">Name</span></span></th>
<th><span data-ttu-id="12f6f-173">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="12f6f-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="12f6f-174">Description</span><span class="sxs-lookup"><span data-stu-id="12f6f-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-175"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-175"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-176">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-176">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-p108">Modalités utilisées dans la session. Par exemple, messagerie instantanée ou transfert de fichier.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-179"><strong>Messages de l’expéditeur</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-179"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-180">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-180">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-181">Nombre de messages envoyés par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-181">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-182"><strong>Messages du destinataire</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-182"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-183">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-183">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-184">Nombre de messages envoyés par l’utilisateur qui a été invité à rejoindre la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-184">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="12f6f-185">Mesures pour les rapports de diagnostic</span><span class="sxs-lookup"><span data-stu-id="12f6f-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="12f6f-186">Le tableau suivant liste les informations fournies dans le Rapport détaillé de session d’égal à égal pour chaque rapport de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="12f6f-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="12f6f-187">Mesures pour les rapports de diagnostic</span><span class="sxs-lookup"><span data-stu-id="12f6f-187">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12f6f-188">Nom</span><span class="sxs-lookup"><span data-stu-id="12f6f-188">Name</span></span></th>
<th><span data-ttu-id="12f6f-189">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="12f6f-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="12f6f-190">Description</span><span class="sxs-lookup"><span data-stu-id="12f6f-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-191"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-191"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-192">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-192">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-193">Lorsque vous cliquez sur cet élément, le rapport montre le rapport de diagnostic pour la session.</span><span class="sxs-lookup"><span data-stu-id="12f6f-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-194"><strong>Heure du rapport</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-194"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-195">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-195">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-196">Date et heure d’enregistrement du rapport.</span><span class="sxs-lookup"><span data-stu-id="12f6f-196">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-197"><strong>Demande</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-197"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-198">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-198">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-p109">Type de demande SIP. Par exemple, INVITE ou BYE.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-201"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-201"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-202">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-202">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-203">Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="12f6f-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12f6f-204"><strong>Type de contenu</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-204"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-205">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-205">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-p110">Type de contenu multimédia utilisé dans la conférence. Par exemple, Application/sdp est un type de contenu commun. Le protocole SDP (Session Description Protocol) est un protocole Internet standard utilisé pour les annonces de session, les invitations aux sessions et autres formes de démarrage de session multimédia.</span><span class="sxs-lookup"><span data-stu-id="12f6f-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f6f-209"><strong>Auteur du rapport</strong></span><span class="sxs-lookup"><span data-stu-id="12f6f-209"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="12f6f-210">Non</span><span class="sxs-lookup"><span data-stu-id="12f6f-210">No</span></span></p></td>
<td><p><span data-ttu-id="12f6f-211">Ordinateur (c’est-à-dire, client ou serveur) qui a signalé le problème.</span><span class="sxs-lookup"><span data-stu-id="12f6f-211">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

