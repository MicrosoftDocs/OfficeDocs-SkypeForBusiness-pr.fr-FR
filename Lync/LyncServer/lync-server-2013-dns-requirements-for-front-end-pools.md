---
title: 'Lync Server 2013 : configuration DNS requise pour les pools frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18c5b7d16cf5bb7fe13c68a025e9033899c62c4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="c5274-102">Configuration DNS requise pour les pools frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5274-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5274-103">_**Dernière modification de la rubrique :** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="c5274-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="c5274-104">Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="c5274-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="c5274-105">Enregistrements DNS requis pour les pools frontaux</span><span class="sxs-lookup"><span data-stu-id="c5274-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="c5274-106">Le tableau suivant spécifie les exigences DNS pour un déploiement de pool frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5274-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="c5274-107">Composants DNS requis pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="c5274-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5274-108">Scénario de déploiement</span><span class="sxs-lookup"><span data-stu-id="c5274-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="c5274-109">Enregistrement DNS requis</span><span class="sxs-lookup"><span data-stu-id="c5274-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5274-110">Un pool frontal avec plusieurs serveurs frontaux et un programme d’équilibrage de la charge matérielle (que l’équilibrage de la charge DNS soit également déployé dans ce pool ou non).</span><span class="sxs-lookup"><span data-stu-id="c5274-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="c5274-111">Quand vous utilisez l’équilibrage de charge DNS et un équilibreur de la charge matérielle, vous avez besoin d’enregistrements Hôte (A).</span><span class="sxs-lookup"><span data-stu-id="c5274-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="c5274-112">Créez un enregistrement A interne qui est résolu en nom de domaine complet (FQDN) du pool de serveur frontal pour l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="c5274-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="c5274-113">Créez un enregistrement (A) hôte interne pour les services web internes vers l’adresse IP virtuelle (VIP) de l’équilibreur de charge.</span><span class="sxs-lookup"><span data-stu-id="c5274-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="c5274-114">Vous devez utiliser le nom des services Web internes comme défini dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c5274-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="c5274-115">Par exemple, si vous utilisez l’équilibrage de charge DNS et l’équilibrage de la charge matérielle, vous devez avoir un enregistrement A pour chaque serveur frontal dans un pool pour l’équilibrage de charge DNS et un enregistrement A pour les services Web internes pointant vers l’adresse IP virtuelle de l’équilibreur de charge matérielle. :</span><span class="sxs-lookup"><span data-stu-id="c5274-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5274-116">Équilibrage de charge DNS :   Pool01.contoso.net   Adresse IP du pool   10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="c5274-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="c5274-117">Chaque serveur frontal aura également un enregistrement A distinct :</span><span class="sxs-lookup"><span data-stu-id="c5274-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="c5274-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="c5274-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="c5274-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="c5274-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="c5274-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="c5274-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="c5274-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="c5274-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="c5274-122">Équilibrage de la charge matérielle :   WebInternal.contoso.net   Address IP de HLB VIP   192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="c5274-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="c5274-p102">Tout le trafic à l’exception du trafic HTTP/HTTPS utilisera l’enregistrement Pool01.contoso.net. Le trafic HTTP/HTTPS utilisera l’adresse des services web interne 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="c5274-p102">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record. HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5274-125">Un pool frontal avec déploiement de l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="c5274-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="c5274-p103">Un ensemble d’enregistrements A internes qui associent le nom de domaine complet du pool à l’adresse IP de chaque serveur au sein du pool. Il doit y avoir un enregistrement A pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="c5274-p103">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool. There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5274-128">Un pool frontal avec déploiement de l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="c5274-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="c5274-129">Un ensemble d’enregistrements A internes qui associent le nom de domaine complet à l’adresse IP de chaque serveur au sein du pool.</span><span class="sxs-lookup"><span data-stu-id="c5274-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="c5274-130">Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-dns-load-balancing.md">DNS Load Balancing in Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c5274-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5274-131">Un pool frontal avec un seul serveur frontal et une base de données principale dédiée, mais aucun équilibrage de charge.</span><span class="sxs-lookup"><span data-stu-id="c5274-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="c5274-132">Un enregistrement A interne associant le nom de domaine complet du pool frontal à l’adresse IP du serveur frontal Enterprise Edition unique.</span><span class="sxs-lookup"><span data-stu-id="c5274-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5274-133">Ouverture de session client automatique</span><span class="sxs-lookup"><span data-stu-id="c5274-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="c5274-134">Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls. _tcp. &lt;domaine&gt; sur le port 5061 qui mappe sur le nom de domaine complet du pool frontal qui authentifie et redirige les demandes client de connexion.</span><span class="sxs-lookup"><span data-stu-id="c5274-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="c5274-135">Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS Requirements for Automatic client Sign-in dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c5274-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5274-136">Détection du service web de mise à jour des périphériques par les périphériques de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="c5274-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="c5274-137">Un enregistrement A interne portant le nom ucupdates-r2. &lt;Domaine&gt; SIP qui est résolu en adresse IP du pool frontal qui héberge le service Web de mise à jour des périphériques.</span><span class="sxs-lookup"><span data-stu-id="c5274-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="c5274-138">Dans le cas où un périphérique de communications unifiées est activé, mais qu’un utilisateur ne s’y est jamais connecté, l’enregistrement A permet au périphérique de détecter le pool frontal hébergeant le service de mise à jour des périphériques et d’obtenir des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="c5274-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="c5274-139">Les périphériques peuvent autrement se procurer ces informations via une mise en service intrabande la première fois qu’un utilisateur se connecte.</span><span class="sxs-lookup"><span data-stu-id="c5274-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="c5274-140">Si vous disposez d’un déploiement existant du service Web de mise à jour des périphériques dans Lync Server 2010, vous avez déjà créé un enregistrement A interne avec le nom ucupdates. &lt;Domaine&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="c5274-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="c5274-141">Pour Microsoft Office Communications Server 2007 R2, vous devez créer un enregistrement DNS A supplémentaire avec le nom ucupdates-r2. &lt;Domaine&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="c5274-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5274-142">Proxy inverse de prise en charge du trafic HTTP</span><span class="sxs-lookup"><span data-stu-id="c5274-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="c5274-143">Enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs web externes en adresse IP externe du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="c5274-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="c5274-144">Les clients et les périphériques de communications unifiées utilisent cet enregistrement pour se connecter au proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="c5274-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="c5274-145">Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c5274-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c5274-146">Le tableau qui suit montre un exemple des enregistrements DNS requis pour le nom de domaine complet de la batterie de serveurs web internes.</span><span class="sxs-lookup"><span data-stu-id="c5274-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="c5274-147">Exemples d’enregistrements DNS requis pour le nom de domaine complet de la batterie de serveurs web internes</span><span class="sxs-lookup"><span data-stu-id="c5274-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5274-148">Nom de domaine complet de la batterie de serveurs web internes</span><span class="sxs-lookup"><span data-stu-id="c5274-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="c5274-149">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="c5274-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="c5274-150">Enregistrement(s) DNS A</span><span class="sxs-lookup"><span data-stu-id="c5274-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5274-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5274-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5274-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5274-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5274-153">Enregistrement DNS A pour le nom ee-pool.contoso.com associé à l’adresse IP virtuelle du programme d’équilibrage de charge utilisé par les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="c5274-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="c5274-154">Enregistrement DNS A pour le nom webcon.contoso.com associé à l’adresse IP virtuelle du programme d’équilibrage de charge utilisé par les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="c5274-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5274-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5274-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5274-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5274-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5274-157">Enregistrement DNS A pour le nom ee-pool.contoso.com associé à l’adresse IP virtuelle du programme d’équilibrage de charge utilisé par les serveurs frontaux Enterprise Edition du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c5274-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="c5274-158">Notez que si vous avez recours à l’équilibrage de la charge DNS dans ce pool, votre pool frontal et votre batterie de serveurs web internes ne peuvent pas avoir le même nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="c5274-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

