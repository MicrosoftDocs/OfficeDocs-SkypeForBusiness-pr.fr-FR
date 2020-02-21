---
title: 'Lync Server 2013 : équilibrage de la charge DNS'
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
ms.openlocfilehash: 47469a8b47273c077a96196b06b827ac13a0e336
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="77e8e-102">Équilibrage de la charge DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77e8e-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77e8e-103">_**Dernière modification de la rubrique :** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="77e8e-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="77e8e-104">Lync Server active l’équilibrage de charge DNS, une solution logicielle qui réduit considérablement la charge d’administration pour l’équilibrage de charge sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="77e8e-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="77e8e-105">L’équilibrage de charge DNS équilibre le trafic réseau propre à Lync Server, tel que le trafic SIP et le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="77e8e-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="77e8e-106">Si vous déployez l’équilibrage de la charge DNS, les frais d’administration de votre organisation pour les programmes d’équilibrage de la charge matérielle seront minimisés.</span><span class="sxs-lookup"><span data-stu-id="77e8e-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="77e8e-107">De plus, le travail ardu de dépannage qu’imposent les problèmes découlant d’une mauvaise configuration des programmes d’équilibrage de la charge pour le trafic SIP sera évité.</span><span class="sxs-lookup"><span data-stu-id="77e8e-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="77e8e-108">Vous pouvez aussi empêcher les connexions serveur afin de mettre les serveurs hors connexion.</span><span class="sxs-lookup"><span data-stu-id="77e8e-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="77e8e-109">L’équilibrage de la charge DNS permet également d’éviter que des problèmes liés aux programmes d’équilibrage de la charge matérielle n’aient une incidence sur des éléments du trafic SIP, notamment le routage de base des appels.</span><span class="sxs-lookup"><span data-stu-id="77e8e-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="77e8e-110">En optant pour l’équilibrage de la charge DNS, vous pouvez aussi acheter des programmes d’équilibrage de la charge matérielle moins chers que ceux proposés pour tous les types de trafic.</span><span class="sxs-lookup"><span data-stu-id="77e8e-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="77e8e-111">Vous devez utiliser des programmes d’équilibrage de charge qui ont passé des tests de compétences d’interopérabilité avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77e8e-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="77e8e-112">Pour plus d’informations sur les tests d’interopérabilité de l’équilibreur de charge, voir « partenaires d' [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)équilibrage de charge Lync Server 2010 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="77e8e-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="77e8e-113">L’équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools de directeurs et les pools de serveurs de médiation autonomes.</span><span class="sxs-lookup"><span data-stu-id="77e8e-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="77e8e-114">Équilibrage de la charge DNS dans les pools frontaux et les pools directeurs</span><span class="sxs-lookup"><span data-stu-id="77e8e-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="77e8e-p104">Vous pouvez désormais utiliser l’équilibrage de la charge DNS pour le trafic SIP dans les pools frontaux et les pools directeurs. Avec l’équilibrage de charge DNS déployé, vous devrez quand même toujours utiliser les programmes d’équilibrage de la charge matérielle pour ces pools, mais seulement pour le trafic HTTPS du client vers le serveur. Le programme d’équilibrage de la charge matérielle est utilisé pour le trafic HTTPS venant des clients sur les ports 443 et 80.</span><span class="sxs-lookup"><span data-stu-id="77e8e-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="77e8e-118">Bien que le recours à des programmes d’équilibrage de la charge matérielle soit toujours nécessaire pour ces pools, leur configuration et leur administration concernera avant tout le trafic HTTPS avec lequel les administrateurs des programmes d’équilibrage de la charge matérielle sont familiarisés.</span><span class="sxs-lookup"><span data-stu-id="77e8e-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="77e8e-119">Équilibrage de charge DNS et prise en charge d’anciens clients et serveurs</span><span class="sxs-lookup"><span data-stu-id="77e8e-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="77e8e-120">L’équilibrage de charge DNS prend en charge le basculement automatique uniquement pour les serveurs exécutant Lync Server 2013 ou Lync Server 2010, ainsi que pour les clients Lync 2013 et Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="77e8e-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="77e8e-121">Les versions antérieures des clients et d’Office Communications Server peuvent toujours se connecter aux pools exécutant l’équilibrage de charge DNS, mais si elles ne peuvent pas établir une connexion avec le premier serveur auquel l’équilibrage de charge DNS les renvoie, ils ne peuvent pas basculer vers un autre serveur du pool. .</span><span class="sxs-lookup"><span data-stu-id="77e8e-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="77e8e-122">En outre, si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum de Exchange 2010 SP1 pour obtenir la prise en charge de l’équilibrage de charge DNS de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77e8e-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="77e8e-123">Si vous utilisez une version antérieure d’Exchange, vos utilisateurs ne disposeront pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange :</span><span class="sxs-lookup"><span data-stu-id="77e8e-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="77e8e-124">Lecture de leur messagerie vocale Voix Entreprise sur leur téléphone</span><span class="sxs-lookup"><span data-stu-id="77e8e-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="77e8e-125">Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="77e8e-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="77e8e-126">Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.</span><span class="sxs-lookup"><span data-stu-id="77e8e-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="77e8e-127">Déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs</span><span class="sxs-lookup"><span data-stu-id="77e8e-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="77e8e-128">Le déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs vous oblige à effectuer quelques étapes supplémentaires avec les enregistrements de noms de domaine complets et les enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="77e8e-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="77e8e-129">Un pool qui utilise l’équilibrage de la charge DNS doit avoir deux noms de domaine complets : le nom de domaine complet standard du pool qui est utilisé par l’équilibrage de la charge DNS (par exemple, pool01.contoso.com) et qui est résolu en adresse IP pour chaque serveur dans le pool et un autre nom de domaine complet pour les services web du pool (par exemple, web01.contoso.com) qui est résolu en adresse IP virtuelle de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="77e8e-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="77e8e-130">Dans le générateur de topologies, si vous voulez déployer l’équilibrage de charge DNS pour un pool, vous devez activer la case à cocher Remplacer le nom de domaine complet du **pool des services Web internes** et taper le nom de domaine complet (FQDN) dans la page **spécifier les URL des services Web pour ce pool** .</span><span class="sxs-lookup"><span data-stu-id="77e8e-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="77e8e-p107">Pour prendre en charge le nom de domaine complet utilisé par l’équilibrage de la charge DNS, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, pool01.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Veillez à inclure uniquement les adresses IP des serveurs en cours de déploiement.</span><span class="sxs-lookup"><span data-stu-id="77e8e-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="77e8e-133">Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="77e8e-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="77e8e-134">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="77e8e-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="77e8e-135">Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="77e8e-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="77e8e-136">Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="77e8e-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="77e8e-137">Équilibrage de charge DNS dans les pools de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="77e8e-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="77e8e-p109">Vous pouvez déployer l’équilibrage de charge DNS dans les pools de serveurs Edge. Dans ce cas, vous devez tenir compte de certaines considérations.</span><span class="sxs-lookup"><span data-stu-id="77e8e-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="77e8e-140">L’utilisation de l’équilibrage de charge DNS sur vos serveurs Edge entraîne une perte des capacités de basculement dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="77e8e-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="77e8e-141">Fédération avec les organisations qui exécutent des versions d’Office Communications Server antérieures à Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="77e8e-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="77e8e-142">Échange de messages instantanés avec des utilisateurs de services de messagerie instantanée (IM\!) publics AOLand Yahoo, en plus des fournisseurs et des serveurs basés sur XMPP, tels que Google Talk.</span><span class="sxs-lookup"><span data-stu-id="77e8e-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="77e8e-143">Google Talk est actuellement le seul partenaire XMPP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="77e8e-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="77e8e-144">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="77e8e-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="77e8e-145">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="77e8e-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="77e8e-146">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="77e8e-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="77e8e-147">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="77e8e-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="77e8e-148">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="77e8e-148">has been announced.</span></span> <span data-ttu-id="77e8e-149">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77e8e-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="77e8e-150">Ces scénarios fonctionneront tant que tous les serveurs Edge dans le pool sont opérationnels, mais si un serveur Edge est indisponible, toutes les demandes envoyées à ces scénarios échoueront au lieu d’être routées vers un autre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="77e8e-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="77e8e-151">Si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum d’Exchange 2013 pour obtenir la prise en charge de l’équilibrage de charge DNS Lync Server sur Edge.</span><span class="sxs-lookup"><span data-stu-id="77e8e-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="77e8e-152">Si vous utilisez une version antérieure d’Exchange, vos utilisateurs distants ne disposeront pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange :</span><span class="sxs-lookup"><span data-stu-id="77e8e-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="77e8e-153">Lecture de leur messagerie vocale Voix Entreprise sur leur téléphone</span><span class="sxs-lookup"><span data-stu-id="77e8e-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="77e8e-154">Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="77e8e-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="77e8e-155">Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.</span><span class="sxs-lookup"><span data-stu-id="77e8e-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="77e8e-p112">Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.</span><span class="sxs-lookup"><span data-stu-id="77e8e-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="77e8e-158">Déploiement de l’équilibrage de charge DNS dans les pools de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="77e8e-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="77e8e-159">Pour déployer l’équilibrage de charge DNS sur l’interface externe de votre pool de serveurs Edge, vous avez besoin des entrées DNS suivantes :</span><span class="sxs-lookup"><span data-stu-id="77e8e-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="77e8e-160">Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="77e8e-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="77e8e-161">Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge d’accès (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="77e8e-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="77e8e-162">Pour le service Edge de conférence Web, vous avez besoin d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="77e8e-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="77e8e-163">Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge de conférence Web (par exemple, webconf.contoso.com) en adresse IP du service Edge de conférence Web sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="77e8e-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="77e8e-164">Pour le service Edge audio/vidéo, vous avez besoin d’une entrée pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="77e8e-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="77e8e-165">Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge audio/vidéo (par exemple, av.contoso.com) en adresse IP du service Edge A/V sur l’un des serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="77e8e-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="77e8e-166">Pour déployer l’équilibrage de la charge DNS sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A qui résout le nom de domaine complet interne du pool de serveurs Edge en adresse IP pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="77e8e-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="77e8e-167">Utilisation de l’équilibrage de charge DNS dans les pools de serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="77e8e-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="77e8e-p116">Vous pouvez utiliser l’équilibrage de charge DNS sur des pools de serveurs de médiation autonomes. Tout le trafic SIP et multimédia est équilibré par l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="77e8e-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="77e8e-170">Pour déployer l’équilibrage de la charge DNS sur un pool de serveurs de médiation, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, mediationpool1.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).</span><span class="sxs-lookup"><span data-stu-id="77e8e-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="77e8e-171">Blocage du trafic vers un serveur avec équilibrage de la charge DNS</span><span class="sxs-lookup"><span data-stu-id="77e8e-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="77e8e-172">Si vous utilisez l’équilibrage de la charge DNS et que vous avez besoin de bloquer le trafic sur un ordinateur spécifique, il ne suffit pas de supprimer les entrées d’adresses IP du nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="77e8e-172">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="77e8e-173">Vous devez également supprimer l’entrée DNS pour l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="77e8e-173">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="77e8e-174">Notez que pour le trafic de serveur à serveur, Lync Server 2013 utilise un équilibrage de charge prenant en charge la topologie.</span><span class="sxs-lookup"><span data-stu-id="77e8e-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="77e8e-175">Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs.</span><span class="sxs-lookup"><span data-stu-id="77e8e-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="77e8e-176">Pour empêcher un serveur de recevoir du trafic de serveur à serveur, vous devez supprimer le serveur de la topologie.</span><span class="sxs-lookup"><span data-stu-id="77e8e-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

