---
title: 'Lync Server 2013 : rapport Détails de la Conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e2cd992e83adb29c43935d4b4c7f223580d53
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="f40db-102">Rapport Détails de la Conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f40db-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f40db-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f40db-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f40db-p101">Le rapport détaillé de conférence donne des informations détaillées sur tous les utilisateurs qui ont participé à une conférence. Vous pouvez par exemple voir des informations, telles que la date et l’heure auxquelles un utilisateur s’est joint à la conférence, la date et l’heure auxquelles l’utilisateur a quitté la conférence et l’agent utilisateur du point de terminaison qui a permis à l’utilisateur de se connecter à la conférence. Vous pouvez également afficher des informations sur le rôle de l’utilisateur dans chaque conférence (par exemple présentateur ou participant). Ce qui est peut-être le plus important, vous pouvez voir rapidement quels utilisateurs ont réussi à rejoindre et suivre la conférence et quels utilisateurs n’ont pas réussi à rejoindre et suivre la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="f40db-108">Accès au rapport détaillé de conférence</span><span class="sxs-lookup"><span data-stu-id="f40db-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="f40db-109">Le rapport détaillé de conférence est accessible à partir des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="f40db-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="f40db-110">[Rapport de contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-call-admission-control-report.md) (en cliquant sur la métrique détaillée pour une conférence)</span><span class="sxs-lookup"><span data-stu-id="f40db-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="f40db-111">[Rapport de la liste des échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md) (en cliquant sur la mesure de conférence)</span><span class="sxs-lookup"><span data-stu-id="f40db-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="f40db-112">[Rapport activité de l’utilisateur dans Lync Server 2013](lync-server-2013-user-activity-report.md) (en cliquant sur la métrique de l’URI de la Conférence)</span><span class="sxs-lookup"><span data-stu-id="f40db-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="f40db-113">À partir du rapport Détails de la Conférence, vous pouvez accéder au [rapport de diagnostic dans Lync Server 2013](lync-server-2013-diagnostic-report.md) en cliquant sur le rapport de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="f40db-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f40db-114">Filtres</span><span class="sxs-lookup"><span data-stu-id="f40db-114">Filters</span></span>

<span data-ttu-id="f40db-p102">Aucun. Vous ne pouvez pas filtrer sur le rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f40db-117">Mesures</span><span class="sxs-lookup"><span data-stu-id="f40db-117">Metrics</span></span>

<span data-ttu-id="f40db-118">Le tableau qui suit répertorie les informations fournies dans la section Informations de conférence du rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="f40db-119">Mesures des informations de conférence</span><span class="sxs-lookup"><span data-stu-id="f40db-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f40db-120">Nom</span><span class="sxs-lookup"><span data-stu-id="f40db-120">Name</span></span></th>
<th><span data-ttu-id="f40db-121">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="f40db-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f40db-122">Description</span><span class="sxs-lookup"><span data-stu-id="f40db-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f40db-123"><strong>URI de la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-p103">URI affectée à la conférence. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f40db-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="f40db-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="f40db-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f40db-127"><strong>FQDN du pool</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-128">Nom de domaine complet du pool de serveurs d’inscriptions ou serveur Edge impliqué dans une session.</span><span class="sxs-lookup"><span data-stu-id="f40db-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f40db-129"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-130">Date et heure auxquelles la conférence a commencé.</span><span class="sxs-lookup"><span data-stu-id="f40db-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f40db-131"><strong>Organisateur</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-132">Adresse SIP de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f40db-133"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-134">Date et heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f40db-135">Le tableau qui suit répertorie les informations fournies dans la section Participation à la conférence du rapport détaille de conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="f40db-136">Mesures de participation à la conférence</span><span class="sxs-lookup"><span data-stu-id="f40db-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f40db-137">Nom</span><span class="sxs-lookup"><span data-stu-id="f40db-137">Name</span></span></th>
<th><span data-ttu-id="f40db-138">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="f40db-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f40db-139">Description</span><span class="sxs-lookup"><span data-stu-id="f40db-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f40db-140"><strong>Utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-141">Adresse SIP de l’utilisateur qui a participé à la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f40db-142"><strong>Rôle</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-143">Rôle (par exemple, présentateur) joué par le participant à la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f40db-144"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-145">Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</span><span class="sxs-lookup"><span data-stu-id="f40db-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f40db-146">Heure d’arrivée</span><span class="sxs-lookup"><span data-stu-id="f40db-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-147">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f40db-148"><strong>Heure de départ</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-149">Date et heure auxquelles le participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f40db-150"><strong>Agent utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-151">Identifiant du logiciel utilisé par le point de terminaison du participant.</span><span class="sxs-lookup"><span data-stu-id="f40db-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f40db-152"><strong>Rapports de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-p104">Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="f40db-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f40db-155">Le tableau suivant répertorie les informations fournies dans la section modalités de la Conférence du rapport Détails de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="f40db-156">Mesures des modalités de conférence</span><span class="sxs-lookup"><span data-stu-id="f40db-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f40db-157">Nom</span><span class="sxs-lookup"><span data-stu-id="f40db-157">Name</span></span></th>
<th><span data-ttu-id="f40db-158">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="f40db-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f40db-159">Description</span><span class="sxs-lookup"><span data-stu-id="f40db-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f40db-160"><strong>Utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-161">Adresse SIP de l’utilisateur qui a participé à la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f40db-162"><strong>Heure d’arrivée</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-163">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f40db-164"><strong>Heure de départ</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-165">Date et heure auxquelles un participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f40db-166"><strong>URI du serveur de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-167">URI du serveur de conférence utilisé dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="f40db-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f40db-168"><strong>Rapports de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="f40db-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f40db-p105">Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="f40db-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

