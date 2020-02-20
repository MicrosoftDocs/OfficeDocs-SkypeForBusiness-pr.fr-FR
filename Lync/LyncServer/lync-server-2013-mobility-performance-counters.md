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
ms.openlocfilehash: cb5363ef31f44abdb9c8ea07938668f17b95c471
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="4639b-102">Compteurs de performances de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4639b-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4639b-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4639b-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4639b-104">Les tableaux suivants répertorient les noms et les descriptions des compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API Web Unified Communications (UCWA) et le service Lync Server 2013 MCX Mobility.</span><span class="sxs-lookup"><span data-stu-id="4639b-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="4639b-105">Le nom de catégorie pour les compteurs dans la table UCWA est **ls : Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="4639b-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="4639b-106">Le nom de catégorie pour les compteurs dans la table MCX Mobility service est **ls : Web-mobile communication service**.</span><span class="sxs-lookup"><span data-stu-id="4639b-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="4639b-107">Compteurs de performance pour UCWA</span><span class="sxs-lookup"><span data-stu-id="4639b-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4639b-108">Compteur</span><span class="sxs-lookup"><span data-stu-id="4639b-108">Counter</span></span></th>
<th><span data-ttu-id="4639b-109">Description</span><span class="sxs-lookup"><span data-stu-id="4639b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4639b-110">Nombre d’applications actives</span><span class="sxs-lookup"><span data-stu-id="4639b-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-111">Nombre actuel d’applications</span><span class="sxs-lookup"><span data-stu-id="4639b-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-112">Nombre de modalités de partage d’applications actives</span><span class="sxs-lookup"><span data-stu-id="4639b-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-113">Le nombre actuel de modalités de partage d’application</span><span class="sxs-lookup"><span data-stu-id="4639b-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-114">Nombre de passes actives audio</span><span class="sxs-lookup"><span data-stu-id="4639b-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-115">Nombre actuel de modalités audio</span><span class="sxs-lookup"><span data-stu-id="4639b-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-116">Nombre de MODALITES de collaboration de données actives</span><span class="sxs-lookup"><span data-stu-id="4639b-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-117">Le nombre actuel de modalités de collaboration de données ;</span><span class="sxs-lookup"><span data-stu-id="4639b-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-118">Latence d’obtention de photos Active Directory (MS)</span><span class="sxs-lookup"><span data-stu-id="4639b-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="4639b-119">Ce compteur indique le temps moyen (en millisecondes) nécessaire pour récupérer une photo à partir d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="4639b-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-120">Nombre de modalités de messagerie active</span><span class="sxs-lookup"><span data-stu-id="4639b-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-121">Nombre actuel de modalités de messagerie</span><span class="sxs-lookup"><span data-stu-id="4639b-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-122">Nombre de passes vidéo panoramique actif</span><span class="sxs-lookup"><span data-stu-id="4639b-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-123">Nombre actuel de modalité vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="4639b-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-124">Nombre d’obtentions actives en attente</span><span class="sxs-lookup"><span data-stu-id="4639b-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-125">Le nombre de gets actuellement en attente ; connexions de longue durée vers le serveur</span><span class="sxs-lookup"><span data-stu-id="4639b-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-126">Nombre de sessions actives</span><span class="sxs-lookup"><span data-stu-id="4639b-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-127">Nombre actuel de points de terminaison inscrits dans UCWA par application et total</span><span class="sxs-lookup"><span data-stu-id="4639b-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-128">Nombre d’instances de l’utilisateur actif</span><span class="sxs-lookup"><span data-stu-id="4639b-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-129">Nombre actuel d’instances utilisateur</span><span class="sxs-lookup"><span data-stu-id="4639b-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-130">Instances utilisateur actives sans application</span><span class="sxs-lookup"><span data-stu-id="4639b-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="4639b-131">Nombre actuel d’instances utilisateur sans application</span><span class="sxs-lookup"><span data-stu-id="4639b-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-132">Nombre de passes de vidéo actives</span><span class="sxs-lookup"><span data-stu-id="4639b-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-133">Nombre actuel de modalités vidéo</span><span class="sxs-lookup"><span data-stu-id="4639b-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-134">Demandes de création d’application reçues/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-135">Taux de demandes de création d’application reçues par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-136">En tant qu’échecs de jonction MCU</span><span class="sxs-lookup"><span data-stu-id="4639b-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-137">Nombre d’échecs de jointures MCU</span><span class="sxs-lookup"><span data-stu-id="4639b-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-138">Échecs de participation de la MCU AV</span><span class="sxs-lookup"><span data-stu-id="4639b-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-139">Nombre d’échecs de participation de la MCU AV</span><span class="sxs-lookup"><span data-stu-id="4639b-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-140">Durée moyenne de démarrage de l’application (MS)</span><span class="sxs-lookup"><span data-stu-id="4639b-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="4639b-141">Durée moyenne de démarrage de l’application en millisecondes</span><span class="sxs-lookup"><span data-stu-id="4639b-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-142">Durée de vie moyenne de la session (MS)</span><span class="sxs-lookup"><span data-stu-id="4639b-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="4639b-143">Durée de vie moyenne d’une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="4639b-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-144">Échecs de jonction de MCU de données</span><span class="sxs-lookup"><span data-stu-id="4639b-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-145">Nombre d’échecs de jonctions de MCU de données</span><span class="sxs-lookup"><span data-stu-id="4639b-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-146">Latence de recherche de contact Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="4639b-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="4639b-147">Ce compteur indique le temps moyen (en millisecondes) entre le contact de recherche dans Exchange</span><span class="sxs-lookup"><span data-stu-id="4639b-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-148">Latence d’obtention de photo HD Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="4639b-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="4639b-149">Ce compteur indique le temps moyen (en millisecondes) nécessaire pour récupérer une photo à partir d’Exchange</span><span class="sxs-lookup"><span data-stu-id="4639b-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-150">Réponses 4xx HTTP/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-151">Taux de réponses par seconde avec le code HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="4639b-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-152">Réponses 5xx HTTP/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-153">Taux de réponses par seconde avec du code HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="4639b-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-154">Échecs de jonctions de la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="4639b-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-155">Nombre d’échecs de jonctions de la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="4639b-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-156">Nombre d’échecs d’obtention de photos Active Directory</span><span class="sxs-lookup"><span data-stu-id="4639b-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-157">Nombre total d’échecs de récupération de photos à partir d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="4639b-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-158">Nombre d’échecs de recherche de contacts</span><span class="sxs-lookup"><span data-stu-id="4639b-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-159">Nombre total d’échecs de recherche de contacts dans Exchange</span><span class="sxs-lookup"><span data-stu-id="4639b-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-160">Nombre d’échecs de désérialisation</span><span class="sxs-lookup"><span data-stu-id="4639b-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-161">Nombre total d’échecs de désérialisation</span><span class="sxs-lookup"><span data-stu-id="4639b-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-162">Nombre d’échecs de la photo HD</span><span class="sxs-lookup"><span data-stu-id="4639b-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-163">Nombre total d’échecs de récupération de photos HD à partir d’Exchange</span><span class="sxs-lookup"><span data-stu-id="4639b-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-164">Sur le nombre maximal d’abonnements par application</span><span class="sxs-lookup"><span data-stu-id="4639b-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="4639b-165">Nombre de demandes d’abonnement sur le maximum autorisé par application</span><span class="sxs-lookup"><span data-stu-id="4639b-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-166">Sur le nombre maximal d’abonnements par lot</span><span class="sxs-lookup"><span data-stu-id="4639b-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="4639b-167">Nombre de demandes d’abonnement sur le maximum autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="4639b-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-168">Échecs d’abonnements de présence</span><span class="sxs-lookup"><span data-stu-id="4639b-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-169">Nombre d’échecs d’abonnement à la présence</span><span class="sxs-lookup"><span data-stu-id="4639b-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-170">Enregistrement des défaillances du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="4639b-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="4639b-171">Nombre d’échecs d’enregistrement des points de terminaison</span><span class="sxs-lookup"><span data-stu-id="4639b-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-172">Demandes reçues/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-173">Taux de demandes reçues par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-174">Demandes réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-175">Taux de demandes réussies (codes de réponse HTTPs/3xx) par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-176">Réussite de la création des demandes d’application/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-177">Taux de demandes de création d’application réussies par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-178">Expiration du nombre d’obtentions en attente</span><span class="sxs-lookup"><span data-stu-id="4639b-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-179">Nombre de récupérations en attente qui ont expiré</span><span class="sxs-lookup"><span data-stu-id="4639b-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-180">Nombre total de demandes de création d’application reçues</span><span class="sxs-lookup"><span data-stu-id="4639b-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="4639b-181">Nombre total de demandes de création d’application reçues depuis le démarrage du service</span><span class="sxs-lookup"><span data-stu-id="4639b-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-182">Nombre total de réponses HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="4639b-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="4639b-183">Nombre total de réponses HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="4639b-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-184">Nombre total de réponses 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="4639b-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="4639b-185">Nombre total de réponses 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="4639b-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-186">Nombre total de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="4639b-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="4639b-187">Quantité totale de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="4639b-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-188">Quantité totale de demandes réussies</span><span class="sxs-lookup"><span data-stu-id="4639b-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4639b-189">Nombre total de demandes ayant réussi</span><span class="sxs-lookup"><span data-stu-id="4639b-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-190">Nombre total de sessions lancées</span><span class="sxs-lookup"><span data-stu-id="4639b-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="4639b-191">Nombre total de sessions qui ont été initiées depuis le démarrage du service</span><span class="sxs-lookup"><span data-stu-id="4639b-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-192">Nombre total de sessions terminées en raison d’un délai d’inactivité</span><span class="sxs-lookup"><span data-stu-id="4639b-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="4639b-193">Quantité totale de sessions qui ont été terminées suite à l’expiration du délai d’inactivité utilisateur</span><span class="sxs-lookup"><span data-stu-id="4639b-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-194">Nombre total d’applications limitées</span><span class="sxs-lookup"><span data-stu-id="4639b-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="4639b-195">Nombre d’applications limitées</span><span class="sxs-lookup"><span data-stu-id="4639b-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="4639b-196">Compteurs de performances pour le service de mobilité MCX</span><span class="sxs-lookup"><span data-stu-id="4639b-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4639b-197">Compteur</span><span class="sxs-lookup"><span data-stu-id="4639b-197">Counter</span></span></th>
<th><span data-ttu-id="4639b-198">Description</span><span class="sxs-lookup"><span data-stu-id="4639b-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4639b-199">Durée de vie moyenne d’une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="4639b-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="4639b-200">Durée de vie moyenne d’une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="4639b-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-201">Abonnements actuels aux notifications push</span><span class="sxs-lookup"><span data-stu-id="4639b-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="4639b-202">Quantité actuelle d’abonnements aux notifications push.</span><span class="sxs-lookup"><span data-stu-id="4639b-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="4639b-203">Ce nombre, en association avec le nombre de sessions actuellement actives, représente le sous-ensemble des sessions actuellement actives qui sont inscrites pour les appareils Windows Mobile ou iPhone.</span><span class="sxs-lookup"><span data-stu-id="4639b-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-204">Nombre d’interrogations réseau expirées actuellement actives</span><span class="sxs-lookup"><span data-stu-id="4639b-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-205">Nombre d’interrogations réseau sont le délai d’attente a expiré</span><span class="sxs-lookup"><span data-stu-id="4639b-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-206">Nombre d’interrogations actuellement actives</span><span class="sxs-lookup"><span data-stu-id="4639b-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-207">Nombre d’interrogations actuellement actives (longues connexions au serveur)</span><span class="sxs-lookup"><span data-stu-id="4639b-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-208">Nombre de sessions actuellement actives</span><span class="sxs-lookup"><span data-stu-id="4639b-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-209">Quantité actuelle de points de terminaison enregistrés dans le service de mobilité</span><span class="sxs-lookup"><span data-stu-id="4639b-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-210">Nombre de sessions actuellement actives avec abonnements de présence actifs</span><span class="sxs-lookup"><span data-stu-id="4639b-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="4639b-211">Nombre de sessions actuellement actives avec abonnements de présence actifs</span><span class="sxs-lookup"><span data-stu-id="4639b-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-212">Demandes de notifications push échouées/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-213">Taux de notifications push ayant échoué par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-214">Demandes de notifications push réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-215">Taux de notifications push ayant réussi par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-216">Demandes de notifications push limitées/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-217">Taux de notifications push ayant été limitées par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-218">Demandes de notifications push/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-219">Taux de notifications push envoyées par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-220">Demandes échouées/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-221">Taux de demandes ayant échoué par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-222">Demandes reçues/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-223">Taux de demandes reçues par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-224">Demandes rejetées/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-225">Taux de demandes rejetées par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-226">Demandes réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-227">Taux de demandes réussies par seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-228">Demandes de lancement de session réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="4639b-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="4639b-p102">Taux de demandes Get Location réussies par seconde. Les demandes de lancement de session consomment le plus de puissance de traitement sur le serveur. La charge maximale prise en charge est de 12 par seconde. La capacité à soutenir ces charges dépend des autres charges imposées sur le serveur. Le lancement d’une session signifie généralement la connexion d’un utilisateur ayant été déconnecté depuis un laps de temps étendu.</span><span class="sxs-lookup"><span data-stu-id="4639b-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-234">Quantité totale d’appels vocaux entrants refusés</span><span class="sxs-lookup"><span data-stu-id="4639b-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4639b-235">Quantité totale d’appels vocaux entrants ayant été refusés</span><span class="sxs-lookup"><span data-stu-id="4639b-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-236">Quantité totale d’appels vocaux entrants échoués</span><span class="sxs-lookup"><span data-stu-id="4639b-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4639b-237">Quantité totale d’appels vocaux entrants ayant échoué</span><span class="sxs-lookup"><span data-stu-id="4639b-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-238">Quantité totale d’appels vocaux sortants échoués</span><span class="sxs-lookup"><span data-stu-id="4639b-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4639b-239">Quantité totale d’appels vocaux sortants ayant échoué</span><span class="sxs-lookup"><span data-stu-id="4639b-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-240">Quantité totale de sessions terminées par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="4639b-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="4639b-241">Quantité totale de sessions auxquelles les utilisateurs ont mis fin</span><span class="sxs-lookup"><span data-stu-id="4639b-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-242">Quantité totale de demandes de notifications push</span><span class="sxs-lookup"><span data-stu-id="4639b-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="4639b-243">Quantité totale de demandes de notifications push</span><span class="sxs-lookup"><span data-stu-id="4639b-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-244">Quantité totale de demandes de notifications push échouées</span><span class="sxs-lookup"><span data-stu-id="4639b-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="4639b-245">Quantité totale de demandes de notifications push ayant échoué</span><span class="sxs-lookup"><span data-stu-id="4639b-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-246">Quantité totale de demandes de notifications push réussies</span><span class="sxs-lookup"><span data-stu-id="4639b-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4639b-247">Quantité totale de demandes de notifications push ayant réussi</span><span class="sxs-lookup"><span data-stu-id="4639b-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-248">Quantité totale de demandes de notifications push limitées</span><span class="sxs-lookup"><span data-stu-id="4639b-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="4639b-249">Quantité totale de demandes de notifications push ayant limitées</span><span class="sxs-lookup"><span data-stu-id="4639b-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-250">Quantité totale de demandes échouées</span><span class="sxs-lookup"><span data-stu-id="4639b-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="4639b-251">Quantité totale de demandes ayant échoué</span><span class="sxs-lookup"><span data-stu-id="4639b-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-252">Quantité totale de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="4639b-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="4639b-253">Quantité totale de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="4639b-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-254">Quantité totale de demandes rejetées</span><span class="sxs-lookup"><span data-stu-id="4639b-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="4639b-255">Quantité totale de demandes ayant été rejetées</span><span class="sxs-lookup"><span data-stu-id="4639b-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-256">Quantité totale de demandes réussies</span><span class="sxs-lookup"><span data-stu-id="4639b-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4639b-257">Quantité totale de demandes effectuées au service de mobilité et ayant réussi</span><span class="sxs-lookup"><span data-stu-id="4639b-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-258">Total de sessions initiées</span><span class="sxs-lookup"><span data-stu-id="4639b-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="4639b-259">Quantité totale de sessions qui ont été initiées depuis le démarrage du service de mobilité</span><span class="sxs-lookup"><span data-stu-id="4639b-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-260">Total des sessions terminées pour inactivité utilisateur</span><span class="sxs-lookup"><span data-stu-id="4639b-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="4639b-261">Quantité totale de sessions qui ont été terminées suite à l’expiration du délai d’inactivité utilisateur</span><span class="sxs-lookup"><span data-stu-id="4639b-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4639b-262">Quantité totale d’appels vocaux entrants réussis</span><span class="sxs-lookup"><span data-stu-id="4639b-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4639b-263">Quantité totale d’appels vocaux entrants ayant été réussis</span><span class="sxs-lookup"><span data-stu-id="4639b-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4639b-264">Quantité totale d’appels vocaux sortants réussis</span><span class="sxs-lookup"><span data-stu-id="4639b-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4639b-265">Quantité totale d’appels vocaux sortants ayant été réussis</span><span class="sxs-lookup"><span data-stu-id="4639b-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

