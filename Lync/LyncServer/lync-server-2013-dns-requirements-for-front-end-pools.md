---
title: 'Lync Server 2013: configuration requise pour le service DNS pour les pools front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="55290-102">Configuration DNS requise pour les listes frontales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55290-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55290-103">_**Dernière modification de la rubrique:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="55290-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="55290-104">Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de la gamme frontale.</span><span class="sxs-lookup"><span data-stu-id="55290-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="55290-105">Enregistrements DNS pour les pools front-end</span><span class="sxs-lookup"><span data-stu-id="55290-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="55290-106">Le tableau suivant indique les exigences DNS pour un déploiement de pool frontal 2013 Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55290-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="55290-107">Configuration requise pour le service DNS pour une liste frontale</span><span class="sxs-lookup"><span data-stu-id="55290-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55290-108">Scénario de déploiement</span><span class="sxs-lookup"><span data-stu-id="55290-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="55290-109">Enregistrement DNS requis</span><span class="sxs-lookup"><span data-stu-id="55290-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55290-110">Pool frontal avec plusieurs serveurs frontaux et un équilibreur de charge matérielle (qu’il s’agisse d’un équilibrage de charge DNS ou non)</span><span class="sxs-lookup"><span data-stu-id="55290-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="55290-111">Lors de l’utilisation de l’équilibrage de charge DNS et de l’équilibrage de charge matérielle, vous devez héberger (A) des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="55290-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="55290-112">Créer un enregistrement A interne qui résout le nom de domaine complet (FQDN) du pool frontal pour l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="55290-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="55290-113">Créer un enregistrement d’hôte interne (A) pour les services Web internes vers l’adresse IP virtuelle (VIP) de l’équilibrage de charge.</span><span class="sxs-lookup"><span data-stu-id="55290-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="55290-114">Vous devez utiliser le nom des services Web internes, tel qu’il est défini dans générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="55290-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="55290-115">Par exemple, si vous utilisez à la fois l’équilibrage de charge DNS et l’équilibrage de charge matérielle, un enregistrement a pour chaque serveur frontal d’un pool pour l’équilibrage de charge DNS et un enregistrement A pour les services Web internes pointant vers l’adresse IP virtuelle de l’équilibrage de charge matérielle. :</span><span class="sxs-lookup"><span data-stu-id="55290-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="55290-116">Équilibrage de charge DNS: adresse IP de Pool01.contoso.net du pool 10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="55290-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="55290-117">Chaque serveur frontal dispose également d’un enregistrement distinct:</span><span class="sxs-lookup"><span data-stu-id="55290-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="55290-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="55290-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="55290-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="55290-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="55290-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="55290-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="55290-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="55290-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="55290-122">Équilibrage de la charge matérielle: adresse IP WebInternal.contoso.net de HLB VIP 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="55290-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="55290-123">Tout le trafic, à l’exception du trafic HTTP/HTTPs, utilise l’enregistrement Pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="55290-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="55290-124">Le trafic HTTP/HTTPs utilise l’adresse de services Web interne définie de 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="55290-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55290-125">Réserve frontale déployée par l’équilibrage de charge DNS</span><span class="sxs-lookup"><span data-stu-id="55290-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="55290-126">Un ensemble d’enregistrements A internes qui résout le nom de domaine complet (FQDN) du pool sur l’adresse IP de chaque serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="55290-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="55290-127">Un enregistrement A doit être enregistré pour chaque serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="55290-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55290-128">Réserve frontale déployée par l’équilibrage de charge DNS</span><span class="sxs-lookup"><span data-stu-id="55290-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="55290-129">Un ensemble d’enregistrements A internes qui résout le nom de domaine complet (FQDN) de chaque serveur dans le pool à l’adresse IP du serveur.</span><span class="sxs-lookup"><span data-stu-id="55290-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="55290-130">Pour plus d’informations, voir <a href="lync-server-2013-dns-load-balancing.md">équilibrage de la charge DNS dans Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="55290-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55290-131">Réserve frontale avec un serveur frontal unique et une base de données principale dédiée, mais pas de solde de charge</span><span class="sxs-lookup"><span data-stu-id="55290-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="55290-132">Un enregistrement A interne qui résout le nom de domaine complet (FQDN) du pool frontal vers l’adresse IP du serveur principal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="55290-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55290-133">Connexion automatique au client</span><span class="sxs-lookup"><span data-stu-id="55290-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="55290-134">Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls. _ TCP. &lt;domaine&gt; sur le port 5061 qui correspond au nom de domaine complet du pool frontal qui authentifie et redirige les demandes de connexion du client.</span><span class="sxs-lookup"><span data-stu-id="55290-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="55290-135">Pour plus d’informations, voir <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">configuration DNS requise pour la connexion automatique au client dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="55290-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55290-136">Découverte du service Web de mise à jour d’appareil par des appareils de communications unifiées (UC)</span><span class="sxs-lookup"><span data-stu-id="55290-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="55290-137">Un enregistrement A interne du nom ucupdates-r2. &lt;Domaine&gt; SIP résolu sur l’adresse IP du pool frontal qui héberge le service Web de mise à jour de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="55290-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="55290-138">Dans le cas où un périphérique de communications unifiées est activé, mais qu’aucun utilisateur ne s’est connecté à l’appareil, l’enregistrement A permet à l’appareil de détecter le service Web de mise à jour des périphériques d’hébergement du pool frontal et d’obtenir les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="55290-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="55290-139">Dans le cas contraire, les appareils obtiennent ces informations en même temps que la première fois qu’un utilisateur se connecte.</span><span class="sxs-lookup"><span data-stu-id="55290-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="55290-140">Si vous avez un déploiement existant du service Web de mise à jour de l’appareil dans Lync Server 2010, vous avez déjà créé un enregistrement A interne avec le nom ucupdates. &lt;Domaine&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="55290-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="55290-141">Pour Microsoft Office Communications Server 2007 R2, vous devez créer un enregistrement DNS A supplémentaire portant le nom ucupdates-r2. &lt;Domaine&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="55290-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55290-142">Proxy inverse pour la prise en charge du trafic HTTP</span><span class="sxs-lookup"><span data-stu-id="55290-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="55290-143">Un enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs Web externe à l’adresse IP externe du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="55290-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="55290-144">Les clients et les appareils UC utilisent cet enregistrement pour se connecter au proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="55290-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="55290-145">Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-determine-dns-requirements.md">déterminer les exigences DNS pour Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="55290-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="55290-146">Le tableau suivant montre un exemple des enregistrements DNS requis pour le nom de domaine complet (FQDN) de la batterie de serveurs Web interne.</span><span class="sxs-lookup"><span data-stu-id="55290-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="55290-147">Exemples d’enregistrements DNS pour le FQDN d’une batterie de serveurs Web interne</span><span class="sxs-lookup"><span data-stu-id="55290-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55290-148">Nom de domaine complet (FQDN) du site Web interne</span><span class="sxs-lookup"><span data-stu-id="55290-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="55290-149">FQDN du pool</span><span class="sxs-lookup"><span data-stu-id="55290-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="55290-150">Enregistrement (s) DNS</span><span class="sxs-lookup"><span data-stu-id="55290-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55290-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="55290-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="55290-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="55290-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="55290-153">Enregistrement DNS A pour le ee-pool.contoso.com résolu vers l’adresse VIP de l’équilibrage de charge utilisé par les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="55290-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="55290-154">Enregistrement DNS A pour webcon.contoso.com résolu vers l’adresse VIP de l’équilibrage de charge utilisé par les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="55290-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55290-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="55290-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="55290-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="55290-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="55290-157">Enregistrement DNS A pour ee-pool.contoso.com résolu vers l’adresse IP virtuelle (VIP) de l’équilibrage de charge utilisé par les serveurs frontaux de l’entreprise Edition dans le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="55290-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="55290-158">Notez que si vous utilisez l’équilibrage de charge DNS sur ce pool, votre pool frontal et votre batterie de serveurs Web interne ne peuvent pas avoir le même nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="55290-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

