---
title: 'Lync Server 2013 : choix d’une topologie'
description: 'Lync Server 2013 : choix d’une topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01ded739c3c5e4e0bd8c0f25f3f0fe8ff1f350b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549680"
---
# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="4e847-103">Choix d’une topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e847-103">Choosing a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="4e847-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4e847-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4e847-105">Lorsque vous choisissez une topologie, vous pouvez utiliser l’une des options de topologie prises en charge suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e847-105">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4e847-106">Sauf indication contraire, si vous avez une expérience de Microsoft Lync Server 2010, vous trouverez ci-dessous des conseils inchangés.</span><span class="sxs-lookup"><span data-stu-id="4e847-106">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="4e847-107">Serveur Edge consolidé unique avec des adresses IP privées et une interface NAT dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e847-107">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="4e847-108">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e847-108">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="4e847-109">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e847-109">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="4e847-110">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e847-110">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="4e847-111">Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e847-111">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="4e847-p101">Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.</span><span class="sxs-lookup"><span data-stu-id="4e847-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="4e847-114">Le tableau suivant récapitule les fonctionnalités disponibles avec les topologies Microsoft Lync Server 2013 prises en charge.</span><span class="sxs-lookup"><span data-stu-id="4e847-114">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="4e847-115">Le titre des colonnes indique la fonctionnalité disponible pour une option de configuration Edge donnée.</span><span class="sxs-lookup"><span data-stu-id="4e847-115">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="4e847-116">Par exemple, vous pouvez voir que l’option Serveur Edge mise à l’échelle (charge DNS équilibrée) prend en charge la haute disponibilité, peut utiliser des adresses IP privées non routables (avec NAT) ou des adresses IP publiques routables affectées aux interfaces externes du serveur Edge et permet de réduire les coûts, car elle ne nécessite pas de programme d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="4e847-116">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="4e847-117">Les scénarios de basculement de serveur Edge pris en charge avec l’équilibrage de charge DNS sont des sessions de point à point entre Lync et Lync, des sessions de conférence Lync, des sessions Lync à PSTN, Office 365 et Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e847-117">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions, Office 365, and Microsoft 365.</span></span> <span data-ttu-id="4e847-118">Les scénarios de basculement de serveur Edge qui ne bénéficient pas de l’équilibrage de charge DNS sont des basculements pour la messagerie unifiée Exchange de l’utilisateur distant (avant Exchange 2010 SP1), la connectivité de messagerie instantanée publique et la Fédération avec des serveurs exécutant Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="4e847-118">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="4e847-119">Récapitulatif des options de topologie de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="4e847-119">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e847-120">Topologie</span><span class="sxs-lookup"><span data-stu-id="4e847-120">Topology</span></span></th>
<th><span data-ttu-id="4e847-121">Haute disponibilité</span><span class="sxs-lookup"><span data-stu-id="4e847-121">High availability</span></span></th>
<th><span data-ttu-id="4e847-122">Enregistrement DNS A supplémentaire requis pour un serveur Edge externe du pool Edge</span><span class="sxs-lookup"><span data-stu-id="4e847-122">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="4e847-123">Basculement de serveur Edge pour les sessions Lync à Lync</span><span class="sxs-lookup"><span data-stu-id="4e847-123">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="4e847-124">Basculement Edge pour les sessions Lync-to-Lync EUM/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="4e847-124">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e847-125">Serveur Edge unique utilisant NAT</span><span class="sxs-lookup"><span data-stu-id="4e847-125">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="4e847-126">Non</span><span class="sxs-lookup"><span data-stu-id="4e847-126">No</span></span></p></td>
<td><p><span data-ttu-id="4e847-127">Non</span><span class="sxs-lookup"><span data-stu-id="4e847-127">No</span></span></p></td>
<td><p><span data-ttu-id="4e847-128">Non</span><span class="sxs-lookup"><span data-stu-id="4e847-128">No</span></span></p></td>
<td><p><span data-ttu-id="4e847-129">Non</span><span class="sxs-lookup"><span data-stu-id="4e847-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e847-130">Serveur Edge unique utilisant les adresses IP publiques</span><span class="sxs-lookup"><span data-stu-id="4e847-130">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="4e847-131">Non</span><span class="sxs-lookup"><span data-stu-id="4e847-131">No</span></span></p></td>
<td><p><span data-ttu-id="4e847-132">Non</span><span class="sxs-lookup"><span data-stu-id="4e847-132">No</span></span></p></td>
<td><p><span data-ttu-id="4e847-133">Non</span><span class="sxs-lookup"><span data-stu-id="4e847-133">No</span></span></p></td>
<td><p><span data-ttu-id="4e847-134">Non</span><span class="sxs-lookup"><span data-stu-id="4e847-134">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e847-135">Serveur Edge mis à l’échelle (charge DNS équilibrée) utilisant NAT</span><span class="sxs-lookup"><span data-stu-id="4e847-135">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="4e847-136">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e847-137">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-137">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e847-138">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-138">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e847-139">Serveur Edge mis à l’échelle (charge DNS équilibrée) utilisant les adresses IP publiques</span><span class="sxs-lookup"><span data-stu-id="4e847-139">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="4e847-140">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e847-141">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e847-142">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-142">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e847-143">Serveur Edge mis à l’échelle (avec charge matérielle équilibrée)</span><span class="sxs-lookup"><span data-stu-id="4e847-143">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="4e847-144">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e847-145">Non (un enregistrement DNS A par VIP)</span><span class="sxs-lookup"><span data-stu-id="4e847-145">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="4e847-146">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e847-147">Oui</span><span class="sxs-lookup"><span data-stu-id="4e847-147">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4e847-148">**\*** Le basculement pour la connectivité PIC (public Instant Messaging) et la Fédération avec des serveurs exécutant Office Communications Server ne sont pas disponibles avec l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="4e847-148">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="4e847-149">Le basculement de la messagerie unifiée Exchange (utilisateur distant) à l’aide de l’équilibrage de charge DNS nécessite Exchange Server 2010 SP1 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="4e847-149">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="4e847-150">Serveur Edge mis à l’échelle (équilibrage de charge DNS)</span><span class="sxs-lookup"><span data-stu-id="4e847-150">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="4e847-151">Adresses IP publiques routables</span><span class="sxs-lookup"><span data-stu-id="4e847-151">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="4e847-152">Adresse IP privée non routable si la traduction d’adresses réseau (NAT) symétrique est utilisée</span><span class="sxs-lookup"><span data-stu-id="4e847-152">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="4e847-153">Si vous utilisez une adresse IP publique ou une adresse IP privée avec NAT, vous continuerez à utiliser le même nombre d’adresses IP en fonction de votre choix de configuration dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="4e847-153">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="4e847-154">Vous pouvez configurer le serveur Edge de sorte qu’il utilise une seule adresse IP avec des ports distincts par service, ou utiliser des adresses IP distinctes par service, mais utiliser le même port (par défaut, TCP 443).</span><span class="sxs-lookup"><span data-stu-id="4e847-154">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="4e847-155">Si vous décidez d’utiliser des adresses IP privées non routables avec tar, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4e847-155">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="4e847-156">Vous devez utiliser des adresses IP privées routables sur les trois interfaces externes</span><span class="sxs-lookup"><span data-stu-id="4e847-156">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="4e847-157">Vous devez configurer la traduction d’adresses réseau symétrique pour le trafic entrant et sortant</span><span class="sxs-lookup"><span data-stu-id="4e847-157">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="4e847-158">Les topologies de serveur Edge mises à l’échelle (avec équilibrage de la charge matérielle) doivent utiliser des adresses IP publiques.</span><span class="sxs-lookup"><span data-stu-id="4e847-158">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="4e847-159">Lync Server 2013 prend en charge le positionnement des interfaces externes d’accès, de conférence Web et de serveur Edge A/V derrière un routeur ou un pare-feu qui effectue la traduction d’adresses réseau (NAT) pour les topologies de serveur Edge consolidées simples et mises à l’ampleur.</span><span class="sxs-lookup"><span data-stu-id="4e847-159">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="4e847-p106">L’utilisation de la technologie NAT pour toutes les interfaces externes Edge exige le recours à l’équilibrage de la charge DNS. Comparé aux programmes d’équilibrage de la charge matérielle, l’équilibrage de la charge DNS (Domain Name System) permet de réduire le nombre d’adresses IP publiques pour chaque serveur Edge au sein d’un pool comme le décrit la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="4e847-p106">Using NAT for all Edge external interfaces requires the use of DNS load balancing. When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="4e847-162">Lync Server 2013 serveur Edge consolidé mis à l’ampleur (charge DNS équilibrée) nécessite trois adresses IP publiques pour chaque serveur Edge dans un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="4e847-162">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="4e847-163">Lync Server 2013 serveur Edge consolidé mis à l’ampleur (avec charge matérielle équilibrée) nécessite trois adresses IP publiques pour les adresses IP virtuelles du programme d’équilibrage de la charge (une exigence unique qui n’est pas incrémentée au fur et à mesure que des serveurs Edge sont ajoutés au pool), ainsi que trois adresses IP publiques par serveur Edge dans un pool.</span><span class="sxs-lookup"><span data-stu-id="4e847-163">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="4e847-164">Exigences d’adresses IP pour la topologie Edge consolidée (adresse IP par rôle)</span><span class="sxs-lookup"><span data-stu-id="4e847-164">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e847-165">Nombre de serveurs Edge par pool</span><span class="sxs-lookup"><span data-stu-id="4e847-165">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="4e847-166">Nombre d’adresses IP requises Lync Server 2013 (charge DNS équilibrée)</span><span class="sxs-lookup"><span data-stu-id="4e847-166">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="4e847-167">Nombre d’adresses IP requises Lync Server 2013 (charge matérielle équilibrée)</span><span class="sxs-lookup"><span data-stu-id="4e847-167">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e847-168">n°2</span><span class="sxs-lookup"><span data-stu-id="4e847-168">2</span></span></p></td>
<td><p><span data-ttu-id="4e847-169">6 </span><span class="sxs-lookup"><span data-stu-id="4e847-169">6</span></span></p></td>
<td><p><span data-ttu-id="4e847-170">3 (1 par adresse IP virtuelle) + 6</span><span class="sxs-lookup"><span data-stu-id="4e847-170">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e847-171">3</span><span class="sxs-lookup"><span data-stu-id="4e847-171">3</span></span></p></td>
<td><p><span data-ttu-id="4e847-172">9 </span><span class="sxs-lookup"><span data-stu-id="4e847-172">9</span></span></p></td>
<td><p><span data-ttu-id="4e847-173">3 (1 par adresse IP virtuelle) + 9</span><span class="sxs-lookup"><span data-stu-id="4e847-173">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e847-174">4 </span><span class="sxs-lookup"><span data-stu-id="4e847-174">4</span></span></p></td>
<td><p><span data-ttu-id="4e847-175">12 </span><span class="sxs-lookup"><span data-stu-id="4e847-175">12</span></span></p></td>
<td><p><span data-ttu-id="4e847-176">3 (1 par adresse IP virtuelle) + 12</span><span class="sxs-lookup"><span data-stu-id="4e847-176">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e847-177">5 </span><span class="sxs-lookup"><span data-stu-id="4e847-177">5</span></span></p></td>
<td><p><span data-ttu-id="4e847-178">15 </span><span class="sxs-lookup"><span data-stu-id="4e847-178">15</span></span></p></td>
<td><p><span data-ttu-id="4e847-179">3 (1 par adresse IP virtuelle) + 15</span><span class="sxs-lookup"><span data-stu-id="4e847-179">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="4e847-180">Exigences d’adresses IP pour la topologie Edge consolidée mise à l’échelle (adresse IP unique pour tous les rôles)</span><span class="sxs-lookup"><span data-stu-id="4e847-180">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e847-181">Nombre de serveurs Edge par pool</span><span class="sxs-lookup"><span data-stu-id="4e847-181">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="4e847-182">Nombre d’adresses IP requises Lync Server 2013 (charge DNS équilibrée)</span><span class="sxs-lookup"><span data-stu-id="4e847-182">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="4e847-183">Nombre d’adresses IP requises Lync Server 2013 (charge matérielle équilibrée)</span><span class="sxs-lookup"><span data-stu-id="4e847-183">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e847-184">n°2</span><span class="sxs-lookup"><span data-stu-id="4e847-184">2</span></span></p></td>
<td><p><span data-ttu-id="4e847-185">n°2</span><span class="sxs-lookup"><span data-stu-id="4e847-185">2</span></span></p></td>
<td><p><span data-ttu-id="4e847-186">1 (1 par adresse IP virtuelle) + 2</span><span class="sxs-lookup"><span data-stu-id="4e847-186">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e847-187">3</span><span class="sxs-lookup"><span data-stu-id="4e847-187">3</span></span></p></td>
<td><p><span data-ttu-id="4e847-188">3</span><span class="sxs-lookup"><span data-stu-id="4e847-188">3</span></span></p></td>
<td><p><span data-ttu-id="4e847-189">1 (1 par adresse IP virtuelle) + 3</span><span class="sxs-lookup"><span data-stu-id="4e847-189">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e847-190">4 </span><span class="sxs-lookup"><span data-stu-id="4e847-190">4</span></span></p></td>
<td><p><span data-ttu-id="4e847-191">4 </span><span class="sxs-lookup"><span data-stu-id="4e847-191">4</span></span></p></td>
<td><p><span data-ttu-id="4e847-192">1 (1 par adresse IP virtuelle) + 4</span><span class="sxs-lookup"><span data-stu-id="4e847-192">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e847-193">5 </span><span class="sxs-lookup"><span data-stu-id="4e847-193">5</span></span></p></td>
<td><p><span data-ttu-id="4e847-194">disque</span><span class="sxs-lookup"><span data-stu-id="4e847-194">5</span></span></p></td>
<td><p><span data-ttu-id="4e847-195">1 (1 par adresse IP virtuelle) + 5</span><span class="sxs-lookup"><span data-stu-id="4e847-195">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4e847-p107">Les principaux points devant orienter la sélection de la topologie sont la haute disponibilité et l’équilibrage de la charge. Si la haute disponibilité est requise, cela peut influencer la décision que vous prendrez en matière d’équilibrage de la charge.</span><span class="sxs-lookup"><span data-stu-id="4e847-p107">The primary decision points for topology selection are high availability and load balancing. The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="4e847-198">**Haute disponibilité**   Si vous avez besoin d’une haute disponibilité, déployez au moins deux serveurs Edge dans un pool.</span><span class="sxs-lookup"><span data-stu-id="4e847-198">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="4e847-199">Un pool Edge unique prend en charge jusqu’à douze serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="4e847-199">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="4e847-200">Pour davantage de capacité, vous pouvez déployer plusieurs pools Edge.</span><span class="sxs-lookup"><span data-stu-id="4e847-200">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="4e847-201">En règle générale, 10 % du nombre d’utilisateurs inclus dans la base auront besoin d’un accès externe.</span><span class="sxs-lookup"><span data-stu-id="4e847-201">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="4e847-202">Le générateur de topologies vous permet de configurer jusqu’à vingt serveurs Edge dans un seul pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="4e847-202">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="4e847-203">Le nombre maximal testé et pris en charge de serveurs Edge dans un pool est de douze et le générateur de topologie autorise un nombre supérieur à douze ne doit pas être interprété comme une prise en charge implicite de plus de douze serveurs Edge dans un seul pool Edge.</span><span class="sxs-lookup"><span data-stu-id="4e847-203">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="4e847-204">**Équilibrage de la charge matérielle**   L’équilibrage de la charge matérielle est pris en charge pour l’équilibrage de charge des serveurs Edge Lync Server 2013 lors de l’utilisation d’adresses IP routables publiquement pour les interfaces externes Edge.</span><span class="sxs-lookup"><span data-stu-id="4e847-204">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="4e847-205">Par exemple, vous devez utiliser cette approche dans les situations où le basculement est nécessaire aux applications suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e847-205">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="4e847-206">solution PIC (Public IM Connectivity) ;</span><span class="sxs-lookup"><span data-stu-id="4e847-206">Public IM connectivity</span></span>
    
      - <span data-ttu-id="4e847-207">Fédération avec des entreprises exécutant Microsoft Office Communications Server 2007 ou Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4e847-207">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="4e847-208">accès externe à la messagerie unifiée Exchange 2007 ou Exchange 2010 ;</span><span class="sxs-lookup"><span data-stu-id="4e847-208">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="4e847-209">L’équilibrage de charge DNS pour Exchange 2010 SP1 et les versions ultérieures est pris en charge pour la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="4e847-209">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="4e847-p111">Ces trois applications continueront à fonctionner, mais ne pourront pas tirer parti de l’équilibrage de la charge DNS et ne se connecteront qu’au premier serveur Edge du pool. En cas d’indisponibilité de ce serveur, la connexion échoue. Par exemple, si plusieurs serveurs Edge sont déployés sur un pool en vue de gérer la charge de trafic fédérée, seul un proxy d’accès recevra le trafic alors que les autres seront inactifs.</span><span class="sxs-lookup"><span data-stu-id="4e847-p111">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool. If that server is unavailable, the connection will fail. For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="4e847-213">L’utilisation de l’équilibrage de charge DNS est recommandée si vous vous fédérer avec des entreprises utilisant Lync Server 2010 et Office 365 ou Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e847-213">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Office 365 or Microsoft 365.</span></span> <span data-ttu-id="4e847-214">Sachez qu’il existe un impact significatif sur les performances si la plupart de vos partenaires fédérés utilisent Office Communications Server 2007 ou Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4e847-214">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="4e847-215"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="4e847-215"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

