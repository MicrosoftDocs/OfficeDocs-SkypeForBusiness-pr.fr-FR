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
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514151"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="a6e37-102">Exceptions IPsec dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6e37-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6e37-103">_**Dernière modification de la rubrique :** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="a6e37-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="a6e37-p101">Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.</span><span class="sxs-lookup"><span data-stu-id="a6e37-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="a6e37-106">Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.</span><span class="sxs-lookup"><span data-stu-id="a6e37-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="a6e37-107">Exceptions recommandées pour IPsec</span><span class="sxs-lookup"><span data-stu-id="a6e37-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="a6e37-108">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="a6e37-108">Rule name</span></span></th>
<th><span data-ttu-id="a6e37-109">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="a6e37-109">Source IP</span></span></th>
<th><span data-ttu-id="a6e37-110">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="a6e37-110">Destination IP</span></span></th>
<th><span data-ttu-id="a6e37-111">Protocole</span><span class="sxs-lookup"><span data-stu-id="a6e37-111">Protocol</span></span></th>
<th><span data-ttu-id="a6e37-112">Port source</span><span class="sxs-lookup"><span data-stu-id="a6e37-112">Source port</span></span></th>
<th><span data-ttu-id="a6e37-113">Port de destination</span><span class="sxs-lookup"><span data-stu-id="a6e37-113">Destination port</span></span></th>
<th><span data-ttu-id="a6e37-114">Besoin d’authentification</span><span class="sxs-lookup"><span data-stu-id="a6e37-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6e37-115">Serveur Edge A/V, ports internes/entrants</span><span class="sxs-lookup"><span data-stu-id="a6e37-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-116">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-116">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-117">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="a6e37-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="a6e37-118">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-119">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-119">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-120">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-120">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-121">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e37-122">Serveur Edge A/V, ports externes/entrants</span><span class="sxs-lookup"><span data-stu-id="a6e37-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-123">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-123">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-124">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="a6e37-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="a6e37-125">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-126">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-126">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-127">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-127">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-128">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e37-129">Serveur Edge A/V, ports internes/sortants</span><span class="sxs-lookup"><span data-stu-id="a6e37-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-130">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="a6e37-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="a6e37-131">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-131">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-132">&amp;TCP UDP</span><span class="sxs-lookup"><span data-stu-id="a6e37-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-133">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-133">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-134">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-135">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e37-136">Serveur Edge A/V, ports externes/sortants</span><span class="sxs-lookup"><span data-stu-id="a6e37-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-137">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="a6e37-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="a6e37-138">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-139">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-140">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-140">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-141">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-142">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e37-143">Serveur de médiation, ports entrants</span><span class="sxs-lookup"><span data-stu-id="a6e37-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-144">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-144">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-145">Élaboration</span><span class="sxs-lookup"><span data-stu-id="a6e37-145">Mediation</span></span></p>
<p><span data-ttu-id="a6e37-146">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="a6e37-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="a6e37-147">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-148">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-148">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-149">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-149">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-150">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e37-151">Serveur de médiation, ports sortants</span><span class="sxs-lookup"><span data-stu-id="a6e37-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-152">Élaboration</span><span class="sxs-lookup"><span data-stu-id="a6e37-152">Mediation</span></span></p>
<p><span data-ttu-id="a6e37-153">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="a6e37-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="a6e37-154">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-154">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-155">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-156">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-156">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-157">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-157">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-158">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e37-159">Intendant Conférence entrant</span><span class="sxs-lookup"><span data-stu-id="a6e37-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-160">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-160">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-161">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="a6e37-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="a6e37-162">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-163">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-163">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-164">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-164">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-165">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e37-166">Intendant Conférence sortant</span><span class="sxs-lookup"><span data-stu-id="a6e37-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-167">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="a6e37-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="a6e37-168">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-168">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-169">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-170">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-170">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-171">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-171">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-172">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e37-173">Serveur de conférence A/V, ports entrants</span><span class="sxs-lookup"><span data-stu-id="a6e37-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-174">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-174">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-175">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a6e37-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a6e37-176">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-177">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-177">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-178">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-178">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-179">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e37-180">Conférence A/V, ports sortants</span><span class="sxs-lookup"><span data-stu-id="a6e37-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-181">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a6e37-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a6e37-182">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-182">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-183">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-184">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-184">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-185">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-185">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-186">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e37-187">Exchange, ports entrants</span><span class="sxs-lookup"><span data-stu-id="a6e37-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-188">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-188">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-189">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="a6e37-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="a6e37-190">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-191">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-191">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-192">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-192">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-193">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e37-194">Serveurs de partage d’application, ports entrants</span><span class="sxs-lookup"><span data-stu-id="a6e37-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-195">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-195">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-196">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="a6e37-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="a6e37-197">TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-198">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-198">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-199">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-199">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-200">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e37-201">Serveur de partage d’application, ports sortants</span><span class="sxs-lookup"><span data-stu-id="a6e37-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-202">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="a6e37-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="a6e37-203">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-203">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-204">TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-205">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-205">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-206">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-206">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-207">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e37-208">Exchange, ports sortants</span><span class="sxs-lookup"><span data-stu-id="a6e37-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="a6e37-209">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="a6e37-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="a6e37-210">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-210">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-211">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="a6e37-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-212">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-212">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-213">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-213">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-214">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e37-215">Clients</span><span class="sxs-lookup"><span data-stu-id="a6e37-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="a6e37-216">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-216">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-217">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-217">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-218">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="a6e37-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="a6e37-219">Plage de ports multimédias définie</span><span class="sxs-lookup"><span data-stu-id="a6e37-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="a6e37-220">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a6e37-220">Any</span></span></p></td>
<td><p><span data-ttu-id="a6e37-221">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="a6e37-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

