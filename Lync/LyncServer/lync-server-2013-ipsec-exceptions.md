---
title: Exceptions IPsec Lync Server 2013
description: Exceptions IPsec Lync Server 2013.
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
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575000"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="7370d-103">Exceptions IPsec dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7370d-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7370d-104">_**Dernière modification de la rubrique :** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="7370d-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="7370d-p101">Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.</span><span class="sxs-lookup"><span data-stu-id="7370d-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="7370d-107">Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.</span><span class="sxs-lookup"><span data-stu-id="7370d-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="7370d-108">Exceptions recommandées pour IPsec</span><span class="sxs-lookup"><span data-stu-id="7370d-108">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="7370d-109">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="7370d-109">Rule name</span></span></th>
<th><span data-ttu-id="7370d-110">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="7370d-110">Source IP</span></span></th>
<th><span data-ttu-id="7370d-111">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="7370d-111">Destination IP</span></span></th>
<th><span data-ttu-id="7370d-112">Protocole</span><span class="sxs-lookup"><span data-stu-id="7370d-112">Protocol</span></span></th>
<th><span data-ttu-id="7370d-113">Port source</span><span class="sxs-lookup"><span data-stu-id="7370d-113">Source port</span></span></th>
<th><span data-ttu-id="7370d-114">Port de destination</span><span class="sxs-lookup"><span data-stu-id="7370d-114">Destination port</span></span></th>
<th><span data-ttu-id="7370d-115">Besoin d’authentification</span><span class="sxs-lookup"><span data-stu-id="7370d-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7370d-116">Serveur Edge A/V, ports internes/entrants</span><span class="sxs-lookup"><span data-stu-id="7370d-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-117">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-117">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-118">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="7370d-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="7370d-119">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-120">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-120">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-121">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-121">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-122">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7370d-123">Serveur Edge A/V, ports externes/entrants</span><span class="sxs-lookup"><span data-stu-id="7370d-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-124">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-124">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-125">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="7370d-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="7370d-126">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-127">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-127">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-128">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-128">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-129">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7370d-130">Serveur Edge A/V, ports internes/sortants</span><span class="sxs-lookup"><span data-stu-id="7370d-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-131">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="7370d-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="7370d-132">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-132">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-133">&amp;TCP UDP</span><span class="sxs-lookup"><span data-stu-id="7370d-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-134">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-134">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-135">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-135">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-136">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7370d-137">Serveur Edge A/V, ports externes/sortants</span><span class="sxs-lookup"><span data-stu-id="7370d-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-138">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="7370d-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="7370d-139">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-139">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-140">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-141">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-141">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-142">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-142">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-143">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7370d-144">Serveur de médiation, ports entrants</span><span class="sxs-lookup"><span data-stu-id="7370d-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-145">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-145">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-146">Élaboration</span><span class="sxs-lookup"><span data-stu-id="7370d-146">Mediation</span></span></p>
<p><span data-ttu-id="7370d-147">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="7370d-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="7370d-148">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-149">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-149">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-150">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-150">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-151">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7370d-152">Serveur de médiation, ports sortants</span><span class="sxs-lookup"><span data-stu-id="7370d-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-153">Élaboration</span><span class="sxs-lookup"><span data-stu-id="7370d-153">Mediation</span></span></p>
<p><span data-ttu-id="7370d-154">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="7370d-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="7370d-155">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-155">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-156">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-157">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-157">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-158">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-158">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-159">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7370d-160">Intendant Conférence entrant</span><span class="sxs-lookup"><span data-stu-id="7370d-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-161">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-161">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-162">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="7370d-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="7370d-163">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-164">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-164">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-165">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-165">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-166">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7370d-167">Intendant Conférence sortant</span><span class="sxs-lookup"><span data-stu-id="7370d-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-168">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="7370d-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="7370d-169">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-169">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-170">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-171">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-171">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-172">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-172">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-173">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7370d-174">Serveur de conférence A/V, ports entrants</span><span class="sxs-lookup"><span data-stu-id="7370d-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-175">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-175">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-176">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="7370d-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="7370d-177">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-178">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-178">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-179">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-179">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-180">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7370d-181">Conférence A/V, ports sortants</span><span class="sxs-lookup"><span data-stu-id="7370d-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-182">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="7370d-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="7370d-183">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-183">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-184">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-185">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-185">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-186">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-186">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-187">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7370d-188">Exchange, ports entrants</span><span class="sxs-lookup"><span data-stu-id="7370d-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-189">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-189">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-190">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="7370d-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="7370d-191">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-192">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-192">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-193">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-193">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-194">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7370d-195">Serveurs de partage d’application, ports entrants</span><span class="sxs-lookup"><span data-stu-id="7370d-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-196">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-196">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-197">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="7370d-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="7370d-198">TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-199">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-199">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-200">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-200">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-201">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7370d-202">Serveur de partage d’application, ports sortants</span><span class="sxs-lookup"><span data-stu-id="7370d-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-203">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="7370d-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="7370d-204">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-204">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-205">TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-206">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-206">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-207">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-207">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-208">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7370d-209">Exchange, ports sortants</span><span class="sxs-lookup"><span data-stu-id="7370d-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="7370d-210">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="7370d-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="7370d-211">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-211">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-212">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="7370d-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7370d-213">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-213">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-214">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-214">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-215">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7370d-216">Clients</span><span class="sxs-lookup"><span data-stu-id="7370d-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="7370d-217">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-217">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-218">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-218">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-219">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="7370d-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="7370d-220">Plage de ports multimédias définie</span><span class="sxs-lookup"><span data-stu-id="7370d-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="7370d-221">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7370d-221">Any</span></span></p></td>
<td><p><span data-ttu-id="7370d-222">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="7370d-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

