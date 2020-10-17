---
title: 'Lync Server 2013 : rapport de diagnostic'
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
ms.openlocfilehash: a6eb6de7f2ba23d52a7b508869dbb25c9c5e3802
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514491"
---
# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="6e7ba-102">Rapport de diagnostic dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e7ba-102">Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e7ba-103">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="6e7ba-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="6e7ba-104">Le Rapport de diagnostic fournit des informations de diagnostic et de dépannage pour les sessions ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="6e7ba-105">Ces informations incluent à la fois l’ID de diagnostic et l’en-tête de diagnostic qui ont été signalés lorsque la session a échoué.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="6e7ba-106">L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête ms-diagnostics) qui est joint à un message SIP, tandis que l’en-tête de diagnostic fournit une description d’accompagnement pour l’ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="6e7ba-107">Ce rapport peut également contenir des informations de dépannage précieuses qui sont connues par le composant de rapport.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="6e7ba-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6e7ba-108">For example:</span></span>

  - <span data-ttu-id="6e7ba-p102">Code de motif fourni par la passerelle PSTN qui a généré la défaillance. Quand un appel sortant échoue sur le réseau téléphonique commuté, un code de motif de la « partie Usager RNIS » (ISUP) est automatiquement généré. Par exemple, une passerelle PSTN peut retourner le code de motif 34, indiquant ainsi qu’aucun circuit ou canal n’était disponible pour terminer l’appel.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="6e7ba-112">Nom de domaine complet (FQDN), port et erreurs Winsock de l’homologue pour les échecs de connectivité.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="6e7ba-p103">Noms recherchés pour les échecs de résolution DNS. La résolution DNS a lieu chaque fois qu’un client contacte un serveur de noms et demande l’adresse IP correspondant au nom du périphérique spécifié</span><span class="sxs-lookup"><span data-stu-id="6e7ba-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="6e7ba-115">Accès au Rapport de diagnostic</span><span class="sxs-lookup"><span data-stu-id="6e7ba-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="6e7ba-116">Le rapport de diagnostic est accessible en cliquant sur la mesure rapport de diagnostic (détail) sur le [rapport détaillé de session P2P dans Lync Server 2013 ou dans](lync-server-2013-peer-to-peer-session-detail-report.md) le rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6e7ba-117">Filtres</span><span class="sxs-lookup"><span data-stu-id="6e7ba-117">Filters</span></span>

<span data-ttu-id="6e7ba-p104">Aucun. Il est impossible de filtrer le rapport de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="6e7ba-120">Mesures</span><span class="sxs-lookup"><span data-stu-id="6e7ba-120">Metrics</span></span>

<span data-ttu-id="6e7ba-121">Le tableau qui suit répertorie les informations fournies dans le rapport de diagnostic pour chaque session.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="6e7ba-122">Mesures du rapport de diagnostic</span><span class="sxs-lookup"><span data-stu-id="6e7ba-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e7ba-123">Nom</span><span class="sxs-lookup"><span data-stu-id="6e7ba-123">Name</span></span></th>
<th><span data-ttu-id="6e7ba-124">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="6e7ba-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6e7ba-125">Description</span><span class="sxs-lookup"><span data-stu-id="6e7ba-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e7ba-126"><strong>Heure du rapport</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-127">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-127">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-128">Date et heure d’enregistrement du rapport.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7ba-129"><strong>Code de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-130">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-130">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-131">Code de réponse SIP envoyé lors de l’échec de session.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7ba-132"><strong>Type de demande</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-133">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-133">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-p105">Type de demande SIP ayant échoué. Par exemple, INVITE, BYE ou SERVICE.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7ba-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-137">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-137">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-138">Source de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7ba-139"><strong>URI de l’utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-140">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-140">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-141">Adresse SIP de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7ba-142"><strong>Agent utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-143">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-143">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-144">Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié la session.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7ba-145"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-146">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-146">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-147">Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7ba-148"><strong>Type de contenu</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-149">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-149">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-p106">Type de contenu multimédia ayant échoué. Par exemple, un type de contenu courant est Application/sdp. Session Description Protocol (SDP) est un protocole Internet standard utilisé pour les annonces de session, les invitations de session et autres formes d’initiation de session multimédia.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7ba-153"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-154">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-154">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-155">Application impliquée dans l’erreur.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7ba-156"><strong>URI de l’utilisateur de destination</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-157">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-157">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-158">Adresse IP de l’utilisateur ayant été invité à participer à la session.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7ba-159">Temps de connexion à la conférence (ms)</span><span class="sxs-lookup"><span data-stu-id="6e7ba-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-160">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-160">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-161">Temps (en millisecondes) utilisé pour que l’utilisateur rejoigne la conférence.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7ba-162"><strong>En-tête de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="6e7ba-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="6e7ba-163">Non</span><span class="sxs-lookup"><span data-stu-id="6e7ba-163">No</span></span></p></td>
<td><p><span data-ttu-id="6e7ba-164">Description de l’ID de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="6e7ba-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6e7ba-165">Une liste des erreurs de diagnostic se trouve dans la [page d’en-tête MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="6e7ba-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

