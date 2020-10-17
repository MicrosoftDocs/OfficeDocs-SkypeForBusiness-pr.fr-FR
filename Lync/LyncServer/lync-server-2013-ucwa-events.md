---
title: 'Lync Server 2013 : événements UCWA'
description: 'Lync Server 2013 : événements UCWA.'
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
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548850"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="a5afb-103">Événements UCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5afb-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5afb-104">_**Dernière modification de la rubrique :** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="a5afb-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="a5afb-105">Lync Server 2013 utilise l’API Web de communications unifiées (UCWA) à différentes fins, de l’accès à Microsoft Exchange pour les recherches de contacts à la mise à jour de la présence des clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="a5afb-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="a5afb-106">UCWA écrit des enregistrements de comportement opérationnel sous forme d’informations de type d’événement, d’avertissement et d’erreur.</span><span class="sxs-lookup"><span data-stu-id="a5afb-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="a5afb-107">Le tableau suivant décrit les événements qui peuvent être écrits par les composants UCWA.</span><span class="sxs-lookup"><span data-stu-id="a5afb-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5afb-108">ID d’évènement</span><span class="sxs-lookup"><span data-stu-id="a5afb-108">Event ID</span></span></th>
<th><span data-ttu-id="a5afb-109">Type d'événement</span><span class="sxs-lookup"><span data-stu-id="a5afb-109">Event Type</span></span></th>
<th><span data-ttu-id="a5afb-110">Résumé</span><span class="sxs-lookup"><span data-stu-id="a5afb-110">Summary</span></span></th>
<th><span data-ttu-id="a5afb-111">Cause et résolution</span><span class="sxs-lookup"><span data-stu-id="a5afb-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-112">20001</span><span class="sxs-lookup"><span data-stu-id="a5afb-112">20001</span></span></p></td>
<td><p><span data-ttu-id="a5afb-113">Message d’information</span><span class="sxs-lookup"><span data-stu-id="a5afb-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="a5afb-114">UCWA initialisé</span><span class="sxs-lookup"><span data-stu-id="a5afb-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="a5afb-115">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-115">N/A</span></span></p>
<p><span data-ttu-id="a5afb-116">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-117">20002</span><span class="sxs-lookup"><span data-stu-id="a5afb-117">20002</span></span></p></td>
<td><p><span data-ttu-id="a5afb-118">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-118">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-119">UCWA a rencontré une exception inattendue lors de l’initialisation</span><span class="sxs-lookup"><span data-stu-id="a5afb-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="a5afb-120">Une erreur inattendue s’est produite lors de l’initialisation</span><span class="sxs-lookup"><span data-stu-id="a5afb-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="a5afb-121">Examiner les détails de l’exception dans l’entrée du journal des événements associé afin de déterminer la cause possible</span><span class="sxs-lookup"><span data-stu-id="a5afb-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-122">20003</span><span class="sxs-lookup"><span data-stu-id="a5afb-122">20003</span></span></p></td>
<td><p><span data-ttu-id="a5afb-123">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-123">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-124">UCWA a rencontré une exception non gérée</span><span class="sxs-lookup"><span data-stu-id="a5afb-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="a5afb-125">Une exception non gérée s’est produite</span><span class="sxs-lookup"><span data-stu-id="a5afb-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="a5afb-126">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="a5afb-126">Restart the server.</span></span> <span data-ttu-id="a5afb-127">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="a5afb-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-128">20004</span><span class="sxs-lookup"><span data-stu-id="a5afb-128">20004</span></span></p></td>
<td><p><span data-ttu-id="a5afb-129">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-129">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-130">Impossible d’accéder à Exchange pour la photo HD</span><span class="sxs-lookup"><span data-stu-id="a5afb-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a5afb-131">La connexion à Exchange n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a5afb-132">Assurez-vous que la connexion à Exchange est disponible.</span><span class="sxs-lookup"><span data-stu-id="a5afb-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-133">20005</span><span class="sxs-lookup"><span data-stu-id="a5afb-133">20005</span></span></p></td>
<td><p><span data-ttu-id="a5afb-134">Message d’information</span><span class="sxs-lookup"><span data-stu-id="a5afb-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="a5afb-135">Récupération de l’échec de l’accès à Exchange pour la photo HD</span><span class="sxs-lookup"><span data-stu-id="a5afb-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a5afb-136">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-137">20006</span><span class="sxs-lookup"><span data-stu-id="a5afb-137">20006</span></span></p></td>
<td><p><span data-ttu-id="a5afb-138">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-138">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-139">Impossible d’accéder à Exchange pour la recherche de contact</span><span class="sxs-lookup"><span data-stu-id="a5afb-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="a5afb-140">La connexion à Exchange n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a5afb-141">Assurez-vous que la connexion à Exchange est disponible.</span><span class="sxs-lookup"><span data-stu-id="a5afb-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-142">20007</span><span class="sxs-lookup"><span data-stu-id="a5afb-142">20007</span></span></p></td>
<td><p><span data-ttu-id="a5afb-143">Message d’information</span><span class="sxs-lookup"><span data-stu-id="a5afb-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="a5afb-144">Récupération d’un contact de recherche inversement dans Exchange</span><span class="sxs-lookup"><span data-stu-id="a5afb-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="a5afb-145">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-146">20008</span><span class="sxs-lookup"><span data-stu-id="a5afb-146">20008</span></span></p></td>
<td><p><span data-ttu-id="a5afb-147">Avertissement</span><span class="sxs-lookup"><span data-stu-id="a5afb-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="a5afb-148">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par application</span><span class="sxs-lookup"><span data-stu-id="a5afb-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="a5afb-149">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par application</span><span class="sxs-lookup"><span data-stu-id="a5afb-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="a5afb-150">Vérifier les clients pour les abonnements inutiles</span><span class="sxs-lookup"><span data-stu-id="a5afb-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-151">20009</span><span class="sxs-lookup"><span data-stu-id="a5afb-151">20009</span></span></p></td>
<td><p><span data-ttu-id="a5afb-152">Avertissement</span><span class="sxs-lookup"><span data-stu-id="a5afb-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="a5afb-153">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="a5afb-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="a5afb-154">Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="a5afb-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="a5afb-155">Vérifier les clients pour les abonnements inutiles</span><span class="sxs-lookup"><span data-stu-id="a5afb-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-156">20010</span><span class="sxs-lookup"><span data-stu-id="a5afb-156">20010</span></span></p></td>
<td><p><span data-ttu-id="a5afb-157">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-157">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-158">Impossible de récupérer les données inbande</span><span class="sxs-lookup"><span data-stu-id="a5afb-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="a5afb-159">Impossible de récupérer les données inbande</span><span class="sxs-lookup"><span data-stu-id="a5afb-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="a5afb-160">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="a5afb-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-161">20011</span><span class="sxs-lookup"><span data-stu-id="a5afb-161">20011</span></span></p></td>
<td><p><span data-ttu-id="a5afb-162">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-162">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-163">Impossible de s’abonner à la présence</span><span class="sxs-lookup"><span data-stu-id="a5afb-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="a5afb-164">Impossible de s’abonner à la présence</span><span class="sxs-lookup"><span data-stu-id="a5afb-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="a5afb-165">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="a5afb-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-166">20012</span><span class="sxs-lookup"><span data-stu-id="a5afb-166">20012</span></span></p></td>
<td><p><span data-ttu-id="a5afb-167">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-167">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-168">Échec de l’enregistrement du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="a5afb-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="a5afb-169">Échec de l’enregistrement du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="a5afb-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="a5afb-170">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="a5afb-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-171">20013</span><span class="sxs-lookup"><span data-stu-id="a5afb-171">20013</span></span></p></td>
<td><p><span data-ttu-id="a5afb-172">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-172">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-173">Le MCU de messagerie instantanée n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a5afb-174">Le MCU de messagerie instantanée n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="a5afb-175">Vérifier si la MCU de messagerie instantanée est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="a5afb-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-176">20014</span><span class="sxs-lookup"><span data-stu-id="a5afb-176">20014</span></span></p></td>
<td><p><span data-ttu-id="a5afb-177">Message d’information</span><span class="sxs-lookup"><span data-stu-id="a5afb-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="a5afb-178">Récupération de l’échec de la connexion au MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="a5afb-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a5afb-179">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-180">20015</span><span class="sxs-lookup"><span data-stu-id="a5afb-180">20015</span></span></p></td>
<td><p><span data-ttu-id="a5afb-181">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-181">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-182">Le MCU AV n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a5afb-183">Le MCU AV n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="a5afb-184">Vérifier si le MCU AV est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="a5afb-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-185">20016</span><span class="sxs-lookup"><span data-stu-id="a5afb-185">20016</span></span></p></td>
<td><p><span data-ttu-id="a5afb-186">Message d’information</span><span class="sxs-lookup"><span data-stu-id="a5afb-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="a5afb-187">Récupération de l’échec de la connexion au MCU AV</span><span class="sxs-lookup"><span data-stu-id="a5afb-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a5afb-188">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-189">20017</span><span class="sxs-lookup"><span data-stu-id="a5afb-189">20017</span></span></p></td>
<td><p><span data-ttu-id="a5afb-190">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-190">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-191">CAR MCU n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a5afb-192">CAR MCU n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="a5afb-193">Voir si MCU est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="a5afb-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-194">20018</span><span class="sxs-lookup"><span data-stu-id="a5afb-194">20018</span></span></p></td>
<td><p><span data-ttu-id="a5afb-195">Message d’information</span><span class="sxs-lookup"><span data-stu-id="a5afb-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="a5afb-196">Récupération de l’échec de la connexion à MCU</span><span class="sxs-lookup"><span data-stu-id="a5afb-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a5afb-197">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-198">20019</span><span class="sxs-lookup"><span data-stu-id="a5afb-198">20019</span></span></p></td>
<td><p><span data-ttu-id="a5afb-199">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-199">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-200">Le MCU de données n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a5afb-201">Le MCU de données n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="a5afb-202">Vérifier si le MCU de données est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="a5afb-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-203">20020</span><span class="sxs-lookup"><span data-stu-id="a5afb-203">20020</span></span></p></td>
<td><p><span data-ttu-id="a5afb-204">Message d’information</span><span class="sxs-lookup"><span data-stu-id="a5afb-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="a5afb-205">Récupération de l’échec de la connexion au MCU de données</span><span class="sxs-lookup"><span data-stu-id="a5afb-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a5afb-206">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-207">20021</span><span class="sxs-lookup"><span data-stu-id="a5afb-207">20021</span></span></p></td>
<td><p><span data-ttu-id="a5afb-208">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-208">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-209">Impossible de rejoindre la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="a5afb-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a5afb-210">Impossible de rejoindre la MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="a5afb-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="a5afb-211">Vérifier si la MCU de messagerie instantanée est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="a5afb-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-212">20022</span><span class="sxs-lookup"><span data-stu-id="a5afb-212">20022</span></span></p></td>
<td><p><span data-ttu-id="a5afb-213">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-213">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-214">Impossible de rejoindre le MCU AV</span><span class="sxs-lookup"><span data-stu-id="a5afb-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a5afb-215">Impossible de rejoindre le MCU AV</span><span class="sxs-lookup"><span data-stu-id="a5afb-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="a5afb-216">Vérifier si le MCU AV est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="a5afb-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-217">20023</span><span class="sxs-lookup"><span data-stu-id="a5afb-217">20023</span></span></p></td>
<td><p><span data-ttu-id="a5afb-218">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-218">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-219">Impossible de rejoindre en tant que MCU</span><span class="sxs-lookup"><span data-stu-id="a5afb-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a5afb-220">Impossible de rejoindre en tant que MCU</span><span class="sxs-lookup"><span data-stu-id="a5afb-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="a5afb-221">Voir si MCU est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="a5afb-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-222">20024</span><span class="sxs-lookup"><span data-stu-id="a5afb-222">20024</span></span></p></td>
<td><p><span data-ttu-id="a5afb-223">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-223">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-224">Impossible de rejoindre le MCU de données</span><span class="sxs-lookup"><span data-stu-id="a5afb-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a5afb-225">Impossible de rejoindre le MCU de données</span><span class="sxs-lookup"><span data-stu-id="a5afb-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="a5afb-226">Vérifier si le MCU de données est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="a5afb-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-227">20025</span><span class="sxs-lookup"><span data-stu-id="a5afb-227">20025</span></span></p></td>
<td><p><span data-ttu-id="a5afb-228">Erreur</span><span class="sxs-lookup"><span data-stu-id="a5afb-228">Error</span></span></p></td>
<td><p><span data-ttu-id="a5afb-229">Impossible d’accéder à Active Directory pour la photo</span><span class="sxs-lookup"><span data-stu-id="a5afb-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a5afb-230">La connexion à Active Directory n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="a5afb-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="a5afb-231">Assurez-vous que la connexion à Active Directory est disponible.</span><span class="sxs-lookup"><span data-stu-id="a5afb-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5afb-232">20026</span><span class="sxs-lookup"><span data-stu-id="a5afb-232">20026</span></span></p></td>
<td><p><span data-ttu-id="a5afb-233">Message d’information</span><span class="sxs-lookup"><span data-stu-id="a5afb-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="a5afb-234">Récupération de l’échec de l’accès à Active Directory pour la photo</span><span class="sxs-lookup"><span data-stu-id="a5afb-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a5afb-235">N/A</span><span class="sxs-lookup"><span data-stu-id="a5afb-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5afb-236">20027</span><span class="sxs-lookup"><span data-stu-id="a5afb-236">20027</span></span></p></td>
<td><p><span data-ttu-id="a5afb-237">Avertissement</span><span class="sxs-lookup"><span data-stu-id="a5afb-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="a5afb-238">Impossible de désérialiser</span><span class="sxs-lookup"><span data-stu-id="a5afb-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="a5afb-239">Impossible de désérialiser</span><span class="sxs-lookup"><span data-stu-id="a5afb-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="a5afb-240">Si le problème persiste, contactez le support technique</span><span class="sxs-lookup"><span data-stu-id="a5afb-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

