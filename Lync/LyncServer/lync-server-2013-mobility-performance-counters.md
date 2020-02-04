---
title: 'Lync Server 2013 : compteurs de performances de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 439c179476c89de8a5245e80e26586d42f4f6e3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="9019f-102">Compteurs de performance de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9019f-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9019f-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="9019f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="9019f-104">Les tableaux suivants répertorient les noms et descriptions des compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API Unified Communications Web API (UCWA) et le service de mobilité MCX de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9019f-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="9019f-105">Le nom de la catégorie pour les compteurs dans le tableau UCWA est **LS:WEB – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="9019f-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="9019f-106">Le nom de la catégorie pour les compteurs dans le tableau Service de mobilité Mcx est **LS:WEB - Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="9019f-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="9019f-107">Compteurs de performances pour UCWA</span><span class="sxs-lookup"><span data-stu-id="9019f-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9019f-108">Compteur</span><span class="sxs-lookup"><span data-stu-id="9019f-108">Counter</span></span></th>
<th><span data-ttu-id="9019f-109">Description</span><span class="sxs-lookup"><span data-stu-id="9019f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9019f-110">Active Application Count</span><span class="sxs-lookup"><span data-stu-id="9019f-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-111">Nombre d’applications en cours</span><span class="sxs-lookup"><span data-stu-id="9019f-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-112">Active Application Sharing Modality Count</span><span class="sxs-lookup"><span data-stu-id="9019f-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-113">Nombre actuel de modalités de partage d’applications</span><span class="sxs-lookup"><span data-stu-id="9019f-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-114">Active Audio Modality Count</span><span class="sxs-lookup"><span data-stu-id="9019f-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-115">Nombre actuel de modalités audio</span><span class="sxs-lookup"><span data-stu-id="9019f-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-116">Active Data Collaboration Modality Count</span><span class="sxs-lookup"><span data-stu-id="9019f-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-117">Nombre actuel de modalités de collaboration de données</span><span class="sxs-lookup"><span data-stu-id="9019f-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-118">Active Directory Photo Get Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="9019f-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="9019f-119">Ce compteur montre le temps moyen (en millisecondes) nécessaire pour récupérer une photo du répertoire actif.</span><span class="sxs-lookup"><span data-stu-id="9019f-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-120">Active Messaging Modality Count</span><span class="sxs-lookup"><span data-stu-id="9019f-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-121">Nombre actuel de modalités de messagerie</span><span class="sxs-lookup"><span data-stu-id="9019f-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-122">Active Panoramic Video Modality Count</span><span class="sxs-lookup"><span data-stu-id="9019f-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-123">Nombre actuel de modalités de vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="9019f-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-124">Active Pending Get Count</span><span class="sxs-lookup"><span data-stu-id="9019f-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-125">Nombre de gets actifs en attente ; connexions au serveur conservées depuis longtemps</span><span class="sxs-lookup"><span data-stu-id="9019f-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-126">Active Session Count</span><span class="sxs-lookup"><span data-stu-id="9019f-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-127">Nombre actuel de points de terminaison enregistrés dans UCWA par application et le total</span><span class="sxs-lookup"><span data-stu-id="9019f-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-128">Active User Instance Count</span><span class="sxs-lookup"><span data-stu-id="9019f-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-129">Nombre d’instances utilisateur en cours</span><span class="sxs-lookup"><span data-stu-id="9019f-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-130">Active User Instances without Application</span><span class="sxs-lookup"><span data-stu-id="9019f-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="9019f-131">Nombre d’instances utilisateur en cours sans application</span><span class="sxs-lookup"><span data-stu-id="9019f-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-132">Active Video Modality Count</span><span class="sxs-lookup"><span data-stu-id="9019f-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-133">Nombre actuel de modalités vidéo</span><span class="sxs-lookup"><span data-stu-id="9019f-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-134">Application Creation Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="9019f-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-135">Taux par seconde de demandes de création d’application reçues</span><span class="sxs-lookup"><span data-stu-id="9019f-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-136">AS MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="9019f-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-137">Nombre d’échecs de connexion au service MCU AS</span><span class="sxs-lookup"><span data-stu-id="9019f-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-138">AV MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="9019f-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-139">Nombre d’échecs de connexion au service MCU audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="9019f-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-140">Average Application Startup Time (ms)</span><span class="sxs-lookup"><span data-stu-id="9019f-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="9019f-141">Délai de démarrage moyen de l’application en millisecondes</span><span class="sxs-lookup"><span data-stu-id="9019f-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-142">Average Lifetime for Session (ms)</span><span class="sxs-lookup"><span data-stu-id="9019f-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="9019f-143">Durée de vie moyenne pour une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="9019f-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-144">Data MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="9019f-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-145">Nombre d’échecs de connexion au service MCU de données</span><span class="sxs-lookup"><span data-stu-id="9019f-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-146">Exchange Contact Search Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="9019f-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="9019f-147">Ce compteur affiche le temps moyen (en millisecondes) nécessaire pour rechercher des contacts dans Exchange</span><span class="sxs-lookup"><span data-stu-id="9019f-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-148">Exchange HD Photo Get Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="9019f-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="9019f-149">Ce compteur affiche le temps moyen (en millisecondes) nécessaire pour récupérer une photo HD d’Exchange</span><span class="sxs-lookup"><span data-stu-id="9019f-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-150">HTTP 4xx Responses/Second</span><span class="sxs-lookup"><span data-stu-id="9019f-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-151">Taux de réponses avec un code 4xx HTTP par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-152">HTTP 5xx Responses/Second</span><span class="sxs-lookup"><span data-stu-id="9019f-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-153">Taux de réponses avec un code 5xx HTTP par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-154">IM MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="9019f-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-155">Nombre d’échecs de connexion au service MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="9019f-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-156">Number of Active Directory Photo Get Failures</span><span class="sxs-lookup"><span data-stu-id="9019f-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-157">Nombre d’échecs de récupération de photos du répertoire actif</span><span class="sxs-lookup"><span data-stu-id="9019f-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-158">Number of Contact Search failures</span><span class="sxs-lookup"><span data-stu-id="9019f-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-159">Nombre total d’échecs de recherche de contacts dans Exchange</span><span class="sxs-lookup"><span data-stu-id="9019f-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-160">Number of Deserialization Failures</span><span class="sxs-lookup"><span data-stu-id="9019f-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-161">Nombre total d’échecs de désérialisation</span><span class="sxs-lookup"><span data-stu-id="9019f-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-162">Nombre d’échecs de photo HD</span><span class="sxs-lookup"><span data-stu-id="9019f-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-163">Nombre total d’échecs de récupération de photos HD depuis Exchange</span><span class="sxs-lookup"><span data-stu-id="9019f-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-164">Over The Maximum Subscriptions Per Application</span><span class="sxs-lookup"><span data-stu-id="9019f-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="9019f-165">Nombre de requêtes d’abonnement dépassant le nombre maximal autorisé par application</span><span class="sxs-lookup"><span data-stu-id="9019f-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-166">Over The Maximum Subscriptions Per Batch</span><span class="sxs-lookup"><span data-stu-id="9019f-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="9019f-167">Nombre de requêtes d’abonnement dépassant le nombre maximal autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="9019f-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-168">Presence Subscription Failures</span><span class="sxs-lookup"><span data-stu-id="9019f-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-169">Nombre d’échecs d’abonnement de présence</span><span class="sxs-lookup"><span data-stu-id="9019f-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-170">Registering Endpoint Failures</span><span class="sxs-lookup"><span data-stu-id="9019f-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="9019f-171">Nombre d’échecs d’enregistrement de points de terminaison</span><span class="sxs-lookup"><span data-stu-id="9019f-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-172">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="9019f-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-173">Taux de demandes reçues par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-174">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="9019f-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-175">Taux de demandes réussies par seconde (codes de réponse 2xx/3xx HTTP)</span><span class="sxs-lookup"><span data-stu-id="9019f-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-176">Succeeded Create Application Requests/Second</span><span class="sxs-lookup"><span data-stu-id="9019f-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-177">Taux de demandes de création d’application réussies par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-178">Timed Out Pending Get Count</span><span class="sxs-lookup"><span data-stu-id="9019f-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-179">Nombre de gets en attente ayant expiré</span><span class="sxs-lookup"><span data-stu-id="9019f-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-180">Total Application Creation Requests Received</span><span class="sxs-lookup"><span data-stu-id="9019f-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="9019f-181">Nombre total de demandes de création d’application reçues depuis le démarrage du service</span><span class="sxs-lookup"><span data-stu-id="9019f-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-182">Total HTTP 4xx Responses</span><span class="sxs-lookup"><span data-stu-id="9019f-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="9019f-183">Nombre total de réponses 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="9019f-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-184">Total HTTP 5xx Responses</span><span class="sxs-lookup"><span data-stu-id="9019f-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="9019f-185">Nombre total de réponses 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="9019f-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-186">Total Requests Received on the Command Channel</span><span class="sxs-lookup"><span data-stu-id="9019f-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="9019f-187">Nombre total de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="9019f-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-188">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="9019f-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="9019f-189">Nombre total de demandes réussies</span><span class="sxs-lookup"><span data-stu-id="9019f-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-190">Total Sessions Initiated</span><span class="sxs-lookup"><span data-stu-id="9019f-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="9019f-191">Nombre total de sessions initiées depuis le démarrage du service</span><span class="sxs-lookup"><span data-stu-id="9019f-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-192">Total Sessions Terminated Because of Idle Timeout</span><span class="sxs-lookup"><span data-stu-id="9019f-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="9019f-193">Nombre total de sessions terminées en raison d’un délai d’expiration d’inactivité</span><span class="sxs-lookup"><span data-stu-id="9019f-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-194">Total Throttled Applications</span><span class="sxs-lookup"><span data-stu-id="9019f-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="9019f-195">Nombre d’applications limitées</span><span class="sxs-lookup"><span data-stu-id="9019f-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="9019f-196">Compteurs de performances pour le service de mobilité Mcx</span><span class="sxs-lookup"><span data-stu-id="9019f-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9019f-197">Compteur</span><span class="sxs-lookup"><span data-stu-id="9019f-197">Counter</span></span></th>
<th><span data-ttu-id="9019f-198">Description</span><span class="sxs-lookup"><span data-stu-id="9019f-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9019f-199">Durée de vie moyenne d’une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="9019f-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="9019f-200">Durée de vie moyenne pour une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="9019f-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-201">Abonnements actuels aux notifications push</span><span class="sxs-lookup"><span data-stu-id="9019f-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="9019f-p101">Nombre actuel d’abonnements de notification push. Ce chiffre, associé au Nombre de sessions actuellement actives, représente le sous-ensemble de sessions actuellement actives enregistrées pour les appareils Windows Mobile ou iPhone.</span><span class="sxs-lookup"><span data-stu-id="9019f-p101">The current number of push notification subscriptions. This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-204">Nombre d’interrogations réseau expirées actuellement actives</span><span class="sxs-lookup"><span data-stu-id="9019f-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-205">Nombre d’interrogations réseau dont le délai d’attente a expiré</span><span class="sxs-lookup"><span data-stu-id="9019f-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-206">Nombre d’interrogations actuellement actives</span><span class="sxs-lookup"><span data-stu-id="9019f-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-207">Nombre d’interrogations actuellement actives (longues connexions au serveur)</span><span class="sxs-lookup"><span data-stu-id="9019f-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-208">Nombre de sessions actuellement actives</span><span class="sxs-lookup"><span data-stu-id="9019f-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-209">Nombre actuel de points de terminaison enregistrés dans le service de mobilité</span><span class="sxs-lookup"><span data-stu-id="9019f-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-210">Nombre de sessions actuellement actives avec abonnements de présence actifs</span><span class="sxs-lookup"><span data-stu-id="9019f-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="9019f-211">Nombre de sessions actuellement actives avec abonnements de présence actifs</span><span class="sxs-lookup"><span data-stu-id="9019f-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-212">Demandes de notifications push ayant échoué/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-213">Taux de notifications push ayant échoué par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-214">Demandes de notifications push réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-215">Taux de notifications push ayant réussi par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-216">Demandes de notifications push limitées/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-217">Taux de notifications push ayant été limitées par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-218">Demandes de notifications push/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-219">Taux de notifications push envoyées par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-220">Demandes ayant échoué/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-221">Taux de demandes ayant échoué par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-222">Demandes reçues/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-223">Taux de demandes reçues par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-224">Demandes rejetées/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-225">Taux de demandes rejetées par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-226">Demandes réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-227">Taux de demandes réussies par seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-228">Demandes de lancement de session réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="9019f-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="9019f-p102">Taux de demandes Get Location réussies par seconde. Les demandes de lancement de session consomment le plus de puissance de traitement sur le serveur. La charge maximale prise en charge est de 12 par seconde. La capacité à soutenir ces charges dépend des autres charges imposées sur le serveur. Le lancement d’une session signifie généralement la connexion d’un utilisateur ayant été déconnecté depuis un laps de temps étendu.</span><span class="sxs-lookup"><span data-stu-id="9019f-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-234">Nombre total d’appels vocaux entrants refusés</span><span class="sxs-lookup"><span data-stu-id="9019f-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="9019f-235">Nombre total d’appels vocaux entrants ayant été refusés</span><span class="sxs-lookup"><span data-stu-id="9019f-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-236">Nombre total d’appels vocaux entrants ayant échoué</span><span class="sxs-lookup"><span data-stu-id="9019f-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="9019f-237">Nombre total d’appels vocaux entrants ayant échoué</span><span class="sxs-lookup"><span data-stu-id="9019f-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-238">Nombre total d’appels vocaux sortants ayant échoué</span><span class="sxs-lookup"><span data-stu-id="9019f-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="9019f-239">Nombre total d’appels vocaux sortants ayant échoué</span><span class="sxs-lookup"><span data-stu-id="9019f-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-240">Nombre total de sessions terminées par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="9019f-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="9019f-241">Nombre total de sessions auxquelles les utilisateurs ont mis fin</span><span class="sxs-lookup"><span data-stu-id="9019f-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-242">Nombre total de demandes de notifications push</span><span class="sxs-lookup"><span data-stu-id="9019f-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="9019f-243">Nombre total de demandes de notifications push</span><span class="sxs-lookup"><span data-stu-id="9019f-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-244">Nombre total de demandes de notifications push ayant échoué</span><span class="sxs-lookup"><span data-stu-id="9019f-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="9019f-245">Nombre total de demandes de notifications push ayant échoué</span><span class="sxs-lookup"><span data-stu-id="9019f-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-246">Nombre total de demandes de notifications push réussies</span><span class="sxs-lookup"><span data-stu-id="9019f-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="9019f-247">Nombre total de demandes de notifications push ayant réussi</span><span class="sxs-lookup"><span data-stu-id="9019f-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-248">Nombre total de demandes de notifications push limitées</span><span class="sxs-lookup"><span data-stu-id="9019f-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="9019f-249">Nombre total de demandes de notifications push ayant limitées</span><span class="sxs-lookup"><span data-stu-id="9019f-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-250">Nombre total de demandes ayant échoué</span><span class="sxs-lookup"><span data-stu-id="9019f-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="9019f-251">Nombre total de demandes ayant échoué</span><span class="sxs-lookup"><span data-stu-id="9019f-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-252">Nombre total de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="9019f-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="9019f-253">Nombre total de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="9019f-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-254">Nombre total de demandes rejetées</span><span class="sxs-lookup"><span data-stu-id="9019f-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="9019f-255">Nombre total de demandes ayant été rejetées</span><span class="sxs-lookup"><span data-stu-id="9019f-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-256">Nombre total de demandes réussies</span><span class="sxs-lookup"><span data-stu-id="9019f-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="9019f-257">Nombre total de demandes effectuées au service de mobilité et ayant réussi</span><span class="sxs-lookup"><span data-stu-id="9019f-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-258">Total de sessions initiées</span><span class="sxs-lookup"><span data-stu-id="9019f-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="9019f-259">Nombre total de sessions qui ont été initiées depuis le démarrage du service de mobilité</span><span class="sxs-lookup"><span data-stu-id="9019f-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-260">Total des sessions terminées pour inactivité utilisateur</span><span class="sxs-lookup"><span data-stu-id="9019f-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="9019f-261">Nombre total de sessions terminées en raison d’un délai d’expiration d’inactivité</span><span class="sxs-lookup"><span data-stu-id="9019f-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9019f-262">Nombre total d’appels vocaux entrants réussis</span><span class="sxs-lookup"><span data-stu-id="9019f-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="9019f-263">Nombre total d’appels vocaux entrants ayant été réussis</span><span class="sxs-lookup"><span data-stu-id="9019f-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9019f-264">Nombre total d’appels vocaux sortants réussis</span><span class="sxs-lookup"><span data-stu-id="9019f-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="9019f-265">Nombre total d’appels vocaux sortants ayant été réussis</span><span class="sxs-lookup"><span data-stu-id="9019f-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

