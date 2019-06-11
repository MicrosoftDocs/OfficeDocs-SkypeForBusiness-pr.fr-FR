---
title: Exceptions IPsec de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="173bf-102">Exceptions IPsec dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="173bf-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="173bf-103">_**Dernière modification de la rubrique:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="173bf-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="173bf-104">Pour les réseaux d’entreprise pour lesquels la sécurité du protocole Internet (IPsec) (voir IETF RFC 4301-4309) a été déployée, le protocole IPsec doit être désactivé sur la plage de ports utilisée pour la remise de la vidéo audio, vidéo et de panorama.</span><span class="sxs-lookup"><span data-stu-id="173bf-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="173bf-105">Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.</span><span class="sxs-lookup"><span data-stu-id="173bf-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="173bf-106">Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.</span><span class="sxs-lookup"><span data-stu-id="173bf-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="173bf-107">Exceptions recommandées pour IPsec</span><span class="sxs-lookup"><span data-stu-id="173bf-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="173bf-108">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="173bf-108">Rule name</span></span></th>
<th><span data-ttu-id="173bf-109">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="173bf-109">Source IP</span></span></th>
<th><span data-ttu-id="173bf-110">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="173bf-110">Destination IP</span></span></th>
<th><span data-ttu-id="173bf-111">Protocole</span><span class="sxs-lookup"><span data-stu-id="173bf-111">Protocol</span></span></th>
<th><span data-ttu-id="173bf-112">Port source</span><span class="sxs-lookup"><span data-stu-id="173bf-112">Source port</span></span></th>
<th><span data-ttu-id="173bf-113">Port de destination</span><span class="sxs-lookup"><span data-stu-id="173bf-113">Destination port</span></span></th>
<th><span data-ttu-id="173bf-114">Besoin d’authentification</span><span class="sxs-lookup"><span data-stu-id="173bf-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="173bf-115">Serveur Edge A/V, ports internes/entrants</span><span class="sxs-lookup"><span data-stu-id="173bf-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-116">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-116">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-117">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="173bf-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="173bf-118">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-119">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-119">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-120">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-120">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-121">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173bf-122">Serveur Edge A/V, ports externes/entrants</span><span class="sxs-lookup"><span data-stu-id="173bf-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-123">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-123">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-124">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="173bf-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="173bf-125">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-126">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-126">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-127">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-127">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-128">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173bf-129">Serveur Edge A/V, ports internes/sortants</span><span class="sxs-lookup"><span data-stu-id="173bf-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-130">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="173bf-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="173bf-131">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-131">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="173bf-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-133">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-133">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-134">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-134">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-135">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173bf-136">Serveur Edge A/V, ports externes/sortants</span><span class="sxs-lookup"><span data-stu-id="173bf-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-137">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="173bf-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="173bf-138">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-138">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-139">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-140">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-140">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-141">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-141">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-142">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173bf-143">Serveur de médiation, ports entrants</span><span class="sxs-lookup"><span data-stu-id="173bf-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-144">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-144">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-145">Serveur(s)</span><span class="sxs-lookup"><span data-stu-id="173bf-145">Mediation</span></span></p>
<p><span data-ttu-id="173bf-146">de médiation</span><span class="sxs-lookup"><span data-stu-id="173bf-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="173bf-147">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-148">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-148">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-149">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-149">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-150">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173bf-151">Serveur de médiation, ports sortants</span><span class="sxs-lookup"><span data-stu-id="173bf-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-152">Serveur(s)</span><span class="sxs-lookup"><span data-stu-id="173bf-152">Mediation</span></span></p>
<p><span data-ttu-id="173bf-153">de médiation</span><span class="sxs-lookup"><span data-stu-id="173bf-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="173bf-154">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-154">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-155">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-156">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-156">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-157">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-157">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-158">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173bf-159">Intendant Conférence entrant</span><span class="sxs-lookup"><span data-stu-id="173bf-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-160">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-160">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-161">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="173bf-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="173bf-162">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-163">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-163">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-164">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-164">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-165">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173bf-166">Intendant Conférence sortant</span><span class="sxs-lookup"><span data-stu-id="173bf-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-167">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="173bf-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="173bf-168">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-168">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-169">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-170">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-170">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-171">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-171">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-172">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173bf-173">Serveur de conférence A/V, ports entrants</span><span class="sxs-lookup"><span data-stu-id="173bf-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-174">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-174">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-175">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="173bf-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="173bf-176">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-177">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-177">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-178">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-178">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-179">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173bf-180">Conférence A/V, ports sortants</span><span class="sxs-lookup"><span data-stu-id="173bf-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-181">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="173bf-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="173bf-182">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-182">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-183">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-184">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-184">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-185">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-185">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-186">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173bf-187">Exchange, ports entrants</span><span class="sxs-lookup"><span data-stu-id="173bf-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-188">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-188">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-189">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="173bf-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="173bf-190">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-191">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-191">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-192">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-192">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-193">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173bf-194">Serveurs de partage d’application, ports entrants</span><span class="sxs-lookup"><span data-stu-id="173bf-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-195">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-195">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-196">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="173bf-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="173bf-197">TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-198">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-198">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-199">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-199">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-200">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173bf-201">Serveur de partage d’application, ports sortants</span><span class="sxs-lookup"><span data-stu-id="173bf-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-202">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="173bf-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="173bf-203">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-203">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-204">TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-205">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-205">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-206">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-206">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-207">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173bf-208">Exchange, ports sortants</span><span class="sxs-lookup"><span data-stu-id="173bf-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="173bf-209">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="173bf-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="173bf-210">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-210">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-211">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="173bf-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="173bf-212">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-212">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-213">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-213">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-214">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173bf-215">Clients</span><span class="sxs-lookup"><span data-stu-id="173bf-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="173bf-216">Indifférente </span><span class="sxs-lookup"><span data-stu-id="173bf-216">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-217">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-217">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-218">UDP</span><span class="sxs-lookup"><span data-stu-id="173bf-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="173bf-219">Plage de ports multimédias définie</span><span class="sxs-lookup"><span data-stu-id="173bf-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="173bf-220">Indifférente</span><span class="sxs-lookup"><span data-stu-id="173bf-220">Any</span></span></p></td>
<td><p><span data-ttu-id="173bf-221">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="173bf-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

