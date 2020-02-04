---
title: 'Lync Server 2013 : Sélection d’une topologie'
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
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="d03d5-102">Sélection d’une topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03d5-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="d03d5-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d03d5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d03d5-104">Lorsque vous choisissez une topologie, vous pouvez utiliser l’une des options de topologie suivantes prises en charge :</span><span class="sxs-lookup"><span data-stu-id="d03d5-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d03d5-105">Sauf indication contraire, si vous avez une connaissance de Microsoft Lync Server 2010, les conseils sont en grande partie inchangés.</span><span class="sxs-lookup"><span data-stu-id="d03d5-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="d03d5-106">Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03d5-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="d03d5-107">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03d5-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="d03d5-108">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03d5-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="d03d5-109">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03d5-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="d03d5-110">Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03d5-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="d03d5-111">L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge.</span><span class="sxs-lookup"><span data-stu-id="d03d5-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="d03d5-112">Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.</span><span class="sxs-lookup"><span data-stu-id="d03d5-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="d03d5-113">Le tableau suivant récapitule les fonctionnalités disponibles avec les topologies Microsoft Lync Server 2013 prises en charge.</span><span class="sxs-lookup"><span data-stu-id="d03d5-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="d03d5-114">Les en-têtes de colonne indiquent les fonctionnalités disponibles pour une option de configuration latérale donnée.</span><span class="sxs-lookup"><span data-stu-id="d03d5-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="d03d5-115">Par exemple, en utilisant l’option de répartition de charge DNS, vous pouvez voir qu’elle prend en charge une haute disponibilité, qu’elle peut utiliser des adresses IP privées non routables (avec la traduction d’adresses réseau) ou des adresses IP publiques routables attribuées aux interfaces externes d’Edge, et réduit les coûts, car un aucun équilibrage de charge matérielle n’est requis.</span><span class="sxs-lookup"><span data-stu-id="d03d5-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="d03d5-116">Les scénarios de basculement de périphérie pris en charge lors de l’équilibrage de charge DNS sont des sessions Lync-to-Lync, des sessions de conférence Lync, des sessions Lync-to-RTC et Office 365.</span><span class="sxs-lookup"><span data-stu-id="d03d5-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="d03d5-117">Les scénarios de basculement vers le bord qui ne bénéficient pas de l’équilibrage de charge DNS sont de basculement pour la messagerie unifiée Exchange Remote User (MU) (antérieure à Exchange 2010 SP1), la connectivité de messagerie instantanée publique et la Fédération avec les serveurs exécutant des communications Office Serveurs.</span><span class="sxs-lookup"><span data-stu-id="d03d5-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="d03d5-118">Résumé des options de topologie du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="d03d5-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="d03d5-119">Topologie</span><span class="sxs-lookup"><span data-stu-id="d03d5-119">Topology</span></span></th>
<th><span data-ttu-id="d03d5-120">Haute disponibilité</span><span class="sxs-lookup"><span data-stu-id="d03d5-120">High availability</span></span></th>
<th><span data-ttu-id="d03d5-121">Enregistrements DNS supplémentaires requis pour le serveur Edge externe dans le pool Edge</span><span class="sxs-lookup"><span data-stu-id="d03d5-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="d03d5-122">Reprise latérale pour les sessions Lync-to-Lync</span><span class="sxs-lookup"><span data-stu-id="d03d5-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="d03d5-123">Reprise latérale pour les sessions de Fédération Lync-to-Lync EUM/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="d03d5-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d03d5-124">Un seul bord avec tar</span><span class="sxs-lookup"><span data-stu-id="d03d5-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="d03d5-125">Non</span><span class="sxs-lookup"><span data-stu-id="d03d5-125">No</span></span></p></td>
<td><p><span data-ttu-id="d03d5-126">Non</span><span class="sxs-lookup"><span data-stu-id="d03d5-126">No</span></span></p></td>
<td><p><span data-ttu-id="d03d5-127">Non</span><span class="sxs-lookup"><span data-stu-id="d03d5-127">No</span></span></p></td>
<td><p><span data-ttu-id="d03d5-128">Non</span><span class="sxs-lookup"><span data-stu-id="d03d5-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d03d5-129">Bordure unique avec adresse IP publique</span><span class="sxs-lookup"><span data-stu-id="d03d5-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="d03d5-130">Non</span><span class="sxs-lookup"><span data-stu-id="d03d5-130">No</span></span></p></td>
<td><p><span data-ttu-id="d03d5-131">Non</span><span class="sxs-lookup"><span data-stu-id="d03d5-131">No</span></span></p></td>
<td><p><span data-ttu-id="d03d5-132">Non</span><span class="sxs-lookup"><span data-stu-id="d03d5-132">No</span></span></p></td>
<td><p><span data-ttu-id="d03d5-133">Non</span><span class="sxs-lookup"><span data-stu-id="d03d5-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d03d5-134">Edge mis à l’échelle (équilibrage de charge DNS) avec tar</span><span class="sxs-lookup"><span data-stu-id="d03d5-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="d03d5-135">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="d03d5-136">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="d03d5-137">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d03d5-138">Contour ajusté (équilibrage de charge DNS) avec adresse IP publique</span><span class="sxs-lookup"><span data-stu-id="d03d5-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="d03d5-139">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="d03d5-140">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="d03d5-141">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d03d5-142">Répartition de charge matérielle latérale mise à l’échelle</span><span class="sxs-lookup"><span data-stu-id="d03d5-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="d03d5-143">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="d03d5-144">Non (un enregistrement DNS A par VIP)</span><span class="sxs-lookup"><span data-stu-id="d03d5-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="d03d5-145">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="d03d5-146">Oui</span><span class="sxs-lookup"><span data-stu-id="d03d5-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d03d5-147">**\*** Le basculement pour la connectivité de messagerie instantanée publique, et la Fédération avec des serveurs exécutant Office Communications Server n’est pas disponible avec l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="d03d5-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="d03d5-148">Le basculement de l’accès à la messagerie unifiée (d’utilisation distante) Exchange Server 2010 SP1 ou une version ultérieure est requise.</span><span class="sxs-lookup"><span data-stu-id="d03d5-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="d03d5-149">Il est possible d’utiliser les topologies à un seul bord et à l’échelle de l’horizontale (équilibrage de charge DNS) :</span><span class="sxs-lookup"><span data-stu-id="d03d5-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="d03d5-150">Adresses IP publiques routables</span><span class="sxs-lookup"><span data-stu-id="d03d5-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="d03d5-151">Adresse IP privée non routable si la traduction d’adresses réseau symétriques est utilisée</span><span class="sxs-lookup"><span data-stu-id="d03d5-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="d03d5-152">Si vous utilisez une adresse IP publique ou une adresse IP privée avec la traduction d’adresses réseau (NAT), vous devez toujours utiliser le même nombre d’adresses IP en fonction de votre choix de configuration dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d03d5-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="d03d5-153">Vous pouvez configurer le serveur de périphérie de sorte qu’il utilise une seule adresse IP avec des ports distincts par service, ou utiliser des adresses IP distinctes par service, mais utiliser le même port (par défaut, TCP 443).</span><span class="sxs-lookup"><span data-stu-id="d03d5-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="d03d5-154">Si vous décidez d’utiliser des adresses IP privées sans routage avec tar :</span><span class="sxs-lookup"><span data-stu-id="d03d5-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="d03d5-155">Vous devez utiliser des adresses IP privées routables sur les trois interfaces externes</span><span class="sxs-lookup"><span data-stu-id="d03d5-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="d03d5-156">Vous devez configurer la traduction d’adresses réseau symétrique pour le trafic entrant et sortant.</span><span class="sxs-lookup"><span data-stu-id="d03d5-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="d03d5-157">La topologie de l’équilibrage du matériel doit utiliser des adresses IP publiques.</span><span class="sxs-lookup"><span data-stu-id="d03d5-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="d03d5-158">Lync Server 2013 prend en charge le placement d’accès, de conférences Web et d’interfaces externes A/V à partir d’un routeur ou d’un pare-feu qui effectue la traduction d’adresses réseau (NAT) pour les topologies de serveur de périphérie unique et à l’échelle.</span><span class="sxs-lookup"><span data-stu-id="d03d5-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="d03d5-159">L’utilisation de la traduction d’adresses réseau pour toutes les interfaces externes d’Edge nécessite l’utilisation de l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="d03d5-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="d03d5-160">Par rapport à l’utilisation d’un dispositif d’équilibrage de la charge matérielle, l’utilisation de l’équilibrage de charge DNS sans NAT vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool Edge, comme décrit dans la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="d03d5-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="d03d5-161">Lync Server 2013 (l’équilibrage de charge DNS) nécessite trois adresses IP publiques pour chaque serveur Edge d’un pool Edge.</span><span class="sxs-lookup"><span data-stu-id="d03d5-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="d03d5-162">Lync Server 2013 (équilibrage de charge matérielle) nécessite trois adresses IP publiques pour les adresses IP virtuelles de l’équilibrage de charge (une exigence qui n’est pas incrémentée en raison de l’ajout de serveurs Edge supplémentaires au pool) et de trois adresses IP publiques par Serveur Edge dans un pool.</span><span class="sxs-lookup"><span data-stu-id="d03d5-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="d03d5-163">Exigences relatives à l’adresse IP pour les bords consolidés mis à l’échelle (adresse IP par rôle)</span><span class="sxs-lookup"><span data-stu-id="d03d5-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d03d5-164">Nombre de serveurs Edge par pool</span><span class="sxs-lookup"><span data-stu-id="d03d5-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="d03d5-165">Nombre d’adresses IP requises Lync Server 2013 (équilibrage de charge DNS)</span><span class="sxs-lookup"><span data-stu-id="d03d5-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="d03d5-166">Nombre d’adresses IP requises Lync Server 2013 (équilibrage de charge matérielle)</span><span class="sxs-lookup"><span data-stu-id="d03d5-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d03d5-167">deuxième</span><span class="sxs-lookup"><span data-stu-id="d03d5-167">2</span></span></p></td>
<td><p><span data-ttu-id="d03d5-168">6</span><span class="sxs-lookup"><span data-stu-id="d03d5-168">6</span></span></p></td>
<td><p><span data-ttu-id="d03d5-169">3 (1 par adresse IP virtuelle) + 6</span><span class="sxs-lookup"><span data-stu-id="d03d5-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d03d5-170">3</span><span class="sxs-lookup"><span data-stu-id="d03d5-170">3</span></span></p></td>
<td><p><span data-ttu-id="d03d5-171">09</span><span class="sxs-lookup"><span data-stu-id="d03d5-171">9</span></span></p></td>
<td><p><span data-ttu-id="d03d5-172">3 (1 par adresse IP virtuelle) + 9</span><span class="sxs-lookup"><span data-stu-id="d03d5-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d03d5-173">4</span><span class="sxs-lookup"><span data-stu-id="d03d5-173">4</span></span></p></td>
<td><p><span data-ttu-id="d03d5-174">midi</span><span class="sxs-lookup"><span data-stu-id="d03d5-174">12</span></span></p></td>
<td><p><span data-ttu-id="d03d5-175">3 (1 par adresse IP virtuelle) + 12</span><span class="sxs-lookup"><span data-stu-id="d03d5-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d03d5-176">5</span><span class="sxs-lookup"><span data-stu-id="d03d5-176">5</span></span></p></td>
<td><p><span data-ttu-id="d03d5-177">0,15</span><span class="sxs-lookup"><span data-stu-id="d03d5-177">15</span></span></p></td>
<td><p><span data-ttu-id="d03d5-178">3 (1 par VIP) + 15</span><span class="sxs-lookup"><span data-stu-id="d03d5-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="d03d5-179">Exigences relatives à l’adresse IP pour les bords consolidés mis à l’échelle (adresse IP unique pour tous les rôles)</span><span class="sxs-lookup"><span data-stu-id="d03d5-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d03d5-180">Nombre de serveurs Edge par pool</span><span class="sxs-lookup"><span data-stu-id="d03d5-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="d03d5-181">Nombre d’adresses IP requises Lync Server 2013 (équilibrage de charge DNS)</span><span class="sxs-lookup"><span data-stu-id="d03d5-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="d03d5-182">Nombre d’adresses IP requises Lync Server 2013 (équilibrage de charge matérielle)</span><span class="sxs-lookup"><span data-stu-id="d03d5-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d03d5-183">2</span><span class="sxs-lookup"><span data-stu-id="d03d5-183">2</span></span></p></td>
<td><p><span data-ttu-id="d03d5-184">deuxième</span><span class="sxs-lookup"><span data-stu-id="d03d5-184">2</span></span></p></td>
<td><p><span data-ttu-id="d03d5-185">1 (1 par adresse IP virtuelle) + 2</span><span class="sxs-lookup"><span data-stu-id="d03d5-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d03d5-186">3</span><span class="sxs-lookup"><span data-stu-id="d03d5-186">3</span></span></p></td>
<td><p><span data-ttu-id="d03d5-187">3</span><span class="sxs-lookup"><span data-stu-id="d03d5-187">3</span></span></p></td>
<td><p><span data-ttu-id="d03d5-188">1 (1 par adresse IP virtuelle) + 3</span><span class="sxs-lookup"><span data-stu-id="d03d5-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d03d5-189">4</span><span class="sxs-lookup"><span data-stu-id="d03d5-189">4</span></span></p></td>
<td><p><span data-ttu-id="d03d5-190">4</span><span class="sxs-lookup"><span data-stu-id="d03d5-190">4</span></span></p></td>
<td><p><span data-ttu-id="d03d5-191">1 (1 par adresse IP virtuelle) + 4</span><span class="sxs-lookup"><span data-stu-id="d03d5-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d03d5-192">5</span><span class="sxs-lookup"><span data-stu-id="d03d5-192">5</span></span></p></td>
<td><p><span data-ttu-id="d03d5-193">5</span><span class="sxs-lookup"><span data-stu-id="d03d5-193">5</span></span></p></td>
<td><p><span data-ttu-id="d03d5-194">1 (1 par adresse IP virtuelle) + 5</span><span class="sxs-lookup"><span data-stu-id="d03d5-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d03d5-195">Les points de décision principaux pour la sélection de la topologie sont haute disponibilité et équilibrage de la charge.</span><span class="sxs-lookup"><span data-stu-id="d03d5-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="d03d5-196">La configuration requise pour une haute disponibilité peut influer sur la décision d’équilibrage de la charge.</span><span class="sxs-lookup"><span data-stu-id="d03d5-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="d03d5-197">**Haute disponibilité**   Si vous avez besoin d’une haute disponibilité, déployez au moins deux serveurs Edge dans un pool.</span><span class="sxs-lookup"><span data-stu-id="d03d5-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="d03d5-198">Un seul pool de bords peut prendre en charge jusqu’à 12 serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="d03d5-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="d03d5-199">Si une plus grande capacité est requise, vous pouvez déployer plusieurs pools de périphérie.</span><span class="sxs-lookup"><span data-stu-id="d03d5-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="d03d5-200">En règle générale, 10% d’une base d’utilisateurs donnée doivent disposer d’un accès externe.</span><span class="sxs-lookup"><span data-stu-id="d03d5-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d03d5-201">Le générateur de topologie vous permet de configurer un maximum de 25 serveurs Edge dans un seul pool Edge.</span><span class="sxs-lookup"><span data-stu-id="d03d5-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="d03d5-202">Le nombre maximal de serveurs de périphérie testé et pris en charge dans un pool est de douze et le générateur de topologie autorisant un nombre supérieur à douze ne doit pas être interprété comme une prise en charge implicite de plus de douze serveurs de frontière dans un seul pool Edge.</span><span class="sxs-lookup"><span data-stu-id="d03d5-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="d03d5-203">**Équilibrage de charge matérielle**   Le système d’équilibrage de la charge matérielle est pris en charge pour l’équilibrage de charge des serveurs Edge Lync Server 2013 lors de l’utilisation d’adresses IP routables publiques pour les interfaces externes de périphérie.</span><span class="sxs-lookup"><span data-stu-id="d03d5-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="d03d5-204">Par exemple, vous pouvez utiliser cette approche dans les situations dans lesquelles le basculement est requis pour l’une des applications suivantes :</span><span class="sxs-lookup"><span data-stu-id="d03d5-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="d03d5-205">Solution PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="d03d5-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="d03d5-206">Fédération avec des sociétés exécutant Microsoft Office Communications Server 2007 ou Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d03d5-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="d03d5-207">Accès externe à la messagerie unifiée Exchange 2007 ou à la messagerie unifiée Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="d03d5-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="d03d5-208">L’équilibrage de charge DNS pour Exchange 2010 SP1 et les versions ultérieures est pris en charge pour la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="d03d5-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="d03d5-209">Ces trois applications continuent de fonctionner, mais elles ne sont pas compatibles avec l’équilibrage de charge DNS et ne se connectent qu’au premier serveur Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="d03d5-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="d03d5-210">Si ce serveur n’est pas disponible, la connexion échouera.</span><span class="sxs-lookup"><span data-stu-id="d03d5-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="d03d5-211">Par exemple, si plusieurs serveurs Edge sont déployés dans un pool pour gérer le chargement du trafic fédéré, un seul proxy d’accès reçoit réellement le trafic alors que les autres sont inactifs.</span><span class="sxs-lookup"><span data-stu-id="d03d5-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d03d5-212">Il est recommandé d’utiliser l’équilibrage de charge DNS si vous vous fédérationz avec des entreprises utilisant Lync Server 2010 et Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="d03d5-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="d03d5-213">Sachez qu’il existe d’importants impacts sur les performances si la plupart de vos partenaires fédérés utilisent Office Communications Server 2007 ou Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d03d5-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="d03d5-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d03d5-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

