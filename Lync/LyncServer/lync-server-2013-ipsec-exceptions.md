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
ms.openlocfilehash: db7291674485dec30211d88e2739b0da89fb334f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="ee93a-102">Exceptions IPsec dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee93a-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee93a-103">_**Dernière modification de la rubrique :** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="ee93a-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="ee93a-p101">Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.</span><span class="sxs-lookup"><span data-stu-id="ee93a-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="ee93a-106">Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.</span><span class="sxs-lookup"><span data-stu-id="ee93a-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="ee93a-107">Exceptions recommandées pour IPsec</span><span class="sxs-lookup"><span data-stu-id="ee93a-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="ee93a-108">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="ee93a-108">Rule name</span></span></th>
<th><span data-ttu-id="ee93a-109">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="ee93a-109">Source IP</span></span></th>
<th><span data-ttu-id="ee93a-110">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="ee93a-110">Destination IP</span></span></th>
<th><span data-ttu-id="ee93a-111">Protocole</span><span class="sxs-lookup"><span data-stu-id="ee93a-111">Protocol</span></span></th>
<th><span data-ttu-id="ee93a-112">Port source</span><span class="sxs-lookup"><span data-stu-id="ee93a-112">Source port</span></span></th>
<th><span data-ttu-id="ee93a-113">Port de destination</span><span class="sxs-lookup"><span data-stu-id="ee93a-113">Destination port</span></span></th>
<th><span data-ttu-id="ee93a-114">Besoin d’authentification</span><span class="sxs-lookup"><span data-stu-id="ee93a-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee93a-115">Serveur Edge A/V, ports internes/entrants</span><span class="sxs-lookup"><span data-stu-id="ee93a-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-116">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-116">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-117">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="ee93a-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="ee93a-118">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-119">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-119">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-120">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-120">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-121">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee93a-122">Serveur Edge A/V, ports externes/entrants</span><span class="sxs-lookup"><span data-stu-id="ee93a-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-123">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-123">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-124">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="ee93a-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="ee93a-125">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-126">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-126">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-127">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-127">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-128">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee93a-129">Serveur Edge A/V, ports internes/sortants</span><span class="sxs-lookup"><span data-stu-id="ee93a-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-130">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="ee93a-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="ee93a-131">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-131">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="ee93a-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-133">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-133">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-134">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-135">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee93a-136">Serveur Edge A/V, ports externes/sortants</span><span class="sxs-lookup"><span data-stu-id="ee93a-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-137">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="ee93a-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="ee93a-138">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-138">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-139">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-140">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-140">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-141">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-141">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-142">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee93a-143">Serveur de médiation, ports entrants</span><span class="sxs-lookup"><span data-stu-id="ee93a-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-144">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-144">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-145">Élaboration</span><span class="sxs-lookup"><span data-stu-id="ee93a-145">Mediation</span></span></p>
<p><span data-ttu-id="ee93a-146">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="ee93a-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="ee93a-147">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-148">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-148">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-149">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-149">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-150">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee93a-151">Serveur de médiation, ports sortants</span><span class="sxs-lookup"><span data-stu-id="ee93a-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-152">Élaboration</span><span class="sxs-lookup"><span data-stu-id="ee93a-152">Mediation</span></span></p>
<p><span data-ttu-id="ee93a-153">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="ee93a-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="ee93a-154">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-154">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-155">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-156">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-156">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-157">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-157">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-158">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee93a-159">Intendant Conférence entrant</span><span class="sxs-lookup"><span data-stu-id="ee93a-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-160">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-160">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-161">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="ee93a-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="ee93a-162">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-163">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-163">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-164">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-164">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-165">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee93a-166">Intendant Conférence sortant</span><span class="sxs-lookup"><span data-stu-id="ee93a-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-167">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="ee93a-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="ee93a-168">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-168">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-169">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-170">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-170">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-171">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-171">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-172">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee93a-173">Serveur de conférence A/V, ports entrants</span><span class="sxs-lookup"><span data-stu-id="ee93a-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-174">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-174">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-175">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ee93a-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ee93a-176">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-177">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-177">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-178">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-178">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-179">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee93a-180">Conférence A/V, ports sortants</span><span class="sxs-lookup"><span data-stu-id="ee93a-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-181">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ee93a-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ee93a-182">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-182">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-183">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-184">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-184">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-185">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-185">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-186">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee93a-187">Exchange, ports entrants</span><span class="sxs-lookup"><span data-stu-id="ee93a-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-188">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-188">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-189">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="ee93a-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="ee93a-190">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-191">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-191">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-192">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-192">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-193">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee93a-194">Serveurs de partage d’application, ports entrants</span><span class="sxs-lookup"><span data-stu-id="ee93a-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-195">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-195">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-196">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="ee93a-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="ee93a-197">TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-198">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-198">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-199">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-199">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-200">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee93a-201">Serveur de partage d’application, ports sortants</span><span class="sxs-lookup"><span data-stu-id="ee93a-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-202">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="ee93a-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="ee93a-203">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-203">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-204">TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-205">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-205">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-206">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-206">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-207">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee93a-208">Exchange, ports sortants</span><span class="sxs-lookup"><span data-stu-id="ee93a-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="ee93a-209">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="ee93a-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="ee93a-210">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-210">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-211">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="ee93a-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-212">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-212">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-213">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-213">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-214">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee93a-215">Clients</span><span class="sxs-lookup"><span data-stu-id="ee93a-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="ee93a-216">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-216">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-217">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-217">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-218">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="ee93a-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="ee93a-219">Plage de ports multimédias définie</span><span class="sxs-lookup"><span data-stu-id="ee93a-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="ee93a-220">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="ee93a-220">Any</span></span></p></td>
<td><p><span data-ttu-id="ee93a-221">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="ee93a-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

