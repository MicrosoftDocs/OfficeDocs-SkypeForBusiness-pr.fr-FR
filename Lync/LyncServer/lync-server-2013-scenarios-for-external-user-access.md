---
title: 'Lync Server 2013 : scénarios pour l’accès des utilisateurs externes'
description: 'Lync Server 2013 : scénarios pour l’accès des utilisateurs externes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b212d371d5a87470fc3d849f185bb5c8659ce05
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547640"
---
# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="eabff-103">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eabff-103">Scenarios for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eabff-104">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="eabff-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="eabff-105">L’accès des utilisateurs externes à Lync Server 2013 nécessite le déploiement d’au moins un serveur Edge et d’un proxy inverse dans votre réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="eabff-105">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="eabff-106">Vous pouvez également déployer un directeur ou un pool directeur dans votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="eabff-106">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="eabff-107">Si vous avez besoin d’une capacité supérieure à celle d’un serveur Edge unique, ou si vous avez besoin d’une haute disponibilité pour votre déploiement de serveur Edge, vous pouvez configurer l’équilibrage de charge et déployer plusieurs serveurs Edge dans un pool à charge équilibrée.</span><span class="sxs-lookup"><span data-stu-id="eabff-107">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="eabff-108">Si votre organisation dispose de plusieurs centres de données, vous pouvez disposer de déploiements de serveur Edge ou de pool Edge à plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="eabff-108">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="eabff-109">Toutefois, un seul des déploiements de serveur Edge peut être désigné comme itinéraire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="eabff-109">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="eabff-110">Cette section définit les scénarios pour les déploiements de serveur Edge et mappe les sections de planification aux scénarios possibles.</span><span class="sxs-lookup"><span data-stu-id="eabff-110">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="eabff-111">Par exemple, si votre déploiement requiert une haute disponibilité, la Fédération avec les contacts XMPP (extensible Messaging and Presence) et Lync Mobility, vous devez sélectionner les entrées correspondantes dans le tableau suivant qui satisferait ces exigences et utiliser les sections de planification référencées pour définir votre déploiement, comme illustré dans le diagramme suivant.</span><span class="sxs-lookup"><span data-stu-id="eabff-111">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="eabff-112">**Processus de sélection d’un scénario de déploiement de serveur Edge**</span><span class="sxs-lookup"><span data-stu-id="eabff-112">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="eabff-113">![Exemple d’organigramme de déploiement](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemple d’organigramme de déploiement")</span><span class="sxs-lookup"><span data-stu-id="eabff-113">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="eabff-114">Ce processus vous permet de planifier et de documenter la configuration de toutes les fonctionnalités potentielles que vous envisagez de déployer pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="eabff-114">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="eabff-115">Toutefois, vous pouvez ajouter des services de Fédération et de mobilité après avoir déployé le serveur Edge et confirmé l’opération correcte avant d’ajouter d’autres fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="eabff-115">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="eabff-116">Le processus d’ajout de fonctionnalités à un déploiement de serveur Edge existant est abordé dans la section relative au déploiement.</span><span class="sxs-lookup"><span data-stu-id="eabff-116">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="eabff-117">Pour plus d’informations sur le déploiement, reportez-vous à la rubrique déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en incluant la planification de ces fonctionnalités lors du processus de planification initial, vous pouvez vous préparer aux exigences de DNS, de pare-feu et de certificat pour les fonctionnalités ajoutées, ce qui vous permet d’acquérir les certificats et de configurer les exigences DNS et de ports</span><span class="sxs-lookup"><span data-stu-id="eabff-117">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="eabff-118">Si vous envisagez d’installer les serveurs Edge et le proxy inverse, puis ajoutez des fonctionnalités ultérieurement (par exemple, la Fédération et la mobilité), déterminez les certificats dont vous aurez besoin pour tous les services après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="eabff-118">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="eabff-119">La planification et l’acquisition des certificats pour toutes les fonctionnalités à l’avance, initialement déployées ou non, vous évitent de devoir commander de nouveaux certificats afin de satisfaire aux exigences de la Fédération (c’est-à-dire sur les serveurs Edge) ou au proxy inverse (pour les services de mobilité).</span><span class="sxs-lookup"><span data-stu-id="eabff-119">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="eabff-120">Tous les services Edge s’exécutent sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="eabff-120">All edge services run on each Edge Server.</span></span> <span data-ttu-id="eabff-121">Les services ne peuvent pas être fractionnés entre deux serveurs Edge différents.</span><span class="sxs-lookup"><span data-stu-id="eabff-121">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="eabff-122">Si vous déployez un pool de serveurs Edge pour l’évolutivité, tous les services Edge sont déployés sur chaque serveur Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="eabff-122">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="eabff-123">Fédération XMPP, Office Communications Server et Fédération Lync Server, la connectivité PIC et la mobilité des clients sont des services supplémentaires qui peuvent être déployés après le déploiement de votre premier serveur Edge ou pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="eabff-123">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="eabff-124">Les services de mobilité constituent une fonctionnalité qui utilise le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="eabff-124">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="eabff-125">L’installation des services de mobilité n’ajoute pas de fonctionnalités à vos serveurs Edge, mais nécessite une reconfiguration de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="eabff-125">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="eabff-126">La colonne d' <STRONG>objectif d’installation</STRONG> qui répertorie ces fonctionnalités fournit des instructions de planification dans la colonne associée sous la <STRONG>section planification du serveur Edge ou des sections</STRONG> permettant de planifier simultanément ces fonctionnalités à déployer lorsque les serveurs Edge sont installés et configurés.</span><span class="sxs-lookup"><span data-stu-id="eabff-126">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="eabff-127">Identification et mise en correspondance de vos objectifs de déploiement</span><span class="sxs-lookup"><span data-stu-id="eabff-127">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eabff-128">Objectif de l’installation</span><span class="sxs-lookup"><span data-stu-id="eabff-128">Installation goal</span></span></th>
<th><span data-ttu-id="eabff-129">Documentation de planification de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="eabff-129">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eabff-p107">Vous considérez qu’un seul serveur suffit pour les services Edge services de votre infrastructure. Vous avez également l’intention d’utiliser des adresses IP privées pour les interfaces externes de serveur Edge utilisant la traduction d’adresses réseau (NAT) sur Internet.</span><span class="sxs-lookup"><span data-stu-id="eabff-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="eabff-132">Utilisez cette section de planification si vous déployez un serveur Edge unique dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="eabff-132">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="eabff-133">Vous allez déployer un serveur Edge avec des adresses IP privées affectées au serveur Edge et utilisera le protocole NAT pour fournir les adresses IP publiques pour les utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="eabff-133">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="eabff-134"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Serveur Edge consolidé unique avec des adresses IP privées et une interface NAT dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eabff-134"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eabff-p109">Vous considérez qu’un seul serveur suffit pour les services Edge services de votre infrastructure. Vous avez également l’intention d’utiliser des adresses IP publiques pour les interfaces externes de serveur sur Internet.</span><span class="sxs-lookup"><span data-stu-id="eabff-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="eabff-137">Utilisez cette section de planification si vous déployez un serveur Edge unique dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="eabff-137">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="eabff-138">Vous allez déployer un serveur Edge avec des adresses IP publiques affectées au serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="eabff-138">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="eabff-139">À la place de NAT, vous utiliserez le routage dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="eabff-139">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="eabff-140">L’adresse IP publique réelle du serveur Edge est disponible pour les connexions d’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="eabff-140">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="eabff-141"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eabff-141"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eabff-p111">Vous considérez que la haute disponibilité des services Edge est importante pour les utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool. Vous avez également l’intention d’utiliser des adresses IP privées pour les interfaces externes de serveur Edge utilisant NAT sur Internet.</span><span class="sxs-lookup"><span data-stu-id="eabff-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="eabff-144">Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="eabff-144">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="eabff-145">Vous allez déployer les serveurs Edge avec des adresses IP privées affectées au serveur Edge, à l’aide de l’équilibrage de charge DNS pour distribuer la communication dans le pool.</span><span class="sxs-lookup"><span data-stu-id="eabff-145">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="eabff-146">Vous utiliserez NAT pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="eabff-146">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="eabff-147"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eabff-147"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eabff-148">Vous considérez que la haute disponibilité des services Edge est importante pour les utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="eabff-148">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="eabff-149">Vous avez également l’intention d’utiliser des adresses IP publiques pour les interfaces externes du serveur Edge sur Internet.</span><span class="sxs-lookup"><span data-stu-id="eabff-149">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="eabff-150">Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="eabff-150">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="eabff-151">Vous allez déployer les serveurs Edge avec des adresses IP publiques affectées au serveur Edge, à l’aide de l’équilibrage de charge DNS pour distribuer la communication dans le pool.</span><span class="sxs-lookup"><span data-stu-id="eabff-151">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="eabff-152">Au lieu d’utiliser NAT, vous utiliserez le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="eabff-152">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="eabff-153"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eabff-153"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eabff-154">Vous avez décidé que la haute disponibilité des services Edge est importante pour vos utilisateurs et vous allez déployer au moins deux serveurs Edge dans ce pool à l’aide d’un programme d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="eabff-154">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="eabff-155">Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="eabff-155">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="eabff-156">Vous allez déployer les serveurs Edge avec des adresses IP publiques affectées au serveur Edge, en utilisant des programmes d’équilibrage de la charge matérielle pour distribuer la communication dans le pool.</span><span class="sxs-lookup"><span data-stu-id="eabff-156">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="eabff-157">Au lieu d’utiliser NAT, vous utiliserez le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="eabff-157">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="eabff-158"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eabff-158"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eabff-159">Les scénarios de fédération vous permettent de planifier la fonctionnalité qui étendra les types de partenaires avec lesquels vos utilisateurs peuvent communiquer.</span><span class="sxs-lookup"><span data-stu-id="eabff-159">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="eabff-160">Fédération Lync Server</span><span class="sxs-lookup"><span data-stu-id="eabff-160">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="eabff-161">Fédération Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="eabff-161">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="eabff-162">Solution PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="eabff-162">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="eabff-163">Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="eabff-163">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="eabff-164">Planification de scénarios de fédération</span><span class="sxs-lookup"><span data-stu-id="eabff-164">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="eabff-165"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planification de la Fédération entre Lync Server 2013 et Office Communications Server</a></span><span class="sxs-lookup"><span data-stu-id="eabff-165"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="eabff-166"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eabff-166"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="eabff-167"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planification de la Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eabff-167"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eabff-168">Les services de mobilité sont fournis via le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="eabff-168">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="eabff-169">Les services qui permettent la mobilité pour les utilisateurs externes sont déployés sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="eabff-169">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="eabff-170">Vous créez ou modifiez des règles de publication existantes sur le proxy inverse afin d’activer les services de mobilité pour les utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="eabff-170">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="eabff-171"><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eabff-171"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="eabff-172">Dans les scénarios suivants, les sections constituent des architectures de référence, des exemples de DNS, des définitions de ports/protocoles et des exigences en matière de certificat.</span><span class="sxs-lookup"><span data-stu-id="eabff-172">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="eabff-173">Elles contiennent également des diagrammes pour votre DNS, des définitions de port/protocole et des besoins en termes de certificat.</span><span class="sxs-lookup"><span data-stu-id="eabff-173">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="eabff-174">Ces diagrammes serviront de modèles que vous pourrez remplir et diffuser à d’autres équipes (par exemple, aux équipes chargées du réseau, de l’infrastructure à clé publique et du déploiement de serveur de votre organisation).</span><span class="sxs-lookup"><span data-stu-id="eabff-174">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="eabff-175">L’objectif des diagrammes est d’améliorer la communication et de garantir la réussite de la communication des éléments de configuration de serveur Edge requis aux personnes qui effectueront le travail de configuration proprement dit.</span><span class="sxs-lookup"><span data-stu-id="eabff-175">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="eabff-176">Nous vous recommandons d’utiliser les diagrammes et les architectures de référence associées pour planifier votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="eabff-176">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

