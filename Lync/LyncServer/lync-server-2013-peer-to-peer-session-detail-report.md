---
title: 'Lync Server 2013 : rapport détaillé sur la session d’égal à égal'
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
ms.openlocfilehash: bff140db52a98e0b442ca65bbbb8b148282c5755
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="e0af2-102">Rapport détaillé sur la session d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0af2-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0af2-103">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e0af2-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e0af2-p101">Le rapport détaillé de session P2P renvoie des informations détaillées sur une session P2P. Par exemple, si vous sélectionnez une session de messagerie instantanée, le rapport indique le nombre de messages envoyés par chacun des deux utilisateurs dans la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="e0af2-106">Accès au rapport détaillé de session P2P</span><span class="sxs-lookup"><span data-stu-id="e0af2-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="e0af2-107">Vous pouvez accéder au rapport de détails de session P2P à partir de l’un des rapports suivants (disponibles en totalité dans la page d’accueil Rapports de surveillance) :</span><span class="sxs-lookup"><span data-stu-id="e0af2-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="e0af2-108">Rapport d’inventaire de téléphonie IP</span><span class="sxs-lookup"><span data-stu-id="e0af2-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="e0af2-109">Rapport d’activité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="e0af2-109">User Activity Report</span></span>

  - <span data-ttu-id="e0af2-110">Rapport de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="e0af2-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="e0af2-111">Rapport de liste des échecs</span><span class="sxs-lookup"><span data-stu-id="e0af2-111">Failure List Report</span></span>

<span data-ttu-id="e0af2-112">Dans le rapport détaillé de la session d’égal à égal, vous pouvez accéder au [rapport de diagnostic dans Lync Server 2013](lync-server-2013-diagnostic-report.md) en cliquant sur le rapport de diagnostic (détails) métrique.</span><span class="sxs-lookup"><span data-stu-id="e0af2-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="e0af2-113">Vous pouvez aussi accéder au rapport des principales défaillances en cliquant sur l’une de ces deux mesures :</span><span class="sxs-lookup"><span data-stu-id="e0af2-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="e0af2-114">Réponse</span><span class="sxs-lookup"><span data-stu-id="e0af2-114">Response</span></span>

  - <span data-ttu-id="e0af2-115">ID de diagnostic</span><span class="sxs-lookup"><span data-stu-id="e0af2-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="e0af2-116">Exploiter au mieux le rapport détaillé de session P2P</span><span class="sxs-lookup"><span data-stu-id="e0af2-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="e0af2-p103">Le rapport détaillé de session P2P comprend un grand nombre de mesures, dont bon nombre peuvent être inconnues des administrateurs système. Cependant, dans bien des cas, vous pouvez afficher une info-bulle qui offre une brève description de cette mesure en maintenant simplement votre souris sur l’étiquette de la mesure.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="e0af2-p104">Note que les mesures qui s’affichent sur un rapport donné dépendent du type de session P2P que vous avez sélectionné. Une session audio/vidéo et une session de messagerie instantanée n’affichent pas le même ensemble de mesures.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="e0af2-121">Vous pouvez également pointer votre souris sur les mesures Code de réponse et ID de diagnostic pour obtenir une description de ces valeurs :</span><span class="sxs-lookup"><span data-stu-id="e0af2-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e0af2-122">Filtres</span><span class="sxs-lookup"><span data-stu-id="e0af2-122">Filters</span></span>

<span data-ttu-id="e0af2-p105">Aucun. Vous ne pouvez pas filtrer le Rapport détaillé de session P2P.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="e0af2-125">Mesures des informations de session</span><span class="sxs-lookup"><span data-stu-id="e0af2-125">Session Information Metrics</span></span>

<span data-ttu-id="e0af2-126">Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P de chaque session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="e0af2-127">Mesures des informations de session</span><span class="sxs-lookup"><span data-stu-id="e0af2-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0af2-128">Nom</span><span class="sxs-lookup"><span data-stu-id="e0af2-128">Name</span></span></th>
<th><span data-ttu-id="e0af2-129">Description</span><span class="sxs-lookup"><span data-stu-id="e0af2-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-130"><strong>FQDN du pool</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-131">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge impliqué dans la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-132"><strong>Heure d’invitation</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-133">Date et heure auxquelles l’invitation a été envoyée à l’origine.</span><span class="sxs-lookup"><span data-stu-id="e0af2-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-134"><strong>Heure de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-135">Date et heure auxquelles l’acceptation de l’invitation a été reçue.</span><span class="sxs-lookup"><span data-stu-id="e0af2-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-136"><strong>De l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-137">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-138"><strong>Agent utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-139">Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-140"><strong>Interne à l’utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-141">Indique si l’utilisateur qui a initié la session était connecté au réseau interne.</span><span class="sxs-lookup"><span data-stu-id="e0af2-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-142"><strong>Utilisateur d’origine intégré au téléphone de bureau</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-143">Indique si le point de terminaison utilisé par l’utilisateur qui a démarré la session est intégré à son téléphone de bureau.</span><span class="sxs-lookup"><span data-stu-id="e0af2-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-144"><strong>Priorité de la session</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-p106">Priorité affectée à la session. Les priorités valides sont : Inconnu, Non urgent, Normal, Urgent et Urgence.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-147"><strong>Code de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-148">Code de réponse SIP envoyé lors de l’échec de session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-149"><strong>Serveur frontal</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-150">Nom du serveur frontal utilisé dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="e0af2-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-151"><strong>Délai de capture</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-152">Date et heure auxquelles les informations de session ont été enregistrées.</span><span class="sxs-lookup"><span data-stu-id="e0af2-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-153"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-154">Date et heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-155"><strong>À l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-156">Adresse IP de l’utilisateur ayant été invité à participer à la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-157"><strong>Agent utilisateur de destination</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-158">Logiciel utilisé par le point de terminaison de l’utilisateur qui a été invité à la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-159"><strong>Interne à l’utilisateur de destination</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-160">Indique si l’utilisateur qui a été invité à la session était connecté au réseau interne.</span><span class="sxs-lookup"><span data-stu-id="e0af2-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-161"><strong>Utilisateur de destination intégré au téléphone de bureau</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-162">Indique si le point de terminaison utilisé par l’utilisateur qui a été invité à la session est intégré à son téléphone de bureau.</span><span class="sxs-lookup"><span data-stu-id="e0af2-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-163"><strong>Nouvelle tentative de session</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-164">Indique si la session est une nouvelle tentative de session qui a précédemment échoué.</span><span class="sxs-lookup"><span data-stu-id="e0af2-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-165"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-p107">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles à l’identification et à la résolution des erreurs. Placez la souris au-dessus du numéro d’ID pour afficher des informations supplémentaires sur cet ID.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="e0af2-168">Mesures des modalités</span><span class="sxs-lookup"><span data-stu-id="e0af2-168">Metrics for Modalities</span></span>

<span data-ttu-id="e0af2-169">Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P de chaque modalité de session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="e0af2-170">Mesures des modalités</span><span class="sxs-lookup"><span data-stu-id="e0af2-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0af2-171">Nom</span><span class="sxs-lookup"><span data-stu-id="e0af2-171">Name</span></span></th>
<th><span data-ttu-id="e0af2-172">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="e0af2-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e0af2-173">Description</span><span class="sxs-lookup"><span data-stu-id="e0af2-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-174"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-175">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-175">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-p108">Modalités utilisées dans la session. Par exemple, messagerie instantanée ou transfert de fichier.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-178"><strong>Messages de l’expéditeur</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-179">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-179">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-180">Nombre de messages envoyés par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-181"><strong>Messages du destinataire</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-182">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-182">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-183">Nombre de messages envoyés par l’utilisateur qui a été invité à rejoindre la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="e0af2-184">Mesures pour les rapports de diagnostic</span><span class="sxs-lookup"><span data-stu-id="e0af2-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="e0af2-185">Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P pour chaque rapport de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="e0af2-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="e0af2-186">Mesures pour les rapports de diagnostic</span><span class="sxs-lookup"><span data-stu-id="e0af2-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0af2-187">Nom</span><span class="sxs-lookup"><span data-stu-id="e0af2-187">Name</span></span></th>
<th><span data-ttu-id="e0af2-188">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="e0af2-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e0af2-189">Description</span><span class="sxs-lookup"><span data-stu-id="e0af2-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-190"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-191">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-191">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-192">Lorsque vous cliquez sur cet élément, le rapport montre le rapport de diagnostic pour la session.</span><span class="sxs-lookup"><span data-stu-id="e0af2-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-193"><strong>Heure du rapport</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-194">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-194">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-195">Date et heure d’enregistrement du rapport.</span><span class="sxs-lookup"><span data-stu-id="e0af2-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-196"><strong>Demande</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-197">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-197">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-p109">Type de demande SIP. Par exemple, INVITE ou BYE.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-200"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-201">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-201">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-202">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs.</span><span class="sxs-lookup"><span data-stu-id="e0af2-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0af2-203"><strong>Type de contenu</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-204">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-204">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-p110">Type de contenu multimédia utilisé dans la conférence. Par exemple, Application/sdp est un type de contenu commun. Le protocole SDP (Session Description Protocol) est un protocole Internet standard utilisé pour les annonces de session, les invitations aux sessions et autres formes de démarrage de session multimédia.</span><span class="sxs-lookup"><span data-stu-id="e0af2-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0af2-208"><strong>Auteur du rapport</strong></span><span class="sxs-lookup"><span data-stu-id="e0af2-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="e0af2-209">Non</span><span class="sxs-lookup"><span data-stu-id="e0af2-209">No</span></span></p></td>
<td><p><span data-ttu-id="e0af2-210">Ordinateur (c’est-à-dire, client ou serveur) qui a signalé le problème.</span><span class="sxs-lookup"><span data-stu-id="e0af2-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

