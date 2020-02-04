---
title: Exceptions IPsec de Lync Server 2013
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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="03dc4-102">Exceptions IPsec dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03dc4-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03dc4-103">_**Dernière modification de la rubrique :** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="03dc4-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="03dc4-104">Pour les réseaux d’entreprise pour lesquels la sécurité du protocole Internet (IPsec) (voir IETF RFC 4301-4309) a été déployée, le protocole IPsec doit être désactivé sur la plage de ports utilisée pour la remise de la vidéo audio, vidéo et de panorama.</span><span class="sxs-lookup"><span data-stu-id="03dc4-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="03dc4-105">Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.</span><span class="sxs-lookup"><span data-stu-id="03dc4-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="03dc4-106">Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.</span><span class="sxs-lookup"><span data-stu-id="03dc4-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="03dc4-107">Exceptions recommandées pour IPsec</span><span class="sxs-lookup"><span data-stu-id="03dc4-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="03dc4-108">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="03dc4-108">Rule name</span></span></th>
<th><span data-ttu-id="03dc4-109">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="03dc4-109">Source IP</span></span></th>
<th><span data-ttu-id="03dc4-110">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="03dc4-110">Destination IP</span></span></th>
<th><span data-ttu-id="03dc4-111">Protocole</span><span class="sxs-lookup"><span data-stu-id="03dc4-111">Protocol</span></span></th>
<th><span data-ttu-id="03dc4-112">Port source</span><span class="sxs-lookup"><span data-stu-id="03dc4-112">Source port</span></span></th>
<th><span data-ttu-id="03dc4-113">Port de destination</span><span class="sxs-lookup"><span data-stu-id="03dc4-113">Destination port</span></span></th>
<th><span data-ttu-id="03dc4-114">Besoin d’authentification</span><span class="sxs-lookup"><span data-stu-id="03dc4-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03dc4-115">Serveur Edge A/V, ports internes/entrants</span><span class="sxs-lookup"><span data-stu-id="03dc4-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-116">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-116">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-117">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="03dc4-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="03dc4-118">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-119">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-119">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-120">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-120">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-121">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03dc4-122">Serveur Edge A/V, ports externes/entrants</span><span class="sxs-lookup"><span data-stu-id="03dc4-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-123">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-123">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-124">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="03dc4-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="03dc4-125">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-126">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-126">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-127">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-127">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-128">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03dc4-129">Serveur Edge A/V, ports internes/sortants</span><span class="sxs-lookup"><span data-stu-id="03dc4-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-130">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="03dc4-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="03dc4-131">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-131">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="03dc4-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-133">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-133">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-134">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-134">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-135">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03dc4-136">Serveur Edge A/V, ports externes/sortants</span><span class="sxs-lookup"><span data-stu-id="03dc4-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-137">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="03dc4-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="03dc4-138">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-138">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-139">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-140">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-140">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-141">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-141">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-142">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03dc4-143">Serveur de médiation, ports entrants</span><span class="sxs-lookup"><span data-stu-id="03dc4-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-144">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-144">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-145">Serveur(s)</span><span class="sxs-lookup"><span data-stu-id="03dc4-145">Mediation</span></span></p>
<p><span data-ttu-id="03dc4-146">de médiation</span><span class="sxs-lookup"><span data-stu-id="03dc4-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="03dc4-147">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-148">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-148">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-149">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-149">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-150">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03dc4-151">Serveur de médiation, ports sortants</span><span class="sxs-lookup"><span data-stu-id="03dc4-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-152">Serveur(s)</span><span class="sxs-lookup"><span data-stu-id="03dc4-152">Mediation</span></span></p>
<p><span data-ttu-id="03dc4-153">de médiation</span><span class="sxs-lookup"><span data-stu-id="03dc4-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="03dc4-154">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-154">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-155">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-156">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-156">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-157">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-157">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-158">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03dc4-159">Intendant Conférence entrant</span><span class="sxs-lookup"><span data-stu-id="03dc4-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-160">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-160">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-161">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="03dc4-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="03dc4-162">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-163">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-163">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-164">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-164">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-165">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03dc4-166">Intendant Conférence sortant</span><span class="sxs-lookup"><span data-stu-id="03dc4-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-167">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="03dc4-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="03dc4-168">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-168">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-169">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-170">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-170">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-171">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-171">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-172">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03dc4-173">Serveur de conférence A/V, ports entrants</span><span class="sxs-lookup"><span data-stu-id="03dc4-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-174">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-174">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-175">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="03dc4-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="03dc4-176">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-177">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-177">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-178">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-178">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-179">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03dc4-180">Conférence A/V, ports sortants</span><span class="sxs-lookup"><span data-stu-id="03dc4-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-181">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="03dc4-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="03dc4-182">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-182">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-183">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-184">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-184">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-185">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-185">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-186">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03dc4-187">Exchange, ports entrants</span><span class="sxs-lookup"><span data-stu-id="03dc4-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-188">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-188">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-189">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="03dc4-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="03dc4-190">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-191">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-191">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-192">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-192">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-193">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03dc4-194">Serveurs de partage d’application, ports entrants</span><span class="sxs-lookup"><span data-stu-id="03dc4-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-195">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-195">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-196">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="03dc4-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="03dc4-197">TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-198">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-198">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-199">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-199">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-200">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03dc4-201">Serveur de partage d’application, ports sortants</span><span class="sxs-lookup"><span data-stu-id="03dc4-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-202">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="03dc4-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="03dc4-203">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-203">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-204">TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-205">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-205">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-206">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-206">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-207">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03dc4-208">Exchange, ports sortants</span><span class="sxs-lookup"><span data-stu-id="03dc4-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="03dc4-209">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="03dc4-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="03dc4-210">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-210">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-211">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="03dc4-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-212">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-212">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-213">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-213">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-214">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03dc4-215">Clients</span><span class="sxs-lookup"><span data-stu-id="03dc4-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="03dc4-216">Indifférente </span><span class="sxs-lookup"><span data-stu-id="03dc4-216">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-217">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-217">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-218">UDP</span><span class="sxs-lookup"><span data-stu-id="03dc4-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="03dc4-219">Plage de ports multimédias définie</span><span class="sxs-lookup"><span data-stu-id="03dc4-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="03dc4-220">Indifférente</span><span class="sxs-lookup"><span data-stu-id="03dc4-220">Any</span></span></p></td>
<td><p><span data-ttu-id="03dc4-221">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="03dc4-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

