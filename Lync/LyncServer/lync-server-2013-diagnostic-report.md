---
title: 'Lync Server 2013 : rapport de diagnostic'
description: 'Lync Server 2013 : rapport de diagnostic.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198b836437285b464ba9172e59c9a60ed0a53b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576250"
---
# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="32b7e-103">Rapport de diagnostic dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32b7e-103">Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32b7e-104">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="32b7e-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="32b7e-105">Le Rapport de diagnostic fournit des informations de diagnostic et de dépannage pour les sessions ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="32b7e-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="32b7e-106">Ces informations incluent à la fois l’ID de diagnostic et l’en-tête de diagnostic qui ont été signalés lorsque la session a échoué.</span><span class="sxs-lookup"><span data-stu-id="32b7e-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="32b7e-107">L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête ms-diagnostics) qui est joint à un message SIP, tandis que l’en-tête de diagnostic fournit une description d’accompagnement pour l’ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="32b7e-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="32b7e-108">Ce rapport peut également contenir des informations de dépannage précieuses qui sont connues par le composant de rapport.</span><span class="sxs-lookup"><span data-stu-id="32b7e-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="32b7e-109">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="32b7e-109">For example:</span></span>

  - <span data-ttu-id="32b7e-p102">Code de motif fourni par la passerelle PSTN qui a généré la défaillance. Quand un appel sortant échoue sur le réseau téléphonique commuté, un code de motif de la « partie Usager RNIS » (ISUP) est automatiquement généré. Par exemple, une passerelle PSTN peut retourner le code de motif 34, indiquant ainsi qu’aucun circuit ou canal n’était disponible pour terminer l’appel.</span><span class="sxs-lookup"><span data-stu-id="32b7e-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="32b7e-113">Nom de domaine complet (FQDN), port et erreurs Winsock de l’homologue pour les échecs de connectivité.</span><span class="sxs-lookup"><span data-stu-id="32b7e-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="32b7e-p103">Noms recherchés pour les échecs de résolution DNS. La résolution DNS a lieu chaque fois qu’un client contacte un serveur de noms et demande l’adresse IP correspondant au nom du périphérique spécifié</span><span class="sxs-lookup"><span data-stu-id="32b7e-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="32b7e-116">Accès au Rapport de diagnostic</span><span class="sxs-lookup"><span data-stu-id="32b7e-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="32b7e-117">Le rapport de diagnostic est accessible en cliquant sur la mesure rapport de diagnostic (détail) sur le [rapport détaillé de session P2P dans Lync Server 2013 ou dans](lync-server-2013-peer-to-peer-session-detail-report.md) le rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b7e-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="32b7e-118">Filtres</span><span class="sxs-lookup"><span data-stu-id="32b7e-118">Filters</span></span>

<span data-ttu-id="32b7e-p104">Aucun. Il est impossible de filtrer le rapport de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="32b7e-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="32b7e-121">Mesures</span><span class="sxs-lookup"><span data-stu-id="32b7e-121">Metrics</span></span>

<span data-ttu-id="32b7e-122">Le tableau qui suit répertorie les informations fournies dans le rapport de diagnostic pour chaque session.</span><span class="sxs-lookup"><span data-stu-id="32b7e-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="32b7e-123">Mesures du rapport de diagnostic</span><span class="sxs-lookup"><span data-stu-id="32b7e-123">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32b7e-124">Nom</span><span class="sxs-lookup"><span data-stu-id="32b7e-124">Name</span></span></th>
<th><span data-ttu-id="32b7e-125">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="32b7e-125">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="32b7e-126">Description</span><span class="sxs-lookup"><span data-stu-id="32b7e-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32b7e-127"><strong>Heure du rapport</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-127"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-128">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-128">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-129">Date et heure d’enregistrement du rapport.</span><span class="sxs-lookup"><span data-stu-id="32b7e-129">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b7e-130"><strong>Code de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-130"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-131">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-131">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-132">Code de réponse SIP envoyé lors de l’échec de session.</span><span class="sxs-lookup"><span data-stu-id="32b7e-132">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b7e-133"><strong>Type de demande</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-133"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-134">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-134">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-p105">Type de demande SIP ayant échoué. Par exemple, INVITE, BYE ou SERVICE.</span><span class="sxs-lookup"><span data-stu-id="32b7e-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b7e-137"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-137"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-138">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-138">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-139">Source de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="32b7e-139">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b7e-140"><strong>URI de l’utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-140"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-141">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-141">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-142">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="32b7e-142">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b7e-143"><strong>Agent utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-143"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-144">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-144">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-145">Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="32b7e-145">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b7e-146"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-146"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-147">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-147">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-148">Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="32b7e-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b7e-149"><strong>Type de contenu</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-149"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-150">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-150">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-p106">Type de contenu multimédia ayant échoué. Par exemple, un type de contenu courant est Application/sdp. Session Description Protocol (SDP) est un protocole Internet standard utilisé pour les annonces de session, les invitations de session et autres formes d’initiation de session multimédia.</span><span class="sxs-lookup"><span data-stu-id="32b7e-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b7e-154"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-154"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-155">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-155">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-156">Application impliquée dans l’erreur.</span><span class="sxs-lookup"><span data-stu-id="32b7e-156">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b7e-157"><strong>URI de l’utilisateur de destination</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-157"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-158">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-158">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-159">Adresse IP de l’utilisateur ayant été invité à participer à la session.</span><span class="sxs-lookup"><span data-stu-id="32b7e-159">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b7e-160">Temps de connexion à la conférence (ms)</span><span class="sxs-lookup"><span data-stu-id="32b7e-160">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="32b7e-161">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-161">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-162">Temps (en millisecondes) utilisé pour que l’utilisateur rejoigne la conférence.</span><span class="sxs-lookup"><span data-stu-id="32b7e-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b7e-163"><strong>En-tête de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="32b7e-163"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="32b7e-164">Non</span><span class="sxs-lookup"><span data-stu-id="32b7e-164">No</span></span></p></td>
<td><p><span data-ttu-id="32b7e-165">Description de l’ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="32b7e-165">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32b7e-166">Une liste des erreurs de diagnostic se trouve dans la [page d’en-tête MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="32b7e-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

