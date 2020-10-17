---
title: 'Lync Server 2013 : événements UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae71fa6e91c0bc212bc019b1afa85ebcacb4d0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527791"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="3621f-102">Événements UCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3621f-102">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3621f-103">_**Dernière modification de la rubrique :** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="3621f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="3621f-104">Lync Server 2013 utilise l’API Web de communications unifiées (UCWA) à différentes fins, de l’accès à Microsoft Exchange pour les recherches de contacts à la mise à jour de la présence des clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="3621f-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="3621f-105">UCWA écrit des enregistrements de comportement opérationnel sous forme d’informations de type d’événement, d’avertissement et d’erreur.</span><span class="sxs-lookup"><span data-stu-id="3621f-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="3621f-106">Le tableau suivant décrit les événements qui peuvent être écrits par les composants UCWA.</span><span class="sxs-lookup"><span data-stu-id="3621f-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3621f-107">ID d’évènement</span><span class="sxs-lookup"><span data-stu-id="3621f-107">Event ID</span></span></th>
<th><span data-ttu-id="3621f-108">Type d'événement</span><span class="sxs-lookup"><span data-stu-id="3621f-108">Event Type</span></span></th>
<th><span data-ttu-id="3621f-109">Résumé</span><span class="sxs-lookup"><span data-stu-id="3621f-109">Summary</span></span></th>
<th><span data-ttu-id="3621f-110">Cause et résolution</span><span class="sxs-lookup"><span data-stu-id="3621f-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3621f-111">20001</span><span class="sxs-lookup"><span data-stu-id="3621f-111">20001</span></span></p></td>
<td><p><span data-ttu-id="3621f-112">Message d’information</span><span class="sxs-lookup"><span data-stu-id="3621f-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="3621f-113">UCWA initialisé</span><span class="sxs-lookup"><span data-stu-id="3621f-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="3621f-114">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-114">N/A</span></span></p>
<p><span data-ttu-id="3621f-115">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-116">20002</span><span class="sxs-lookup"><span data-stu-id="3621f-116">20002</span></span></p></td>
<td><p><span data-ttu-id="3621f-117">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-117">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-118">UCWA a rencontré une exception inattendue lors de l’initialisation</span><span class="sxs-lookup"><span data-stu-id="3621f-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="3621f-119">Une erreur inattendue s’est produite lors de l’initialisation</span><span class="sxs-lookup"><span data-stu-id="3621f-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="3621f-120">Examiner les détails de l’exception dans l’entrée du journal des événements associé afin de déterminer la cause possible</span><span class="sxs-lookup"><span data-stu-id="3621f-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-121">20003</span><span class="sxs-lookup"><span data-stu-id="3621f-121">20003</span></span></p></td>
<td><p><span data-ttu-id="3621f-122">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-122">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-123">UCWA a rencontré une exception non gérée</span><span class="sxs-lookup"><span data-stu-id="3621f-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="3621f-124">Une exception non gérée s’est produite</span><span class="sxs-lookup"><span data-stu-id="3621f-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="3621f-125">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="3621f-125">Restart the server.</span></span> <span data-ttu-id="3621f-126">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="3621f-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-127">20004</span><span class="sxs-lookup"><span data-stu-id="3621f-127">20004</span></span></p></td>
<td><p><span data-ttu-id="3621f-128">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-128">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-129">Impossible d’accéder à Exchange pour la photo HD</span><span class="sxs-lookup"><span data-stu-id="3621f-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="3621f-130">La connexion à Exchange n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="3621f-131">Assurez-vous que la connexion à Exchange est disponible.</span><span class="sxs-lookup"><span data-stu-id="3621f-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-132">20005</span><span class="sxs-lookup"><span data-stu-id="3621f-132">20005</span></span></p></td>
<td><p><span data-ttu-id="3621f-133">Message d’information</span><span class="sxs-lookup"><span data-stu-id="3621f-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="3621f-134">Récupération de l’échec de l’accès à Exchange pour la photo HD</span><span class="sxs-lookup"><span data-stu-id="3621f-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="3621f-135">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-136">20006</span><span class="sxs-lookup"><span data-stu-id="3621f-136">20006</span></span></p></td>
<td><p><span data-ttu-id="3621f-137">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-137">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-138">Impossible d’accéder à Exchange pour la recherche de contact</span><span class="sxs-lookup"><span data-stu-id="3621f-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="3621f-139">La connexion à Exchange n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="3621f-140">Assurez-vous que la connexion à Exchange est disponible.</span><span class="sxs-lookup"><span data-stu-id="3621f-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-141">20007</span><span class="sxs-lookup"><span data-stu-id="3621f-141">20007</span></span></p></td>
<td><p><span data-ttu-id="3621f-142">Message d’information</span><span class="sxs-lookup"><span data-stu-id="3621f-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="3621f-143">Récupération d’un contact de recherche inversement dans Exchange</span><span class="sxs-lookup"><span data-stu-id="3621f-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="3621f-144">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-145">20008</span><span class="sxs-lookup"><span data-stu-id="3621f-145">20008</span></span></p></td>
<td><p><span data-ttu-id="3621f-146">Avertissement</span><span class="sxs-lookup"><span data-stu-id="3621f-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="3621f-147">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par application</span><span class="sxs-lookup"><span data-stu-id="3621f-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="3621f-148">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par application</span><span class="sxs-lookup"><span data-stu-id="3621f-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="3621f-149">Vérifier les clients pour les abonnements inutiles</span><span class="sxs-lookup"><span data-stu-id="3621f-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-150">20009</span><span class="sxs-lookup"><span data-stu-id="3621f-150">20009</span></span></p></td>
<td><p><span data-ttu-id="3621f-151">Avertissement</span><span class="sxs-lookup"><span data-stu-id="3621f-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="3621f-152">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="3621f-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="3621f-153">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="3621f-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="3621f-154">Vérifier les clients pour les abonnements inutiles</span><span class="sxs-lookup"><span data-stu-id="3621f-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-155">20010</span><span class="sxs-lookup"><span data-stu-id="3621f-155">20010</span></span></p></td>
<td><p><span data-ttu-id="3621f-156">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-156">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-157">Impossible de récupérer les données inbande</span><span class="sxs-lookup"><span data-stu-id="3621f-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="3621f-158">Impossible de récupérer les données inbande</span><span class="sxs-lookup"><span data-stu-id="3621f-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="3621f-159">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="3621f-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-160">20011</span><span class="sxs-lookup"><span data-stu-id="3621f-160">20011</span></span></p></td>
<td><p><span data-ttu-id="3621f-161">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-161">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-162">Impossible de s’abonner à la présence</span><span class="sxs-lookup"><span data-stu-id="3621f-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="3621f-163">Impossible de s’abonner à la présence</span><span class="sxs-lookup"><span data-stu-id="3621f-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="3621f-164">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="3621f-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-165">20012</span><span class="sxs-lookup"><span data-stu-id="3621f-165">20012</span></span></p></td>
<td><p><span data-ttu-id="3621f-166">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-166">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-167">Échec de l’enregistrement du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="3621f-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="3621f-168">Échec de l’enregistrement du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="3621f-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="3621f-169">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="3621f-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-170">20013</span><span class="sxs-lookup"><span data-stu-id="3621f-170">20013</span></span></p></td>
<td><p><span data-ttu-id="3621f-171">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-171">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-172">Le MCU de messagerie instantanée n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="3621f-173">Le MCU de messagerie instantanée n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="3621f-174">Vérifier si la MCU de messagerie instantanée est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="3621f-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-175">20014</span><span class="sxs-lookup"><span data-stu-id="3621f-175">20014</span></span></p></td>
<td><p><span data-ttu-id="3621f-176">Message d’information</span><span class="sxs-lookup"><span data-stu-id="3621f-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="3621f-177">Récupération de l’échec de la connexion au MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="3621f-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="3621f-178">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-179">20015</span><span class="sxs-lookup"><span data-stu-id="3621f-179">20015</span></span></p></td>
<td><p><span data-ttu-id="3621f-180">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-180">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-181">Le MCU AV n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="3621f-182">Le MCU AV n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="3621f-183">Vérifier si le MCU AV est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="3621f-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-184">20016</span><span class="sxs-lookup"><span data-stu-id="3621f-184">20016</span></span></p></td>
<td><p><span data-ttu-id="3621f-185">Message d’information</span><span class="sxs-lookup"><span data-stu-id="3621f-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="3621f-186">Récupération de l’échec de la connexion au MCU AV</span><span class="sxs-lookup"><span data-stu-id="3621f-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="3621f-187">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-188">20017</span><span class="sxs-lookup"><span data-stu-id="3621f-188">20017</span></span></p></td>
<td><p><span data-ttu-id="3621f-189">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-189">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-190">CAR MCU n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="3621f-191">CAR MCU n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="3621f-192">Voir si MCU est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="3621f-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-193">20018</span><span class="sxs-lookup"><span data-stu-id="3621f-193">20018</span></span></p></td>
<td><p><span data-ttu-id="3621f-194">Message d’information</span><span class="sxs-lookup"><span data-stu-id="3621f-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="3621f-195">Récupération de l’échec de la connexion à MCU</span><span class="sxs-lookup"><span data-stu-id="3621f-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="3621f-196">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-197">20019</span><span class="sxs-lookup"><span data-stu-id="3621f-197">20019</span></span></p></td>
<td><p><span data-ttu-id="3621f-198">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-198">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-199">Le MCU de données n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="3621f-200">Le MCU de données n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="3621f-201">Vérifier si le MCU de données est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="3621f-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-202">20020</span><span class="sxs-lookup"><span data-stu-id="3621f-202">20020</span></span></p></td>
<td><p><span data-ttu-id="3621f-203">Message d’information</span><span class="sxs-lookup"><span data-stu-id="3621f-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="3621f-204">Récupération de l’échec de la connexion au MCU de données</span><span class="sxs-lookup"><span data-stu-id="3621f-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="3621f-205">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-206">20021</span><span class="sxs-lookup"><span data-stu-id="3621f-206">20021</span></span></p></td>
<td><p><span data-ttu-id="3621f-207">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-207">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-208">Impossible de rejoindre la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="3621f-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="3621f-209">Impossible de rejoindre la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="3621f-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="3621f-210">Vérifier si la MCU de messagerie instantanée est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="3621f-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-211">20022</span><span class="sxs-lookup"><span data-stu-id="3621f-211">20022</span></span></p></td>
<td><p><span data-ttu-id="3621f-212">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-212">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-213">Impossible de rejoindre le MCU AV</span><span class="sxs-lookup"><span data-stu-id="3621f-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="3621f-214">Impossible de rejoindre le MCU AV</span><span class="sxs-lookup"><span data-stu-id="3621f-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="3621f-215">Vérifier si le MCU AV est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="3621f-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-216">20023</span><span class="sxs-lookup"><span data-stu-id="3621f-216">20023</span></span></p></td>
<td><p><span data-ttu-id="3621f-217">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-217">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-218">Impossible de rejoindre en tant que MCU</span><span class="sxs-lookup"><span data-stu-id="3621f-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="3621f-219">Impossible de rejoindre en tant que MCU</span><span class="sxs-lookup"><span data-stu-id="3621f-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="3621f-220">Voir si MCU est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="3621f-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-221">20024</span><span class="sxs-lookup"><span data-stu-id="3621f-221">20024</span></span></p></td>
<td><p><span data-ttu-id="3621f-222">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-222">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-223">Impossible de rejoindre le MCU de données</span><span class="sxs-lookup"><span data-stu-id="3621f-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="3621f-224">Impossible de rejoindre le MCU de données</span><span class="sxs-lookup"><span data-stu-id="3621f-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="3621f-225">Vérifier si le MCU de données est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="3621f-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-226">20025</span><span class="sxs-lookup"><span data-stu-id="3621f-226">20025</span></span></p></td>
<td><p><span data-ttu-id="3621f-227">Erreur</span><span class="sxs-lookup"><span data-stu-id="3621f-227">Error</span></span></p></td>
<td><p><span data-ttu-id="3621f-228">Impossible d’accéder à Active Directory pour la photo</span><span class="sxs-lookup"><span data-stu-id="3621f-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="3621f-229">La connexion à Active Directory n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="3621f-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="3621f-230">Assurez-vous que la connexion à Active Directory est disponible.</span><span class="sxs-lookup"><span data-stu-id="3621f-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3621f-231">20026</span><span class="sxs-lookup"><span data-stu-id="3621f-231">20026</span></span></p></td>
<td><p><span data-ttu-id="3621f-232">Message d’information</span><span class="sxs-lookup"><span data-stu-id="3621f-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="3621f-233">Récupération de l’échec de l’accès à Active Directory pour la photo</span><span class="sxs-lookup"><span data-stu-id="3621f-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="3621f-234">N/A</span><span class="sxs-lookup"><span data-stu-id="3621f-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3621f-235">20027</span><span class="sxs-lookup"><span data-stu-id="3621f-235">20027</span></span></p></td>
<td><p><span data-ttu-id="3621f-236">Avertissement</span><span class="sxs-lookup"><span data-stu-id="3621f-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="3621f-237">Impossible de désérialiser</span><span class="sxs-lookup"><span data-stu-id="3621f-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="3621f-238">Impossible de désérialiser</span><span class="sxs-lookup"><span data-stu-id="3621f-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="3621f-239">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="3621f-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

