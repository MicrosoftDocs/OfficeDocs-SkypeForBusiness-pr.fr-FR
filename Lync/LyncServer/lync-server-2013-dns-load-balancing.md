---
title: 'Lync Server 2013 : équilibrage de charge DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="14bcd-102">Équilibrage de charge DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14bcd-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14bcd-103">_**Dernière modification de la rubrique :** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="14bcd-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="14bcd-104">Lync Server active l’équilibrage de charge DNS, une solution logicielle permettant de réduire considérablement la surcharge d’administration pour l’équilibrage de charge sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="14bcd-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="14bcd-105">L’équilibrage de charge DNS équilibre le trafic réseau unique vers Lync Server, comme le trafic SIP et le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="14bcd-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="14bcd-106">Si vous déployez l’équilibrage de charge DNS, la surcharge d’administration de votre organisation pour les équilibreurs de charge matérielle est réduite.</span><span class="sxs-lookup"><span data-stu-id="14bcd-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="14bcd-107">Par ailleurs, le dépannage complexe des problèmes liés à la configuration incompatibilité des équilibreurs de charge pour le trafic SIP sera éliminé.</span><span class="sxs-lookup"><span data-stu-id="14bcd-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="14bcd-108">Vous pouvez également empêcher les connexions au serveur pour pouvoir mettre en ligne des serveurs.</span><span class="sxs-lookup"><span data-stu-id="14bcd-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="14bcd-109">L’équilibrage de charge DNS vérifie également que les problèmes liés à l’équilibrage de charge matérielle n’affectent pas les éléments du trafic SIP tels que le routage des appels de base.</span><span class="sxs-lookup"><span data-stu-id="14bcd-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="14bcd-110">Si vous utilisez l’équilibrage de charge DNS, vous pouvez également être en mesure d’acheter des équilibreurs de charge matérielle économiques que si vous utilisiez les équilibreurs de charge matérielle pour tous les types de trafic.</span><span class="sxs-lookup"><span data-stu-id="14bcd-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="14bcd-111">Vous devez utiliser des équilibreurs de charge qui ont passé des tests de compétences d’interopérabilité avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14bcd-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="14bcd-112">Pour plus d’informations sur le test de l’interopérabilité de l’équilibrage de charge, voir « partenaires de [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)l’équilibrage de charge Lync Server 2010 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="14bcd-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="14bcd-113">Le service d’équilibrage de la charge DNS est pris en charge pour les pools front-end, les pools de serveurs Edge, les pools de directeurs et les pools de serveurs de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="14bcd-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="14bcd-114">Équilibrage de charge DNS pour les pools front-end et les pools de directeurs</span><span class="sxs-lookup"><span data-stu-id="14bcd-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="14bcd-115">Vous pouvez utiliser l’équilibrage de charge DNS pour le trafic SIP sur les listes frontales et les pools de Director.</span><span class="sxs-lookup"><span data-stu-id="14bcd-115">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools.</span></span> <span data-ttu-id="14bcd-116">Après le déploiement de l’équilibrage de charge DNS, vous devez également utiliser des équilibreurs de charge matérielle pour ces pools, mais uniquement pour le trafic HTTPs de client à serveur.</span><span class="sxs-lookup"><span data-stu-id="14bcd-116">With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic.</span></span> <span data-ttu-id="14bcd-117">L’équilibrage de charge matérielle est utilisé pour le trafic HTTPs des clients sur les ports 443 et 80.</span><span class="sxs-lookup"><span data-stu-id="14bcd-117">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="14bcd-118">Même si vous avez encore besoin d’équilibreurs de charge matérielle pour ces pools, leur configuration et leur administration s’adresseront essentiellement au trafic HTTPs, que les administrateurs des équilibreurs de charge matérielle sont habitués.</span><span class="sxs-lookup"><span data-stu-id="14bcd-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="14bcd-119">Équilibrage de charge DNS et prise en charge de clients et de serveurs plus anciens</span><span class="sxs-lookup"><span data-stu-id="14bcd-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="14bcd-120">L’équilibrage de charge DNS prend en charge le basculement automatique uniquement pour les serveurs exécutant Lync Server 2013 ou Lync Server 2010 ainsi que les clients Lync 2013 et Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="14bcd-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="14bcd-121">Les versions antérieures de clients et d’Office Communications Server peuvent toujours se connecter aux pools exécutant l’équilibrage de charge DNS, mais, si elles ne peuvent pas établir une connexion au premier serveur auquel l’équilibrage de charge DNS fait référence, elles ne peuvent pas basculer sur un autre serveur du pool. .</span><span class="sxs-lookup"><span data-stu-id="14bcd-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="14bcd-122">Par ailleurs, si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum de Exchange 2010 SP1 pour obtenir une prise en charge de l’équilibrage de charge DNS de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14bcd-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="14bcd-123">Si vous utilisez une version antérieure d’Exchange, vos utilisateurs ne disposent pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange :</span><span class="sxs-lookup"><span data-stu-id="14bcd-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="14bcd-124">Lecture de la messagerie vocale de votre entreprise sur son téléphone</span><span class="sxs-lookup"><span data-stu-id="14bcd-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="14bcd-125">Transfert d’appels à partir d’un standard automatique de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="14bcd-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="14bcd-126">Tous les autres scénarios Exchange UM fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="14bcd-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="14bcd-127">Déploiement de l’équilibrage de charge DNS pour les pools front-end et les pools de directeurs</span><span class="sxs-lookup"><span data-stu-id="14bcd-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="14bcd-128">Le déploiement de l’équilibrage de charge DNS pour les pools principaux et les pools de directeurs nécessite que vous effectuiez quelques étapes supplémentaires avec les noms de domaine complets et les enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="14bcd-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="14bcd-129">Un pool qui utilise l’équilibrage de charge DNS doit avoir deux noms de domaine complets (FQDN) du pool standard utilisés par l’équilibrage de charge DNS (par exemple, pool01.contoso.com), et est résolu sur l’IPs physique des serveurs du pool et un autre nom de domaine complet pour les services Web du pool (par exemple, web01.contoso.com), qui est résolue en adresse IP virtuelle du pool.</span><span class="sxs-lookup"><span data-stu-id="14bcd-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="14bcd-130">Dans le générateur de topologie, si vous voulez déployer l’équilibrage de charge DNS pour un pool, pour créer ce nom de domaine complet supplémentaire pour les services Web du pool, vous devez activer la case à cocher **ignorer le nom de domaine complet du pool de services Web internes** , puis taper le nom de domaine complet (FQDN) dans la page **spécifier les URL des services Web pour ce pool** .</span><span class="sxs-lookup"><span data-stu-id="14bcd-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="14bcd-131">Pour prendre en charge le FQDN utilisé par l’équilibrage de charge DNS, vous devez configurer le système DNS pour résoudre le nom de domaine complet (par exemple, pool01.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).</span><span class="sxs-lookup"><span data-stu-id="14bcd-131">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="14bcd-132">Vous ne devez inclure que les adresses IP des serveurs actuellement déployés.</span><span class="sxs-lookup"><span data-stu-id="14bcd-132">You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="14bcd-133">Si vous avez plusieurs pools front-end ou serveur frontal, le nom de domaine complet des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="14bcd-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="14bcd-134">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="14bcd-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="14bcd-135">Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="14bcd-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="14bcd-136">Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de réalisateur.</span><span class="sxs-lookup"><span data-stu-id="14bcd-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="14bcd-137">Équilibrage de charge DNS sur les pools de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="14bcd-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="14bcd-138">Vous pouvez déployer l’équilibrage de charge DNS sur les pools de serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="14bcd-138">You can deploy DNS load balancing on Edge Server pools.</span></span> <span data-ttu-id="14bcd-139">Dans le cas contraire, vous devez tenir compte de certaines considérations.</span><span class="sxs-lookup"><span data-stu-id="14bcd-139">If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="14bcd-140">L’utilisation de l’équilibrage de charge DNS sur votre serveur Edge entraîne une perte de fonctionnalité de basculement dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="14bcd-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="14bcd-141">Fédération avec des organisations qui utilisent des versions d’Office Communications Server précédées d’une version antérieure à Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="14bcd-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="14bcd-142">Échangez des messages instantanés avec des utilisateurs de services de messagerie instantanée publique\!AOLand Yahoo, en plus des fournisseurs et des serveurs utilisant la fonction de messagerie vocale, tels que Google Talk.</span><span class="sxs-lookup"><span data-stu-id="14bcd-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="14bcd-143">Pour le moment, Google Talk est le seul partenaire XMPP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="14bcd-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="14bcd-144">À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="14bcd-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="14bcd-145">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="14bcd-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="14bcd-146">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="14bcd-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="14bcd-147">Date de fin de vie du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="14bcd-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="14bcd-148">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="14bcd-148">has been announced.</span></span> <span data-ttu-id="14bcd-149">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="14bcd-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="14bcd-150">Ces scénarios fonctionneront tant que tous les serveurs Edge du pool seront opérationnels, mais si un serveur Edge n’est pas disponible, toutes les demandes de ces scénarios qui y sont envoyés échoueront au lieu d’être routés vers un autre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="14bcd-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="14bcd-151">Si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum d’Exchange 2013 pour obtenir une prise en charge de l’équilibrage de charge DNS de Lync Server sur Edge.</span><span class="sxs-lookup"><span data-stu-id="14bcd-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="14bcd-152">Si vous utilisez une version antérieure d’Exchange, vos utilisateurs distants ne disposent pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange :</span><span class="sxs-lookup"><span data-stu-id="14bcd-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="14bcd-153">Lecture de la messagerie vocale de votre entreprise sur son téléphone</span><span class="sxs-lookup"><span data-stu-id="14bcd-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="14bcd-154">Transfert d’appels à partir d’un standard automatique de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="14bcd-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="14bcd-155">Tous les autres scénarios Exchange UM fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="14bcd-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="14bcd-156">L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge.</span><span class="sxs-lookup"><span data-stu-id="14bcd-156">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="14bcd-157">Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.</span><span class="sxs-lookup"><span data-stu-id="14bcd-157">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="14bcd-158">Déploiement de l’équilibrage de charge DNS sur les pools de serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="14bcd-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="14bcd-159">Pour déployer l’équilibrage de charge DNS sur l’interface externe de votre pool de serveurs Edge, vous avez besoin des entrées DNS suivantes :</span><span class="sxs-lookup"><span data-stu-id="14bcd-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="14bcd-160">Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="14bcd-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="14bcd-161">Chaque entrée doit résoudre le nom de domaine complet du service Edge d’accès (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="14bcd-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="14bcd-162">Pour le service Edge de conférence Web, vous avez besoin d’une entrée pour chaque serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="14bcd-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="14bcd-163">Chaque entrée doit résoudre le nom de domaine complet (par exemple, webconf.contoso.com) de l’adresse IP du service Edge de conférence Web sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="14bcd-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="14bcd-164">Pour le service Edge audio/vidéo, vous avez besoin d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="14bcd-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="14bcd-165">Chaque entrée doit résoudre le nom de domaine complet (par exemple, av.contoso.com) de l’adresse IP du service Edge A/V sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="14bcd-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="14bcd-166">Pour déployer l’équilibrage de charge DNS sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A, qui résout le nom de domaine complet (FQDN) du pool de serveurs Edge, à l’adresse IP de chaque serveur du pool.</span><span class="sxs-lookup"><span data-stu-id="14bcd-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="14bcd-167">Utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="14bcd-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="14bcd-168">Vous pouvez utiliser l’équilibrage de charge DNS sur les pools de serveurs de médiation autonomes.</span><span class="sxs-lookup"><span data-stu-id="14bcd-168">You can use DNS load balancing on stand-alone Mediation Server pools.</span></span> <span data-ttu-id="14bcd-169">Le trafic SIP et de média est équilibré par l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="14bcd-169">All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="14bcd-170">Pour déployer l’équilibrage de charge DNS sur un pool de serveurs de médiation, vous devez configurer le DNS pour résoudre le nom de domaine complet (par exemple, mediationpool1.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).</span><span class="sxs-lookup"><span data-stu-id="14bcd-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="14bcd-171">Blocage du trafic vers un serveur avec l’équilibrage de charge DNS</span><span class="sxs-lookup"><span data-stu-id="14bcd-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="14bcd-p117">Si vous utilisez l’équilibrage de charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également l’entrée DNS associée à l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="14bcd-p117">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="14bcd-174">Notez que pour le trafic de serveur à serveur, Lync Server 2013 utilise l’équilibrage de charge prenant en charge la topologie.</span><span class="sxs-lookup"><span data-stu-id="14bcd-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="14bcd-175">Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs.</span><span class="sxs-lookup"><span data-stu-id="14bcd-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="14bcd-176">Pour empêcher un serveur de recevoir du trafic de serveur à serveur, vous devez supprimer le serveur de la topologie.</span><span class="sxs-lookup"><span data-stu-id="14bcd-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

