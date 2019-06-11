---
title: 'Lync Server 2013 : Scénarios d’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e4f7410d7038971c6ddefe1af1c7b3ecd97ab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="3e5de-102">Scénarios d’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e5de-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e5de-103">_**Dernière modification de la rubrique:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3e5de-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3e5de-104">Si vous fournissez un accès utilisateur externe pour Lync Server 2013, vous devez déployer au moins un serveur Edge et un proxy inverse dans votre réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="3e5de-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="3e5de-105">Le cas échéant, vous pouvez déployer un réalisateur ou un pool de réalisateurs dans votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="3e5de-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="3e5de-106">Si vous avez besoin d’une capacité supérieure à celle d’un serveur Edge unique, ou si vous avez besoin d’une haute disponibilité pour le déploiement de votre serveur Edge, vous pouvez configurer l’équilibrage de charge et déployer plusieurs serveurs Edge dans un pool équilibré.</span><span class="sxs-lookup"><span data-stu-id="3e5de-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="3e5de-107">Si votre organisation possède plusieurs centres de données, vous pouvez utiliser des déploiements de serveur Edge ou de pool Edge à plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="3e5de-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="3e5de-108">Toutefois, vous ne pouvez désigner qu’un des déploiements de serveur Edge en tant qu’itinéraire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="3e5de-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="3e5de-109">Cette section définit les scénarios pour les déploiements de serveurs de périphérie et établit une correspondance entre les sections de planification et les scénarios possibles.</span><span class="sxs-lookup"><span data-stu-id="3e5de-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="3e5de-110">Par exemple, si votre déploiement a besoin d’une haute disponibilité, de la Fédération avec les contacts de présence et de présence (XMPP) et de mobilité Lync, vous devez sélectionner les entrées correspondantes dans le tableau suivant qui satisfont les exigences et utiliser le sections de planification référencées permettant de définir votre déploiement, comme illustré dans l’organigramme suivant.</span><span class="sxs-lookup"><span data-stu-id="3e5de-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="3e5de-111">**Processus de sélection de scénario de déploiement de serveur Edge**</span><span class="sxs-lookup"><span data-stu-id="3e5de-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="3e5de-112">![Exemple de diagramme de flux de déploiement] (images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemple de diagramme de flux de déploiement")</span><span class="sxs-lookup"><span data-stu-id="3e5de-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="3e5de-113">En utilisant ce processus, vous pouvez planifier la configuration de toutes les fonctionnalités potentielles que vous envisagez de déployer pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3e5de-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="3e5de-114">Toutefois, vous pouvez ajouter des services de Fédération et de mobilité après avoir déployé le serveur de périphérie et avoir confirmé l’opération correcte avant d’ajouter d’autres fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="3e5de-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="3e5de-115">Le processus d’ajout de fonctionnalités à un déploiement de serveur Edge existant est abordé dans la section déploiement.</span><span class="sxs-lookup"><span data-stu-id="3e5de-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="3e5de-116">Pour plus d’informations sur le déploiement, reportez-vous à la section déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en incluant la planification de ces fonctionnalités lors du processus de planification initial. ce qui vous permet d’acquérir les certificats et de configurer les exigences DNS et de port/protocole à l’avance.</span><span class="sxs-lookup"><span data-stu-id="3e5de-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="3e5de-117">Si vous envisagez d’installer les serveurs Edge et le proxy inverse, puis ajoutez des fonctionnalités plus tard (par exemple, la Fédération et la mobilité), déterminez les certificats dont vous aurez besoin pour tous les services après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="3e5de-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="3e5de-118">En planifiant et en acquérant les certificats pour toutes les fonctionnalités à l’avance, déployées ou non, vous vous évite d’avoir à commander de nouveaux certificats pour répondre aux exigences de Fédération (c’est-à-dire, sur les serveurs de périphérie) ou en tant que proxy inverse (en ce qui concerne la mobilité. services).</span><span class="sxs-lookup"><span data-stu-id="3e5de-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3e5de-119">Tous les services Edge s’exécutent sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="3e5de-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="3e5de-120">Les services ne peuvent pas être partagés entre deux serveurs d’arête différents.</span><span class="sxs-lookup"><span data-stu-id="3e5de-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="3e5de-121">Si vous déployez un pool de périphérie pour une extensibilité, tous les services Edge sont déployés sur chaque serveur Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="3e5de-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="3e5de-122">XMPP Federation, Office Communications Server et Lync Server Federation, la connectivité de messagerie instantanée publique et la mobilité du client sont des services supplémentaires qui peuvent être déployés après le déploiement de votre premier serveur Edge ou pool d’arêtes.</span><span class="sxs-lookup"><span data-stu-id="3e5de-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="3e5de-123">Les services de mobilité sont une fonctionnalité qui utilise le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="3e5de-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="3e5de-124">L’installation des services de mobilité n’ajoute pas de fonctionnalités à vos serveurs Edge, mais nécessite une reconfiguration de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="3e5de-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="3e5de-125">La colonne objectif de l' <STRONG>installation</STRONG> qui répertorie ces fonctionnalités fournit des recommandations en matière de planification dans la colonne associée sous la <STRONG>section planification du serveur de périphérie</STRONG> pour planifier les fonctionnalités en cours de déploiement lorsque les serveurs Edge sont installés et configurés.</span><span class="sxs-lookup"><span data-stu-id="3e5de-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="3e5de-126">Identification et mappage de vos objectifs de déploiement</span><span class="sxs-lookup"><span data-stu-id="3e5de-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e5de-127">Objectif de l’installation</span><span class="sxs-lookup"><span data-stu-id="3e5de-127">Installation goal</span></span></th>
<th><span data-ttu-id="3e5de-128">Documentation sur la planification du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3e5de-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e5de-129">Vous avez décidé qu’un seul serveur est suffisant pour les services Edge dans votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="3e5de-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="3e5de-130">Vous envisagez également d’utiliser des adresses IP privées pour les interfaces externes du serveur Edge avec tar sur Internet.</span><span class="sxs-lookup"><span data-stu-id="3e5de-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="3e5de-131">Utilisez cette section planification si vous déployez un serveur Edge unique dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="3e5de-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="3e5de-132">Vous déploierez un serveur Edge avec des adresses IP privées affectées au serveur Edge et utiliserez tar pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="3e5de-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="3e5de-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e5de-134">Vous avez décidé qu’un seul serveur est suffisant pour les services Edge dans votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="3e5de-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="3e5de-135">Vous envisagez également d’utiliser des adresses IP publiques pour les interfaces externes du serveur Edge vers Internet.</span><span class="sxs-lookup"><span data-stu-id="3e5de-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="3e5de-136">Utilisez cette section planification si vous déployez un serveur Edge unique dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="3e5de-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="3e5de-137">Vous déploierez un serveur Edge avec des adresses IP publiques affectées au serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="3e5de-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="3e5de-138">Au lieu de tar, vous utiliserez le routage dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="3e5de-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="3e5de-139">L’adresse IP publique réelle du serveur Edge est mise à la disposition des connexions d’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="3e5de-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="3e5de-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e5de-141">Vous avez décidé qu’il est important de disposer d’une haute disponibilité des services Edge pour vos utilisateurs et de déployer deux ou plusieurs serveurs Edge dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="3e5de-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="3e5de-142">Vous envisagez également d’utiliser des adresses IP privées pour les interfaces externes du serveur Edge avec tar sur Internet.</span><span class="sxs-lookup"><span data-stu-id="3e5de-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="3e5de-143">Utilisez cette section planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="3e5de-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="3e5de-144">Vous déploierez les serveurs Edge avec des adresses IP privées affectées au serveur Edge, en utilisant l’équilibrage de charge DNS pour répartir la communication entre le pool.</span><span class="sxs-lookup"><span data-stu-id="3e5de-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="3e5de-145">Vous utiliserez tar pour fournir les adresses IP publiques pour les utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="3e5de-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="3e5de-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e5de-147">Vous avez décidé qu’il est important de disposer d’une haute disponibilité des services Edge pour vos utilisateurs et de déployer deux ou plusieurs serveurs Edge dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="3e5de-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="3e5de-148">Vous envisagez également d’utiliser des adresses IP publiques pour les interfaces externes du serveur Edge vers Internet.</span><span class="sxs-lookup"><span data-stu-id="3e5de-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="3e5de-149">Utilisez cette section planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="3e5de-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="3e5de-150">Vous déploierez les serveurs Edge possédant des adresses IP publiques affectées au serveur Edge, à l’aide de l’équilibrage de charge DNS pour répartir la communication entre le pool.</span><span class="sxs-lookup"><span data-stu-id="3e5de-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="3e5de-151">Au lieu de la traduction d’adresses réseau (NAT), vous allez utiliser le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="3e5de-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="3e5de-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e5de-153">Vous avez décidé qu’il est important de disposer d’une haute disponibilité des services Edge pour vos utilisateurs et que vous déploierez deux ou plusieurs serveurs Edge dans ce pool à l’aide d’un dispositif d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="3e5de-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="3e5de-154">Utilisez cette section planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="3e5de-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="3e5de-155">Vous déploierez les serveurs Edge avec des adresses IP publiques affectées au serveur Edge, en utilisant des équilibreurs de charge matérielle pour distribuer la communication entre le pool.</span><span class="sxs-lookup"><span data-stu-id="3e5de-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="3e5de-156">Au lieu de la traduction d’adresses réseau (NAT), vous allez utiliser le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="3e5de-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="3e5de-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e5de-158">Les scénarios de Fédération vous permettent de planifier la fonctionnalité qui permettra aux utilisateurs de communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="3e5de-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5de-159">Fédération Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e5de-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="3e5de-160">Fédération Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="3e5de-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="3e5de-161">Solution PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="3e5de-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="3e5de-162">Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="3e5de-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e5de-163">Planification des scénarios de Fédération</span><span class="sxs-lookup"><span data-stu-id="3e5de-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5de-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planification de Lync Server 2013 et de la Fédération Office Communications Server</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="3e5de-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="3e5de-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planification de la Fédération des protocoles de messagerie et de présence extensibles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e5de-167">Les services de mobilité sont proposés par le biais du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="3e5de-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="3e5de-168">Les services qui autorisent la mobilité pour les utilisateurs externes sont déployés sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="3e5de-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="3e5de-169">Pour activer les services de mobilité pour les utilisateurs externes, vous pouvez créer ou modifier des règles de publication existantes sur le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="3e5de-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="3e5de-170"><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e5de-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="3e5de-171">Dans les sections de scénarios suivantes, vous trouverez des architectures de référence, des exemples de définitions de port/protocole et de certificat.</span><span class="sxs-lookup"><span data-stu-id="3e5de-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="3e5de-172">Vous trouverez également des diagrammes pour les définitions DNS, port/protocole et certificats.</span><span class="sxs-lookup"><span data-stu-id="3e5de-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="3e5de-173">Les diagrammes vous fournissent un modèle qui vous permettra de remplir et de distribuer d’autres équipes (par exemple, l’équipe réseau de votre organisation, l’équipe d’infrastructure à clé publique et l’équipe de déploiement du serveur).</span><span class="sxs-lookup"><span data-stu-id="3e5de-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="3e5de-174">L’objectif des diagrammes est d’améliorer la communication et de garantir le succès lors de la communication des éléments de configuration de serveur Edge requis aux personnes qui effectuent le fonctionnement de la configuration réelle.</span><span class="sxs-lookup"><span data-stu-id="3e5de-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="3e5de-175">Nous vous recommandons d’utiliser les diagrammes et les architectures de référence associées pour planifier votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="3e5de-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

