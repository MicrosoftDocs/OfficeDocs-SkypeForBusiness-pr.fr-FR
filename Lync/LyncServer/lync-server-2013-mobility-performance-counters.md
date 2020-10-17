---
title: 'Lync Server 2013 : compteurs de performances de mobilité'
description: 'Lync Server 2013 : compteurs de performances de mobilité.'
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
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550530"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="974f5-103">Compteurs de performances de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="974f5-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="974f5-104">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="974f5-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="974f5-105">Les tableaux suivants répertorient les noms et les descriptions des compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API Web Unified Communications (UCWA) et le service Lync Server 2013 MCX Mobility.</span><span class="sxs-lookup"><span data-stu-id="974f5-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="974f5-106">Le nom de catégorie pour les compteurs dans la table UCWA est **ls : Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="974f5-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="974f5-107">Le nom de catégorie pour les compteurs dans la table MCX Mobility service est **ls : Web-mobile communication service**.</span><span class="sxs-lookup"><span data-stu-id="974f5-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="974f5-108">Compteurs de performance pour UCWA</span><span class="sxs-lookup"><span data-stu-id="974f5-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="974f5-109">Compteur</span><span class="sxs-lookup"><span data-stu-id="974f5-109">Counter</span></span></th>
<th><span data-ttu-id="974f5-110">Description</span><span class="sxs-lookup"><span data-stu-id="974f5-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="974f5-111">Nombre d’applications actives</span><span class="sxs-lookup"><span data-stu-id="974f5-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-112">Nombre actuel d’applications</span><span class="sxs-lookup"><span data-stu-id="974f5-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-113">Nombre de modalités de partage d’applications actives</span><span class="sxs-lookup"><span data-stu-id="974f5-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-114">Le nombre actuel de modalités de partage d’application</span><span class="sxs-lookup"><span data-stu-id="974f5-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-115">Nombre de passes actives audio</span><span class="sxs-lookup"><span data-stu-id="974f5-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-116">Nombre actuel de modalités audio</span><span class="sxs-lookup"><span data-stu-id="974f5-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-117">Nombre de MODALITES de collaboration de données actives</span><span class="sxs-lookup"><span data-stu-id="974f5-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-118">Le nombre actuel de modalités de collaboration de données ;</span><span class="sxs-lookup"><span data-stu-id="974f5-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-119">Latence d’obtention de photos Active Directory (MS)</span><span class="sxs-lookup"><span data-stu-id="974f5-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="974f5-120">Ce compteur indique le temps moyen (en millisecondes) nécessaire pour récupérer une photo à partir d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="974f5-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-121">Nombre de modalités de messagerie active</span><span class="sxs-lookup"><span data-stu-id="974f5-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-122">Nombre actuel de modalités de messagerie</span><span class="sxs-lookup"><span data-stu-id="974f5-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-123">Nombre de passes vidéo panoramique actif</span><span class="sxs-lookup"><span data-stu-id="974f5-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-124">Nombre actuel de modalité vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="974f5-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-125">Nombre d’obtentions actives en attente</span><span class="sxs-lookup"><span data-stu-id="974f5-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-126">Le nombre de gets actuellement en attente ; connexions de longue durée vers le serveur</span><span class="sxs-lookup"><span data-stu-id="974f5-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-127">Nombre de sessions actives</span><span class="sxs-lookup"><span data-stu-id="974f5-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-128">Nombre actuel de points de terminaison inscrits dans UCWA par application et total</span><span class="sxs-lookup"><span data-stu-id="974f5-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-129">Nombre d’instances de l’utilisateur actif</span><span class="sxs-lookup"><span data-stu-id="974f5-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-130">Nombre actuel d’instances utilisateur</span><span class="sxs-lookup"><span data-stu-id="974f5-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-131">Instances utilisateur actives sans application</span><span class="sxs-lookup"><span data-stu-id="974f5-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="974f5-132">Nombre actuel d’instances utilisateur sans application</span><span class="sxs-lookup"><span data-stu-id="974f5-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-133">Nombre de passes de vidéo actives</span><span class="sxs-lookup"><span data-stu-id="974f5-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-134">Nombre actuel de modalités vidéo</span><span class="sxs-lookup"><span data-stu-id="974f5-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-135">Demandes de création d’application reçues/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-136">Taux de demandes de création d’application reçues par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-137">En tant qu’échecs de jonction MCU</span><span class="sxs-lookup"><span data-stu-id="974f5-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-138">Nombre d’échecs de jointures MCU</span><span class="sxs-lookup"><span data-stu-id="974f5-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-139">Échecs de participation de la MCU AV</span><span class="sxs-lookup"><span data-stu-id="974f5-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-140">Nombre d’échecs de participation de la MCU AV</span><span class="sxs-lookup"><span data-stu-id="974f5-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-141">Durée moyenne de démarrage de l’application (MS)</span><span class="sxs-lookup"><span data-stu-id="974f5-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="974f5-142">Durée moyenne de démarrage de l’application en millisecondes</span><span class="sxs-lookup"><span data-stu-id="974f5-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-143">Durée de vie moyenne de la session (MS)</span><span class="sxs-lookup"><span data-stu-id="974f5-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="974f5-144">Durée de vie moyenne d’une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="974f5-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-145">Échecs de jonction de MCU de données</span><span class="sxs-lookup"><span data-stu-id="974f5-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-146">Nombre d’échecs de jonctions de MCU de données</span><span class="sxs-lookup"><span data-stu-id="974f5-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-147">Latence de recherche de contact Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="974f5-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="974f5-148">Ce compteur indique le temps moyen (en millisecondes) entre le contact de recherche dans Exchange</span><span class="sxs-lookup"><span data-stu-id="974f5-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-149">Latence d’obtention de photo HD Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="974f5-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="974f5-150">Ce compteur indique le temps moyen (en millisecondes) nécessaire pour récupérer une photo à partir d’Exchange</span><span class="sxs-lookup"><span data-stu-id="974f5-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-151">Réponses 4xx HTTP/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-152">Taux de réponses par seconde avec le code HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="974f5-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-153">Réponses 5xx HTTP/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-154">Taux de réponses par seconde avec du code HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="974f5-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-155">Échecs de jonctions de la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="974f5-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-156">Nombre d’échecs de jonctions de la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="974f5-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-157">Nombre d’échecs d’obtention de photos Active Directory</span><span class="sxs-lookup"><span data-stu-id="974f5-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-158">Nombre total d’échecs de récupération de photos à partir d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="974f5-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-159">Nombre d’échecs de recherche de contacts</span><span class="sxs-lookup"><span data-stu-id="974f5-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-160">Nombre total d’échecs de recherche de contacts dans Exchange</span><span class="sxs-lookup"><span data-stu-id="974f5-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-161">Nombre d’échecs de désérialisation</span><span class="sxs-lookup"><span data-stu-id="974f5-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-162">Nombre total d’échecs de désérialisation</span><span class="sxs-lookup"><span data-stu-id="974f5-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-163">Nombre d’échecs de la photo HD</span><span class="sxs-lookup"><span data-stu-id="974f5-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-164">Nombre total d’échecs de récupération de photos HD à partir d’Exchange</span><span class="sxs-lookup"><span data-stu-id="974f5-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-165">Sur le nombre maximal d’abonnements par application</span><span class="sxs-lookup"><span data-stu-id="974f5-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="974f5-166">Nombre de demandes d’abonnement sur le maximum autorisé par application</span><span class="sxs-lookup"><span data-stu-id="974f5-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-167">Sur le nombre maximal d’abonnements par lot</span><span class="sxs-lookup"><span data-stu-id="974f5-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="974f5-168">Nombre de demandes d’abonnement sur le maximum autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="974f5-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-169">Échecs d’abonnements de présence</span><span class="sxs-lookup"><span data-stu-id="974f5-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-170">Nombre d’échecs d’abonnement à la présence</span><span class="sxs-lookup"><span data-stu-id="974f5-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-171">Enregistrement des défaillances du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="974f5-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="974f5-172">Nombre d’échecs d’enregistrement des points de terminaison</span><span class="sxs-lookup"><span data-stu-id="974f5-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-173">Demandes reçues/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-174">Taux de demandes reçues par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-175">Demandes réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-176">Taux de demandes réussies (codes de réponse HTTPs/3xx) par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-177">Réussite de la création des demandes d’application/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-178">Taux de demandes de création d’application réussies par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-179">Expiration du nombre d’obtentions en attente</span><span class="sxs-lookup"><span data-stu-id="974f5-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-180">Nombre de récupérations en attente qui ont expiré</span><span class="sxs-lookup"><span data-stu-id="974f5-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-181">Nombre total de demandes de création d’application reçues</span><span class="sxs-lookup"><span data-stu-id="974f5-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="974f5-182">Nombre total de demandes de création d’application reçues depuis le démarrage du service</span><span class="sxs-lookup"><span data-stu-id="974f5-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-183">Nombre total de réponses HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="974f5-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="974f5-184">Nombre total de réponses HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="974f5-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-185">Nombre total de réponses 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="974f5-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="974f5-186">Nombre total de réponses 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="974f5-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-187">Nombre total de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="974f5-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="974f5-188">Quantité totale de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="974f5-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-189">Quantité totale de demandes réussies</span><span class="sxs-lookup"><span data-stu-id="974f5-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="974f5-190">Nombre total de demandes ayant réussi</span><span class="sxs-lookup"><span data-stu-id="974f5-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-191">Nombre total de sessions lancées</span><span class="sxs-lookup"><span data-stu-id="974f5-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="974f5-192">Nombre total de sessions qui ont été initiées depuis le démarrage du service</span><span class="sxs-lookup"><span data-stu-id="974f5-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-193">Nombre total de sessions terminées en raison d’un délai d’inactivité</span><span class="sxs-lookup"><span data-stu-id="974f5-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="974f5-194">Quantité totale de sessions qui ont été terminées suite à l’expiration du délai d’inactivité utilisateur</span><span class="sxs-lookup"><span data-stu-id="974f5-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-195">Nombre total d’applications limitées</span><span class="sxs-lookup"><span data-stu-id="974f5-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="974f5-196">Nombre d’applications limitées</span><span class="sxs-lookup"><span data-stu-id="974f5-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="974f5-197">Compteurs de performances pour le service de mobilité MCX</span><span class="sxs-lookup"><span data-stu-id="974f5-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="974f5-198">Compteur</span><span class="sxs-lookup"><span data-stu-id="974f5-198">Counter</span></span></th>
<th><span data-ttu-id="974f5-199">Description</span><span class="sxs-lookup"><span data-stu-id="974f5-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="974f5-200">Durée de vie moyenne d’une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="974f5-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="974f5-201">Durée de vie moyenne d’une session en millisecondes</span><span class="sxs-lookup"><span data-stu-id="974f5-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-202">Abonnements actuels aux notifications push</span><span class="sxs-lookup"><span data-stu-id="974f5-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="974f5-203">Quantité actuelle d’abonnements aux notifications push.</span><span class="sxs-lookup"><span data-stu-id="974f5-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="974f5-204">Ce nombre, en association avec le nombre de sessions actuellement actives, représente le sous-ensemble des sessions actuellement actives qui sont inscrites pour les appareils Windows Mobile ou iPhone.</span><span class="sxs-lookup"><span data-stu-id="974f5-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-205">Nombre d’interrogations réseau expirées actuellement actives</span><span class="sxs-lookup"><span data-stu-id="974f5-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-206">Nombre d’interrogations réseau sont le délai d’attente a expiré</span><span class="sxs-lookup"><span data-stu-id="974f5-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-207">Nombre d’interrogations actuellement actives</span><span class="sxs-lookup"><span data-stu-id="974f5-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-208">Nombre d’interrogations actuellement actives (longues connexions au serveur)</span><span class="sxs-lookup"><span data-stu-id="974f5-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-209">Nombre de sessions actuellement actives</span><span class="sxs-lookup"><span data-stu-id="974f5-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-210">Quantité actuelle de points de terminaison enregistrés dans le service de mobilité</span><span class="sxs-lookup"><span data-stu-id="974f5-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-211">Nombre de sessions actuellement actives avec abonnements de présence actifs</span><span class="sxs-lookup"><span data-stu-id="974f5-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="974f5-212">Nombre de sessions actuellement actives avec abonnements de présence actifs</span><span class="sxs-lookup"><span data-stu-id="974f5-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-213">Demandes de notifications push échouées/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-214">Taux de notifications push ayant échoué par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-215">Demandes de notifications push réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-216">Taux de notifications push ayant réussi par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-217">Demandes de notifications push limitées/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-218">Taux de notifications push ayant été limitées par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-219">Demandes de notifications push/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-220">Taux de notifications push envoyées par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-221">Demandes échouées/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-222">Taux de demandes ayant échoué par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-223">Demandes reçues/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-224">Taux de demandes reçues par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-225">Demandes rejetées/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-226">Taux de demandes rejetées par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-227">Demandes réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-228">Taux de demandes réussies par seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-229">Demandes de lancement de session réussies/seconde</span><span class="sxs-lookup"><span data-stu-id="974f5-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="974f5-p102">Taux de demandes Get Location réussies par seconde. Les demandes de lancement de session consomment le plus de puissance de traitement sur le serveur. La charge maximale prise en charge est de 12 par seconde. La capacité à soutenir ces charges dépend des autres charges imposées sur le serveur. Le lancement d’une session signifie généralement la connexion d’un utilisateur ayant été déconnecté depuis un laps de temps étendu.</span><span class="sxs-lookup"><span data-stu-id="974f5-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-235">Quantité totale d’appels vocaux entrants refusés</span><span class="sxs-lookup"><span data-stu-id="974f5-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="974f5-236">Quantité totale d’appels vocaux entrants ayant été refusés</span><span class="sxs-lookup"><span data-stu-id="974f5-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-237">Quantité totale d’appels vocaux entrants échoués</span><span class="sxs-lookup"><span data-stu-id="974f5-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="974f5-238">Quantité totale d’appels vocaux entrants ayant échoué</span><span class="sxs-lookup"><span data-stu-id="974f5-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-239">Quantité totale d’appels vocaux sortants échoués</span><span class="sxs-lookup"><span data-stu-id="974f5-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="974f5-240">Quantité totale d’appels vocaux sortants ayant échoué</span><span class="sxs-lookup"><span data-stu-id="974f5-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-241">Quantité totale de sessions terminées par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="974f5-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="974f5-242">Quantité totale de sessions auxquelles les utilisateurs ont mis fin</span><span class="sxs-lookup"><span data-stu-id="974f5-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-243">Quantité totale de demandes de notifications push</span><span class="sxs-lookup"><span data-stu-id="974f5-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="974f5-244">Quantité totale de demandes de notifications push</span><span class="sxs-lookup"><span data-stu-id="974f5-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-245">Quantité totale de demandes de notifications push échouées</span><span class="sxs-lookup"><span data-stu-id="974f5-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="974f5-246">Quantité totale de demandes de notifications push ayant échoué</span><span class="sxs-lookup"><span data-stu-id="974f5-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-247">Quantité totale de demandes de notifications push réussies</span><span class="sxs-lookup"><span data-stu-id="974f5-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="974f5-248">Quantité totale de demandes de notifications push ayant réussi</span><span class="sxs-lookup"><span data-stu-id="974f5-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-249">Quantité totale de demandes de notifications push limitées</span><span class="sxs-lookup"><span data-stu-id="974f5-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="974f5-250">Quantité totale de demandes de notifications push ayant limitées</span><span class="sxs-lookup"><span data-stu-id="974f5-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-251">Quantité totale de demandes échouées</span><span class="sxs-lookup"><span data-stu-id="974f5-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="974f5-252">Quantité totale de demandes ayant échoué</span><span class="sxs-lookup"><span data-stu-id="974f5-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-253">Quantité totale de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="974f5-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="974f5-254">Quantité totale de demandes reçues sur le canal de commande</span><span class="sxs-lookup"><span data-stu-id="974f5-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-255">Quantité totale de demandes rejetées</span><span class="sxs-lookup"><span data-stu-id="974f5-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="974f5-256">Quantité totale de demandes ayant été rejetées</span><span class="sxs-lookup"><span data-stu-id="974f5-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-257">Quantité totale de demandes réussies</span><span class="sxs-lookup"><span data-stu-id="974f5-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="974f5-258">Quantité totale de demandes effectuées au service de mobilité et ayant réussi</span><span class="sxs-lookup"><span data-stu-id="974f5-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-259">Total de sessions initiées</span><span class="sxs-lookup"><span data-stu-id="974f5-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="974f5-260">Quantité totale de sessions qui ont été initiées depuis le démarrage du service de mobilité</span><span class="sxs-lookup"><span data-stu-id="974f5-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-261">Total des sessions terminées pour inactivité utilisateur</span><span class="sxs-lookup"><span data-stu-id="974f5-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="974f5-262">Quantité totale de sessions qui ont été terminées suite à l’expiration du délai d’inactivité utilisateur</span><span class="sxs-lookup"><span data-stu-id="974f5-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="974f5-263">Quantité totale d’appels vocaux entrants réussis</span><span class="sxs-lookup"><span data-stu-id="974f5-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="974f5-264">Quantité totale d’appels vocaux entrants ayant été réussis</span><span class="sxs-lookup"><span data-stu-id="974f5-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="974f5-265">Quantité totale d’appels vocaux sortants réussis</span><span class="sxs-lookup"><span data-stu-id="974f5-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="974f5-266">Quantité totale d’appels vocaux sortants ayant été réussis</span><span class="sxs-lookup"><span data-stu-id="974f5-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

