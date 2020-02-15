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
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="2296b-102">Événements UCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2296b-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2296b-103">_**Dernière modification de la rubrique :** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="2296b-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="2296b-104">Lync Server 2013 utilise l’API Web de communications unifiées (UCWA) à différentes fins, de l’accès à Microsoft Exchange pour les recherches de contacts à la mise à jour de la présence des clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="2296b-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="2296b-105">UCWA écrit des enregistrements de comportement opérationnel sous forme d’informations de type d’événement, d’avertissement et d’erreur.</span><span class="sxs-lookup"><span data-stu-id="2296b-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="2296b-106">Le tableau suivant décrit les événements qui peuvent être écrits par les composants UCWA.</span><span class="sxs-lookup"><span data-stu-id="2296b-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2296b-107">ID d’évènement</span><span class="sxs-lookup"><span data-stu-id="2296b-107">Event ID</span></span></th>
<th><span data-ttu-id="2296b-108">Type d'événement</span><span class="sxs-lookup"><span data-stu-id="2296b-108">Event Type</span></span></th>
<th><span data-ttu-id="2296b-109">Résumé</span><span class="sxs-lookup"><span data-stu-id="2296b-109">Summary</span></span></th>
<th><span data-ttu-id="2296b-110">Cause et résolution</span><span class="sxs-lookup"><span data-stu-id="2296b-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2296b-111">20001</span><span class="sxs-lookup"><span data-stu-id="2296b-111">20001</span></span></p></td>
<td><p><span data-ttu-id="2296b-112">Message d’information</span><span class="sxs-lookup"><span data-stu-id="2296b-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="2296b-113">UCWA initialisé</span><span class="sxs-lookup"><span data-stu-id="2296b-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="2296b-114">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-114">N/A</span></span></p>
<p><span data-ttu-id="2296b-115">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-116">20002</span><span class="sxs-lookup"><span data-stu-id="2296b-116">20002</span></span></p></td>
<td><p><span data-ttu-id="2296b-117">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-117">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-118">UCWA a rencontré une exception inattendue lors de l’initialisation</span><span class="sxs-lookup"><span data-stu-id="2296b-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="2296b-119">Une erreur inattendue s’est produite lors de l’initialisation</span><span class="sxs-lookup"><span data-stu-id="2296b-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="2296b-120">Examiner les détails de l’exception dans l’entrée du journal des événements associé afin de déterminer la cause possible</span><span class="sxs-lookup"><span data-stu-id="2296b-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-121">20003</span><span class="sxs-lookup"><span data-stu-id="2296b-121">20003</span></span></p></td>
<td><p><span data-ttu-id="2296b-122">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-122">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-123">UCWA a rencontré une exception non gérée</span><span class="sxs-lookup"><span data-stu-id="2296b-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="2296b-124">Une exception non gérée s’est produite</span><span class="sxs-lookup"><span data-stu-id="2296b-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="2296b-125">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="2296b-125">Restart the server.</span></span> <span data-ttu-id="2296b-126">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="2296b-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-127">20004</span><span class="sxs-lookup"><span data-stu-id="2296b-127">20004</span></span></p></td>
<td><p><span data-ttu-id="2296b-128">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-128">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-129">Impossible d’accéder à Exchange pour la photo HD</span><span class="sxs-lookup"><span data-stu-id="2296b-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="2296b-130">La connexion à Exchange n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="2296b-131">Assurez-vous que la connexion à Exchange est disponible.</span><span class="sxs-lookup"><span data-stu-id="2296b-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-132">20005</span><span class="sxs-lookup"><span data-stu-id="2296b-132">20005</span></span></p></td>
<td><p><span data-ttu-id="2296b-133">Message d’information</span><span class="sxs-lookup"><span data-stu-id="2296b-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="2296b-134">Récupération de l’échec de l’accès à Exchange pour la photo HD</span><span class="sxs-lookup"><span data-stu-id="2296b-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="2296b-135">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-136">20006</span><span class="sxs-lookup"><span data-stu-id="2296b-136">20006</span></span></p></td>
<td><p><span data-ttu-id="2296b-137">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-137">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-138">Impossible d’accéder à Exchange pour la recherche de contact</span><span class="sxs-lookup"><span data-stu-id="2296b-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="2296b-139">La connexion à Exchange n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="2296b-140">Assurez-vous que la connexion à Exchange est disponible.</span><span class="sxs-lookup"><span data-stu-id="2296b-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-141">20007</span><span class="sxs-lookup"><span data-stu-id="2296b-141">20007</span></span></p></td>
<td><p><span data-ttu-id="2296b-142">Message d’information</span><span class="sxs-lookup"><span data-stu-id="2296b-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="2296b-143">Récupération d’un contact de recherche inversement dans Exchange</span><span class="sxs-lookup"><span data-stu-id="2296b-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="2296b-144">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-145">20008</span><span class="sxs-lookup"><span data-stu-id="2296b-145">20008</span></span></p></td>
<td><p><span data-ttu-id="2296b-146">Avertissement</span><span class="sxs-lookup"><span data-stu-id="2296b-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="2296b-147">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par application</span><span class="sxs-lookup"><span data-stu-id="2296b-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="2296b-148">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par application</span><span class="sxs-lookup"><span data-stu-id="2296b-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="2296b-149">Vérifier les clients pour les abonnements inutiles</span><span class="sxs-lookup"><span data-stu-id="2296b-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-150">20009</span><span class="sxs-lookup"><span data-stu-id="2296b-150">20009</span></span></p></td>
<td><p><span data-ttu-id="2296b-151">Avertissement</span><span class="sxs-lookup"><span data-stu-id="2296b-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="2296b-152">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="2296b-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="2296b-153">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="2296b-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="2296b-154">Vérifier les clients pour les abonnements inutiles</span><span class="sxs-lookup"><span data-stu-id="2296b-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-155">20010</span><span class="sxs-lookup"><span data-stu-id="2296b-155">20010</span></span></p></td>
<td><p><span data-ttu-id="2296b-156">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-156">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-157">Impossible de récupérer les données inbande</span><span class="sxs-lookup"><span data-stu-id="2296b-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="2296b-158">Impossible de récupérer les données inbande</span><span class="sxs-lookup"><span data-stu-id="2296b-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="2296b-159">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="2296b-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-160">20011</span><span class="sxs-lookup"><span data-stu-id="2296b-160">20011</span></span></p></td>
<td><p><span data-ttu-id="2296b-161">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-161">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-162">Impossible de s’abonner à la présence</span><span class="sxs-lookup"><span data-stu-id="2296b-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="2296b-163">Impossible de s’abonner à la présence</span><span class="sxs-lookup"><span data-stu-id="2296b-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="2296b-164">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="2296b-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-165">20012</span><span class="sxs-lookup"><span data-stu-id="2296b-165">20012</span></span></p></td>
<td><p><span data-ttu-id="2296b-166">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-166">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-167">Échec de l’enregistrement du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="2296b-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="2296b-168">Échec de l’enregistrement du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="2296b-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="2296b-169">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="2296b-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-170">20013</span><span class="sxs-lookup"><span data-stu-id="2296b-170">20013</span></span></p></td>
<td><p><span data-ttu-id="2296b-171">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-171">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-172">Le MCU de messagerie instantanée n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2296b-173">Le MCU de messagerie instantanée n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="2296b-174">Vérifier si la MCU de messagerie instantanée est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2296b-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-175">20014</span><span class="sxs-lookup"><span data-stu-id="2296b-175">20014</span></span></p></td>
<td><p><span data-ttu-id="2296b-176">Message d’information</span><span class="sxs-lookup"><span data-stu-id="2296b-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="2296b-177">Récupération de l’échec de la connexion au MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="2296b-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="2296b-178">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-179">20015</span><span class="sxs-lookup"><span data-stu-id="2296b-179">20015</span></span></p></td>
<td><p><span data-ttu-id="2296b-180">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-180">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-181">Le MCU AV n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2296b-182">Le MCU AV n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="2296b-183">Vérifier si le MCU AV est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2296b-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-184">20016</span><span class="sxs-lookup"><span data-stu-id="2296b-184">20016</span></span></p></td>
<td><p><span data-ttu-id="2296b-185">Message d’information</span><span class="sxs-lookup"><span data-stu-id="2296b-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="2296b-186">Récupération de l’échec de la connexion au MCU AV</span><span class="sxs-lookup"><span data-stu-id="2296b-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="2296b-187">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-188">20017</span><span class="sxs-lookup"><span data-stu-id="2296b-188">20017</span></span></p></td>
<td><p><span data-ttu-id="2296b-189">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-189">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-190">CAR MCU n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2296b-191">CAR MCU n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="2296b-192">Voir si MCU est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2296b-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-193">20018</span><span class="sxs-lookup"><span data-stu-id="2296b-193">20018</span></span></p></td>
<td><p><span data-ttu-id="2296b-194">Message d’information</span><span class="sxs-lookup"><span data-stu-id="2296b-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="2296b-195">Récupération de l’échec de la connexion à MCU</span><span class="sxs-lookup"><span data-stu-id="2296b-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="2296b-196">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-197">20019</span><span class="sxs-lookup"><span data-stu-id="2296b-197">20019</span></span></p></td>
<td><p><span data-ttu-id="2296b-198">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-198">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-199">Le MCU de données n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2296b-200">Le MCU de données n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="2296b-201">Vérifier si le MCU de données est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2296b-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-202">20020</span><span class="sxs-lookup"><span data-stu-id="2296b-202">20020</span></span></p></td>
<td><p><span data-ttu-id="2296b-203">Message d’information</span><span class="sxs-lookup"><span data-stu-id="2296b-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="2296b-204">Récupération de l’échec de la connexion au MCU de données</span><span class="sxs-lookup"><span data-stu-id="2296b-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="2296b-205">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-206">20021</span><span class="sxs-lookup"><span data-stu-id="2296b-206">20021</span></span></p></td>
<td><p><span data-ttu-id="2296b-207">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-207">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-208">Impossible de rejoindre la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="2296b-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="2296b-209">Impossible de rejoindre la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="2296b-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="2296b-210">Vérifier si la MCU de messagerie instantanée est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2296b-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-211">20022</span><span class="sxs-lookup"><span data-stu-id="2296b-211">20022</span></span></p></td>
<td><p><span data-ttu-id="2296b-212">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-212">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-213">Impossible de rejoindre le MCU AV</span><span class="sxs-lookup"><span data-stu-id="2296b-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="2296b-214">Impossible de rejoindre le MCU AV</span><span class="sxs-lookup"><span data-stu-id="2296b-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="2296b-215">Vérifier si le MCU AV est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2296b-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-216">20023</span><span class="sxs-lookup"><span data-stu-id="2296b-216">20023</span></span></p></td>
<td><p><span data-ttu-id="2296b-217">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-217">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-218">Impossible de rejoindre en tant que MCU</span><span class="sxs-lookup"><span data-stu-id="2296b-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="2296b-219">Impossible de rejoindre en tant que MCU</span><span class="sxs-lookup"><span data-stu-id="2296b-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="2296b-220">Voir si MCU est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2296b-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-221">20024</span><span class="sxs-lookup"><span data-stu-id="2296b-221">20024</span></span></p></td>
<td><p><span data-ttu-id="2296b-222">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-222">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-223">Impossible de rejoindre le MCU de données</span><span class="sxs-lookup"><span data-stu-id="2296b-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="2296b-224">Impossible de rejoindre le MCU de données</span><span class="sxs-lookup"><span data-stu-id="2296b-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="2296b-225">Vérifier si le MCU de données est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2296b-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-226">20025</span><span class="sxs-lookup"><span data-stu-id="2296b-226">20025</span></span></p></td>
<td><p><span data-ttu-id="2296b-227">Error</span><span class="sxs-lookup"><span data-stu-id="2296b-227">Error</span></span></p></td>
<td><p><span data-ttu-id="2296b-228">Impossible d’accéder à Active Directory pour la photo</span><span class="sxs-lookup"><span data-stu-id="2296b-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="2296b-229">La connexion à Active Directory n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="2296b-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="2296b-230">Assurez-vous que la connexion à Active Directory est disponible.</span><span class="sxs-lookup"><span data-stu-id="2296b-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2296b-231">20026</span><span class="sxs-lookup"><span data-stu-id="2296b-231">20026</span></span></p></td>
<td><p><span data-ttu-id="2296b-232">Message d’information</span><span class="sxs-lookup"><span data-stu-id="2296b-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="2296b-233">Récupération de l’échec de l’accès à Active Directory pour la photo</span><span class="sxs-lookup"><span data-stu-id="2296b-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="2296b-234">N/A</span><span class="sxs-lookup"><span data-stu-id="2296b-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2296b-235">20027</span><span class="sxs-lookup"><span data-stu-id="2296b-235">20027</span></span></p></td>
<td><p><span data-ttu-id="2296b-236">Avertissement</span><span class="sxs-lookup"><span data-stu-id="2296b-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="2296b-237">Impossible de désérialiser</span><span class="sxs-lookup"><span data-stu-id="2296b-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="2296b-238">Impossible de désérialiser</span><span class="sxs-lookup"><span data-stu-id="2296b-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="2296b-239">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="2296b-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

