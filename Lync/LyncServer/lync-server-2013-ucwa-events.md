---
title: 'Lync Server 2013: événements UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="d7655-102">Événements adUCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7655-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7655-103">_**Dernière modification de la rubrique:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="d7655-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="d7655-104">Lync Server 2013 utilise l’API UCWA (Unified Communications Web API) à diverses fins, en accédant à Microsoft Exchange pour les recherches de contacts pour la mise à jour de la présence pour les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="d7655-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="d7655-p101">L’API UCWA écrit les enregistrements liés aux opérations en tant qu’événements de type information, avertissement ou erreur. Le tableau suivant décrit les événements pouvant être écrits par les composants de l’API UCWA.</span><span class="sxs-lookup"><span data-stu-id="d7655-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7655-107">ID d’événement</span><span class="sxs-lookup"><span data-stu-id="d7655-107">Event ID</span></span></th>
<th><span data-ttu-id="d7655-108">Type d’événement</span><span class="sxs-lookup"><span data-stu-id="d7655-108">Event Type</span></span></th>
<th><span data-ttu-id="d7655-109">Résumé</span><span class="sxs-lookup"><span data-stu-id="d7655-109">Summary</span></span></th>
<th><span data-ttu-id="d7655-110">Cause et résolution</span><span class="sxs-lookup"><span data-stu-id="d7655-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7655-111">20001</span><span class="sxs-lookup"><span data-stu-id="d7655-111">20001</span></span></p></td>
<td><p><span data-ttu-id="d7655-112">Information</span><span class="sxs-lookup"><span data-stu-id="d7655-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="d7655-113">API UCWA initialisée</span><span class="sxs-lookup"><span data-stu-id="d7655-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="d7655-114">N/A </span><span class="sxs-lookup"><span data-stu-id="d7655-114">N/A</span></span></p>
<p><span data-ttu-id="d7655-115">N/A </span><span class="sxs-lookup"><span data-stu-id="d7655-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-116">20002</span><span class="sxs-lookup"><span data-stu-id="d7655-116">20002</span></span></p></td>
<td><p><span data-ttu-id="d7655-117">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-117">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-118">L’API UCWA a rencontré une exception inattendue pendant son initialisation.</span><span class="sxs-lookup"><span data-stu-id="d7655-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="d7655-119">Une erreur inattendue s’est produite pendant l’initialisation.</span><span class="sxs-lookup"><span data-stu-id="d7655-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="d7655-120">Examinez les détails de l’exception dans l’entrée correspondante du journal des événements pour déterminer la cause possible.</span><span class="sxs-lookup"><span data-stu-id="d7655-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-121">20003</span><span class="sxs-lookup"><span data-stu-id="d7655-121">20003</span></span></p></td>
<td><p><span data-ttu-id="d7655-122">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-122">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-123">L’API UCWA a rencontré une exception non traitée.</span><span class="sxs-lookup"><span data-stu-id="d7655-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="d7655-124">Une exception non traitée s’est produite.</span><span class="sxs-lookup"><span data-stu-id="d7655-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="d7655-p102">Redémarrez le serveur. Si le problème persiste, contactez le support technique.</span><span class="sxs-lookup"><span data-stu-id="d7655-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-127">20004</span><span class="sxs-lookup"><span data-stu-id="d7655-127">20004</span></span></p></td>
<td><p><span data-ttu-id="d7655-128">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-128">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-129">Impossible d’accéder à Exchange pour la photo HD</span><span class="sxs-lookup"><span data-stu-id="d7655-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d7655-130">La connexion à Exchange n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d7655-131">Vérifiez que la connexion à Exchange est disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-132">20005</span><span class="sxs-lookup"><span data-stu-id="d7655-132">20005</span></span></p></td>
<td><p><span data-ttu-id="d7655-133">Information</span><span class="sxs-lookup"><span data-stu-id="d7655-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="d7655-134">Récupération de l’échec de l’accès à Exchange pour la photo HD</span><span class="sxs-lookup"><span data-stu-id="d7655-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d7655-135">S/O</span><span class="sxs-lookup"><span data-stu-id="d7655-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-136">20006</span><span class="sxs-lookup"><span data-stu-id="d7655-136">20006</span></span></p></td>
<td><p><span data-ttu-id="d7655-137">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-137">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-138">Impossible d’accéder à Exchange pour la recherche de contact</span><span class="sxs-lookup"><span data-stu-id="d7655-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="d7655-139">La connexion à Exchange n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d7655-140">Vérifiez que la connexion à Exchange est disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-141">20007</span><span class="sxs-lookup"><span data-stu-id="d7655-141">20007</span></span></p></td>
<td><p><span data-ttu-id="d7655-142">Information</span><span class="sxs-lookup"><span data-stu-id="d7655-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="d7655-143">Récupération de l’échec de la recherche de contact dans Exchange</span><span class="sxs-lookup"><span data-stu-id="d7655-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="d7655-144">S/O</span><span class="sxs-lookup"><span data-stu-id="d7655-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-145">20008</span><span class="sxs-lookup"><span data-stu-id="d7655-145">20008</span></span></p></td>
<td><p><span data-ttu-id="d7655-146">Avertissement</span><span class="sxs-lookup"><span data-stu-id="d7655-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="d7655-147">Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par application</span><span class="sxs-lookup"><span data-stu-id="d7655-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="d7655-148">Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par application</span><span class="sxs-lookup"><span data-stu-id="d7655-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="d7655-149">Vérifiez si les clients possèdent des abonnements superflus.</span><span class="sxs-lookup"><span data-stu-id="d7655-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-150">20009</span><span class="sxs-lookup"><span data-stu-id="d7655-150">20009</span></span></p></td>
<td><p><span data-ttu-id="d7655-151">Avertissement</span><span class="sxs-lookup"><span data-stu-id="d7655-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="d7655-152">Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="d7655-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="d7655-153">Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par lot</span><span class="sxs-lookup"><span data-stu-id="d7655-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="d7655-154">Vérifiez si les clients possèdent des abonnements superflus.</span><span class="sxs-lookup"><span data-stu-id="d7655-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-155">20010</span><span class="sxs-lookup"><span data-stu-id="d7655-155">20010</span></span></p></td>
<td><p><span data-ttu-id="d7655-156">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-156">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-157">Impossible de récupérer les données de la bande entrante</span><span class="sxs-lookup"><span data-stu-id="d7655-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="d7655-158">Impossible de récupérer les données de la bande entrante</span><span class="sxs-lookup"><span data-stu-id="d7655-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="d7655-159">Si le problème persiste, contactez le support technique.</span><span class="sxs-lookup"><span data-stu-id="d7655-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-160">20011</span><span class="sxs-lookup"><span data-stu-id="d7655-160">20011</span></span></p></td>
<td><p><span data-ttu-id="d7655-161">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-161">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-162">Impossible de s’abonner aux informations de présence</span><span class="sxs-lookup"><span data-stu-id="d7655-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="d7655-163">Impossible de s’abonner aux informations de présence</span><span class="sxs-lookup"><span data-stu-id="d7655-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="d7655-164">Si le problème persiste, contactez le support technique.</span><span class="sxs-lookup"><span data-stu-id="d7655-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-165">20012</span><span class="sxs-lookup"><span data-stu-id="d7655-165">20012</span></span></p></td>
<td><p><span data-ttu-id="d7655-166">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-166">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-167">Échec de l’enregistrement du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="d7655-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="d7655-168">Échec de l’enregistrement du point de terminaison</span><span class="sxs-lookup"><span data-stu-id="d7655-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="d7655-169">Si le problème persiste, contactez le support technique.</span><span class="sxs-lookup"><span data-stu-id="d7655-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-170">20013</span><span class="sxs-lookup"><span data-stu-id="d7655-170">20013</span></span></p></td>
<td><p><span data-ttu-id="d7655-171">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-171">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-172">Le MCU de messagerie instantanée n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d7655-173">Le MCU de messagerie instantanée n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="d7655-174">Vérifiez si le MCU de messagerie instantanée est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d7655-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-175">20014</span><span class="sxs-lookup"><span data-stu-id="d7655-175">20014</span></span></p></td>
<td><p><span data-ttu-id="d7655-176">Information</span><span class="sxs-lookup"><span data-stu-id="d7655-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="d7655-177">Récupération de l’échec de la connexion au MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="d7655-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d7655-178">S/O</span><span class="sxs-lookup"><span data-stu-id="d7655-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-179">20015</span><span class="sxs-lookup"><span data-stu-id="d7655-179">20015</span></span></p></td>
<td><p><span data-ttu-id="d7655-180">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-180">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-181">Le MCU AV n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d7655-182">Le MCU AV n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="d7655-183">Vérifiez si le MCU AV est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d7655-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-184">20016</span><span class="sxs-lookup"><span data-stu-id="d7655-184">20016</span></span></p></td>
<td><p><span data-ttu-id="d7655-185">Information</span><span class="sxs-lookup"><span data-stu-id="d7655-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="d7655-186">Récupération de l’échec de la connexion au MCU AV</span><span class="sxs-lookup"><span data-stu-id="d7655-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d7655-187">S/O</span><span class="sxs-lookup"><span data-stu-id="d7655-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-188">20017</span><span class="sxs-lookup"><span data-stu-id="d7655-188">20017</span></span></p></td>
<td><p><span data-ttu-id="d7655-189">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-189">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-190">Le MCU AS n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d7655-191">Le MCU AS n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="d7655-192">Vérifiez si le MCU AS est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d7655-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-193">20018</span><span class="sxs-lookup"><span data-stu-id="d7655-193">20018</span></span></p></td>
<td><p><span data-ttu-id="d7655-194">Information</span><span class="sxs-lookup"><span data-stu-id="d7655-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="d7655-195">Récupération de l’échec de la connexion au MCU AS</span><span class="sxs-lookup"><span data-stu-id="d7655-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d7655-196">N/A</span><span class="sxs-lookup"><span data-stu-id="d7655-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-197">20019</span><span class="sxs-lookup"><span data-stu-id="d7655-197">20019</span></span></p></td>
<td><p><span data-ttu-id="d7655-198">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-198">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-199">Le MCU de données n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d7655-200">Le MCU de données n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="d7655-201">Vérifiez si le MCU de données est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d7655-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-202">20020</span><span class="sxs-lookup"><span data-stu-id="d7655-202">20020</span></span></p></td>
<td><p><span data-ttu-id="d7655-203">Information</span><span class="sxs-lookup"><span data-stu-id="d7655-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="d7655-204">Récupération de l’échec de la connexion au MCU de données</span><span class="sxs-lookup"><span data-stu-id="d7655-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d7655-205">S/O</span><span class="sxs-lookup"><span data-stu-id="d7655-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-206">20021</span><span class="sxs-lookup"><span data-stu-id="d7655-206">20021</span></span></p></td>
<td><p><span data-ttu-id="d7655-207">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-207">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-208">Impossible de rejoindre le MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="d7655-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d7655-209">Impossible de rejoindre le MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="d7655-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="d7655-210">Vérifiez si le MCU de messagerie instantanée est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d7655-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-211">20022</span><span class="sxs-lookup"><span data-stu-id="d7655-211">20022</span></span></p></td>
<td><p><span data-ttu-id="d7655-212">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-212">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-213">Impossible de rejoindre le MCU AV</span><span class="sxs-lookup"><span data-stu-id="d7655-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d7655-214">Impossible de rejoindre le MCU AV</span><span class="sxs-lookup"><span data-stu-id="d7655-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="d7655-215">Vérifiez si le MCU AV est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d7655-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-216">20023</span><span class="sxs-lookup"><span data-stu-id="d7655-216">20023</span></span></p></td>
<td><p><span data-ttu-id="d7655-217">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-217">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-218">Impossible de rejoindre le MCU AS</span><span class="sxs-lookup"><span data-stu-id="d7655-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d7655-219">Impossible de rejoindre le MCU AS</span><span class="sxs-lookup"><span data-stu-id="d7655-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="d7655-220">Vérifiez si le MCU AS est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d7655-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-221">20024</span><span class="sxs-lookup"><span data-stu-id="d7655-221">20024</span></span></p></td>
<td><p><span data-ttu-id="d7655-222">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-222">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-223">Impossible de rejoindre le MCU de données</span><span class="sxs-lookup"><span data-stu-id="d7655-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d7655-224">Impossible de rejoindre le MCU de données</span><span class="sxs-lookup"><span data-stu-id="d7655-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="d7655-225">Vérifiez si le MCU de données est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d7655-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-226">20025</span><span class="sxs-lookup"><span data-stu-id="d7655-226">20025</span></span></p></td>
<td><p><span data-ttu-id="d7655-227">Erreur</span><span class="sxs-lookup"><span data-stu-id="d7655-227">Error</span></span></p></td>
<td><p><span data-ttu-id="d7655-228">Impossible d’accéder à Active Directory pour la photo</span><span class="sxs-lookup"><span data-stu-id="d7655-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d7655-229">La connexion à Active Directory n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="d7655-230">Vérifiez que la connexion à Active Directory est disponible.</span><span class="sxs-lookup"><span data-stu-id="d7655-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7655-231">20026</span><span class="sxs-lookup"><span data-stu-id="d7655-231">20026</span></span></p></td>
<td><p><span data-ttu-id="d7655-232">Information</span><span class="sxs-lookup"><span data-stu-id="d7655-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="d7655-233">Récupération de l’échec de l’accès à Active Directory pour la photo</span><span class="sxs-lookup"><span data-stu-id="d7655-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d7655-234">N/A</span><span class="sxs-lookup"><span data-stu-id="d7655-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7655-235">20027</span><span class="sxs-lookup"><span data-stu-id="d7655-235">20027</span></span></p></td>
<td><p><span data-ttu-id="d7655-236">Avertissement</span><span class="sxs-lookup"><span data-stu-id="d7655-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="d7655-237">Impossible d’effectuer la désérialisation</span><span class="sxs-lookup"><span data-stu-id="d7655-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="d7655-238">Impossible d’effectuer la désérialisation</span><span class="sxs-lookup"><span data-stu-id="d7655-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="d7655-239">Si le problème persiste, contactez le support technique.</span><span class="sxs-lookup"><span data-stu-id="d7655-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

