---
title: Exceptions IPsec Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="45615-102">Exceptions IPsec dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45615-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45615-103">_**Dernière modification de la rubrique :** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="45615-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="45615-p101">Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.</span><span class="sxs-lookup"><span data-stu-id="45615-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="45615-106">Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.</span><span class="sxs-lookup"><span data-stu-id="45615-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="45615-107">Exceptions recommandées pour IPsec</span><span class="sxs-lookup"><span data-stu-id="45615-107">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45615-108">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="45615-108">Rule name</span></span></th>
<th><span data-ttu-id="45615-109">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="45615-109">Source IP</span></span></th>
<th><span data-ttu-id="45615-110">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="45615-110">Destination IP</span></span></th>
<th><span data-ttu-id="45615-111">Protocole</span><span class="sxs-lookup"><span data-stu-id="45615-111">Protocol</span></span></th>
<th><span data-ttu-id="45615-112">Port source</span><span class="sxs-lookup"><span data-stu-id="45615-112">Source port</span></span></th>
<th><span data-ttu-id="45615-113">Port de destination</span><span class="sxs-lookup"><span data-stu-id="45615-113">Destination port</span></span></th>
<th><span data-ttu-id="45615-114">Besoin d’authentification</span><span class="sxs-lookup"><span data-stu-id="45615-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45615-115">Serveur Edge A/V, ports internes/entrants</span><span class="sxs-lookup"><span data-stu-id="45615-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="45615-116">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-116">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-117">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="45615-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="45615-118">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-119">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-119">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-120">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-120">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-121">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45615-122">Serveur Edge A/V, ports externes/entrants</span><span class="sxs-lookup"><span data-stu-id="45615-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="45615-123">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-123">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-124">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="45615-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="45615-125">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-126">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-126">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-127">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-127">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-128">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45615-129">Serveur Edge A/V, ports internes/sortants</span><span class="sxs-lookup"><span data-stu-id="45615-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="45615-130">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="45615-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="45615-131">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-131">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="45615-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-133">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-133">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-134">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-134">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-135">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45615-136">Serveur Edge A/V, ports externes/sortants</span><span class="sxs-lookup"><span data-stu-id="45615-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="45615-137">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="45615-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="45615-138">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-138">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-139">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-140">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-140">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-141">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-141">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-142">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45615-143">Serveur de médiation, ports entrants</span><span class="sxs-lookup"><span data-stu-id="45615-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="45615-144">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-144">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-145">Élaboration</span><span class="sxs-lookup"><span data-stu-id="45615-145">Mediation</span></span></p>
<p><span data-ttu-id="45615-146">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="45615-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="45615-147">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-148">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-148">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-149">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-149">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-150">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45615-151">Serveur de médiation, ports sortants</span><span class="sxs-lookup"><span data-stu-id="45615-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="45615-152">Élaboration</span><span class="sxs-lookup"><span data-stu-id="45615-152">Mediation</span></span></p>
<p><span data-ttu-id="45615-153">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="45615-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="45615-154">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-154">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-155">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-156">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-156">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-157">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-157">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-158">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45615-159">Intendant Conférence entrant</span><span class="sxs-lookup"><span data-stu-id="45615-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="45615-160">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-160">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-161">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="45615-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="45615-162">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-163">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-163">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-164">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-164">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-165">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45615-166">Intendant Conférence sortant</span><span class="sxs-lookup"><span data-stu-id="45615-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="45615-167">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="45615-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="45615-168">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-168">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-169">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-170">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-170">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-171">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-171">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-172">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45615-173">Serveur de conférence A/V, ports entrants</span><span class="sxs-lookup"><span data-stu-id="45615-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="45615-174">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-174">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-175">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="45615-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="45615-176">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-177">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-177">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-178">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-178">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-179">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45615-180">Conférence A/V, ports sortants</span><span class="sxs-lookup"><span data-stu-id="45615-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="45615-181">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="45615-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="45615-182">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-182">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-183">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-184">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-184">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-185">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-185">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-186">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45615-187">Exchange, ports entrants</span><span class="sxs-lookup"><span data-stu-id="45615-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="45615-188">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-188">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-189">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="45615-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="45615-190">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-191">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-191">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-192">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-192">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-193">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45615-194">Serveurs de partage d’application, ports entrants</span><span class="sxs-lookup"><span data-stu-id="45615-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="45615-195">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-195">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-196">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="45615-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="45615-197">TCP</span><span class="sxs-lookup"><span data-stu-id="45615-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-198">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-198">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-199">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-199">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-200">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45615-201">Serveur de partage d’application, ports sortants</span><span class="sxs-lookup"><span data-stu-id="45615-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="45615-202">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="45615-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="45615-203">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-203">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-204">TCP</span><span class="sxs-lookup"><span data-stu-id="45615-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-205">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-205">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-206">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-206">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-207">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45615-208">Exchange, ports sortants</span><span class="sxs-lookup"><span data-stu-id="45615-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="45615-209">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="45615-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="45615-210">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-210">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-211">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="45615-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="45615-212">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-212">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-213">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-213">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-214">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45615-215">Clients</span><span class="sxs-lookup"><span data-stu-id="45615-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="45615-216">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-216">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-217">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-217">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-218">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="45615-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="45615-219">Plage de ports multimédias définie</span><span class="sxs-lookup"><span data-stu-id="45615-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="45615-220">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="45615-220">Any</span></span></p></td>
<td><p><span data-ttu-id="45615-221">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="45615-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

