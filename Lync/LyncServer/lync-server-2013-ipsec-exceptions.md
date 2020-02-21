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
ms.openlocfilehash: bd649cea823ce13460de924ffc49741b3ca5c6d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="58b13-102">Exceptions IPsec dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58b13-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58b13-103">_**Dernière modification de la rubrique :** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="58b13-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="58b13-p101">Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.</span><span class="sxs-lookup"><span data-stu-id="58b13-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="58b13-106">Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.</span><span class="sxs-lookup"><span data-stu-id="58b13-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="58b13-107">Exceptions recommandées pour IPsec</span><span class="sxs-lookup"><span data-stu-id="58b13-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="58b13-108">Nom de la règle</span><span class="sxs-lookup"><span data-stu-id="58b13-108">Rule name</span></span></th>
<th><span data-ttu-id="58b13-109">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="58b13-109">Source IP</span></span></th>
<th><span data-ttu-id="58b13-110">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="58b13-110">Destination IP</span></span></th>
<th><span data-ttu-id="58b13-111">Protocole</span><span class="sxs-lookup"><span data-stu-id="58b13-111">Protocol</span></span></th>
<th><span data-ttu-id="58b13-112">Port source</span><span class="sxs-lookup"><span data-stu-id="58b13-112">Source port</span></span></th>
<th><span data-ttu-id="58b13-113">Port de destination</span><span class="sxs-lookup"><span data-stu-id="58b13-113">Destination port</span></span></th>
<th><span data-ttu-id="58b13-114">Besoin d’authentification</span><span class="sxs-lookup"><span data-stu-id="58b13-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58b13-115">Serveur Edge A/V, ports internes/entrants</span><span class="sxs-lookup"><span data-stu-id="58b13-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-116">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-116">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-117">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="58b13-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="58b13-118">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-119">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-119">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-120">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-120">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-121">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58b13-122">Serveur Edge A/V, ports externes/entrants</span><span class="sxs-lookup"><span data-stu-id="58b13-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-123">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-123">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-124">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="58b13-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="58b13-125">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-126">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-126">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-127">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-127">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-128">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58b13-129">Serveur Edge A/V, ports internes/sortants</span><span class="sxs-lookup"><span data-stu-id="58b13-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-130">Serveur Edge A/V - interne</span><span class="sxs-lookup"><span data-stu-id="58b13-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="58b13-131">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-131">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="58b13-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-133">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-133">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-134">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-134">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-135">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58b13-136">Serveur Edge A/V, ports externes/sortants</span><span class="sxs-lookup"><span data-stu-id="58b13-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-137">Serveur Edge A/V - externe</span><span class="sxs-lookup"><span data-stu-id="58b13-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="58b13-138">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-138">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-139">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-140">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-140">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-141">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-141">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-142">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58b13-143">Serveur de médiation, ports entrants</span><span class="sxs-lookup"><span data-stu-id="58b13-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-144">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-144">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-145">Élaboration</span><span class="sxs-lookup"><span data-stu-id="58b13-145">Mediation</span></span></p>
<p><span data-ttu-id="58b13-146">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="58b13-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="58b13-147">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-148">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-148">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-149">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-149">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-150">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58b13-151">Serveur de médiation, ports sortants</span><span class="sxs-lookup"><span data-stu-id="58b13-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-152">Élaboration</span><span class="sxs-lookup"><span data-stu-id="58b13-152">Mediation</span></span></p>
<p><span data-ttu-id="58b13-153">Serveur (s)</span><span class="sxs-lookup"><span data-stu-id="58b13-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="58b13-154">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-154">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-155">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-156">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-156">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-157">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-157">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-158">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58b13-159">Intendant Conférence entrant</span><span class="sxs-lookup"><span data-stu-id="58b13-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-160">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-160">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-161">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="58b13-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="58b13-162">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-163">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-163">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-164">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-164">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-165">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58b13-166">Intendant Conférence sortant</span><span class="sxs-lookup"><span data-stu-id="58b13-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-167">Serveur frontal exécutant l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="58b13-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="58b13-168">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-168">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-169">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-170">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-170">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-171">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-171">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-172">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58b13-173">Serveur de conférence A/V, ports entrants</span><span class="sxs-lookup"><span data-stu-id="58b13-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-174">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-174">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-175">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="58b13-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="58b13-176">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-177">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-177">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-178">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-178">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-179">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58b13-180">Conférence A/V, ports sortants</span><span class="sxs-lookup"><span data-stu-id="58b13-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-181">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="58b13-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="58b13-182">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-182">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-183">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-184">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-184">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-185">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-185">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-186">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58b13-187">Exchange, ports entrants</span><span class="sxs-lookup"><span data-stu-id="58b13-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-188">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-188">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-189">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="58b13-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="58b13-190">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-191">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-191">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-192">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-192">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-193">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58b13-194">Serveurs de partage d’application, ports entrants</span><span class="sxs-lookup"><span data-stu-id="58b13-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-195">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-195">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-196">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="58b13-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="58b13-197">TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-198">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-198">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-199">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-199">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-200">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58b13-201">Serveur de partage d’application, ports sortants</span><span class="sxs-lookup"><span data-stu-id="58b13-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-202">Serveurs de partage d’application</span><span class="sxs-lookup"><span data-stu-id="58b13-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="58b13-203">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-203">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-204">TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-205">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-205">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-206">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-206">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-207">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58b13-208">Exchange, ports sortants</span><span class="sxs-lookup"><span data-stu-id="58b13-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="58b13-209">Messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="58b13-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="58b13-210">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-210">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-211">UDP et TCP</span><span class="sxs-lookup"><span data-stu-id="58b13-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="58b13-212">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-212">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-213">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-213">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-214">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58b13-215">Clients</span><span class="sxs-lookup"><span data-stu-id="58b13-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="58b13-216">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-216">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-217">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-217">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-218">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="58b13-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="58b13-219">Plage de ports multimédias définie</span><span class="sxs-lookup"><span data-stu-id="58b13-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="58b13-220">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="58b13-220">Any</span></span></p></td>
<td><p><span data-ttu-id="58b13-221">Ne pas authentifier</span><span class="sxs-lookup"><span data-stu-id="58b13-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

