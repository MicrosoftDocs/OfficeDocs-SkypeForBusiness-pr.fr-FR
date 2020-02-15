---
title: 'Lync Server 2013 : scénarios pour l’accès des utilisateurs externes'
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
ms.openlocfilehash: bd560105303db5d09656c36620c9e8435feed86f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="5e5ad-102">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e5ad-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e5ad-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5e5ad-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="5e5ad-104">L’accès des utilisateurs externes à Lync Server 2013 nécessite le déploiement d’au moins un serveur Edge et d’un proxy inverse dans votre réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="5e5ad-105">Vous pouvez également déployer un directeur ou un pool directeur dans votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="5e5ad-106">Si vous avez besoin d’une capacité supérieure à celle d’un serveur Edge unique, ou si vous avez besoin d’une haute disponibilité pour votre déploiement de serveur Edge, vous pouvez configurer l’équilibrage de charge et déployer plusieurs serveurs Edge dans un pool à charge équilibrée.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="5e5ad-107">Si votre organisation dispose de plusieurs centres de données, vous pouvez disposer de déploiements de serveur Edge ou de pool Edge à plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="5e5ad-108">Toutefois, un seul des déploiements de serveur Edge peut être désigné comme itinéraire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="5e5ad-109">Cette section définit les scénarios pour les déploiements de serveur Edge et mappe les sections de planification aux scénarios possibles.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="5e5ad-110">Par exemple, si votre déploiement requiert une haute disponibilité, la Fédération avec les contacts XMPP (extensible Messaging and Presence) et Lync Mobility, sélectionnez les entrées correspondantes dans le tableau suivant qui satisferont ces exigences et utilisez le sections de planification référencées pour définir votre déploiement, comme illustré dans le diagramme suivant.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="5e5ad-111">**Processus de sélection d’un scénario de déploiement de serveur Edge**</span><span class="sxs-lookup"><span data-stu-id="5e5ad-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="5e5ad-112">![Exemple d’organigramme de déploiement](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemple d’organigramme de déploiement")</span><span class="sxs-lookup"><span data-stu-id="5e5ad-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="5e5ad-113">Ce processus vous permet de planifier et de documenter la configuration de toutes les fonctionnalités potentielles que vous envisagez de déployer pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="5e5ad-114">Toutefois, vous pouvez ajouter des services de Fédération et de mobilité après avoir déployé le serveur Edge et confirmé l’opération correcte avant d’ajouter d’autres fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="5e5ad-115">Le processus d’ajout de fonctionnalités à un déploiement de serveur Edge existant est abordé dans la section relative au déploiement.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="5e5ad-116">Pour plus d’informations sur le déploiement, reportez-vous à la rubrique déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en incluant la planification de ces fonctionnalités lors du processus de planification initial, vous pouvez vous préparer aux exigences de DNS, de pare-feu et de certificat pour les fonctionnalités ajoutées, ce qui vous permet d’acquérir les certificats et de configurer les exigences DNS et de ports</span><span class="sxs-lookup"><span data-stu-id="5e5ad-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5e5ad-117">Si vous envisagez d’installer les serveurs Edge et le proxy inverse, puis ajoutez des fonctionnalités ultérieurement (par exemple, la Fédération et la mobilité), déterminez les certificats dont vous aurez besoin pour tous les services après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="5e5ad-118">La planification et l’acquisition des certificats pour toutes les fonctionnalités à l’avance, initialement déployés ou non, vous évitent de devoir commander de nouveaux certificats afin de satisfaire aux exigences de la Fédération (c’est-à-dire sur les serveurs Edge) ou au proxy inverse (pour la mobilité services).</span><span class="sxs-lookup"><span data-stu-id="5e5ad-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5e5ad-119">Tous les services Edge s’exécutent sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="5e5ad-120">Les services ne peuvent pas être fractionnés entre deux serveurs Edge différents.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="5e5ad-121">Si vous déployez un pool de serveurs Edge pour l’évolutivité, tous les services Edge sont déployés sur chaque serveur Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="5e5ad-122">Fédération XMPP, Office Communications Server et Fédération Lync Server, la connectivité PIC et la mobilité des clients sont des services supplémentaires qui peuvent être déployés après le déploiement de votre premier serveur Edge ou pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="5e5ad-123">Les services de mobilité constituent une fonctionnalité qui utilise le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="5e5ad-124">L’installation des services de mobilité n’ajoute pas de fonctionnalités à vos serveurs Edge, mais nécessite une reconfiguration de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="5e5ad-125">La colonne d' <STRONG>objectif d’installation</STRONG> qui répertorie ces fonctionnalités fournit des instructions de planification dans la colonne associée sous la <STRONG>section planification du serveur Edge ou des sections</STRONG> permettant de planifier simultanément ces fonctionnalités à déployer lorsque les serveurs Edge sont installés et configurés.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="5e5ad-126">Identification et mise en correspondance de vos objectifs de déploiement</span><span class="sxs-lookup"><span data-stu-id="5e5ad-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e5ad-127">Objectif de l’installation</span><span class="sxs-lookup"><span data-stu-id="5e5ad-127">Installation goal</span></span></th>
<th><span data-ttu-id="5e5ad-128">Documentation de planification de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="5e5ad-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e5ad-p107">Vous considérez qu’un seul serveur suffit pour les services Edge services de votre infrastructure. Vous avez également l’intention d’utiliser des adresses IP privées pour les interfaces externes de serveur Edge utilisant la traduction d’adresses réseau (NAT) sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="5e5ad-131">Utilisez cette section de planification si vous déployez un serveur Edge unique dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="5e5ad-132">Vous allez déployer un serveur Edge avec des adresses IP privées affectées au serveur Edge et utilisera le protocole NAT pour fournir les adresses IP publiques pour les utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="5e5ad-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Serveur Edge consolidé unique avec des adresses IP privées et une interface NAT dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e5ad-p109">Vous considérez qu’un seul serveur suffit pour les services Edge services de votre infrastructure. Vous avez également l’intention d’utiliser des adresses IP publiques pour les interfaces externes de serveur sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="5e5ad-136">Utilisez cette section de planification si vous déployez un serveur Edge unique dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="5e5ad-137">Vous allez déployer un serveur Edge avec des adresses IP publiques affectées au serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="5e5ad-138">À la place de NAT, vous utiliserez le routage dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="5e5ad-139">L’adresse IP publique réelle du serveur Edge est disponible pour les connexions d’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="5e5ad-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e5ad-p111">Vous considérez que la haute disponibilité des services Edge est importante pour les utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool. Vous avez également l’intention d’utiliser des adresses IP privées pour les interfaces externes de serveur Edge utilisant NAT sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="5e5ad-143">Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="5e5ad-144">Vous allez déployer les serveurs Edge avec des adresses IP privées affectées au serveur Edge, à l’aide de l’équilibrage de charge DNS pour distribuer la communication dans le pool.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="5e5ad-145">Vous utiliserez NAT pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="5e5ad-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e5ad-147">Vous considérez que la haute disponibilité des services Edge est importante pour les utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="5e5ad-148">Vous avez également l’intention d’utiliser des adresses IP publiques pour les interfaces externes du serveur Edge sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="5e5ad-149">Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="5e5ad-150">Vous allez déployer les serveurs Edge avec des adresses IP publiques affectées au serveur Edge, à l’aide de l’équilibrage de charge DNS pour distribuer la communication dans le pool.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="5e5ad-151">Au lieu d’utiliser NAT, vous utiliserez le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="5e5ad-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e5ad-153">Vous avez décidé que la haute disponibilité des services Edge est importante pour vos utilisateurs et vous allez déployer au moins deux serveurs Edge dans ce pool à l’aide d’un programme d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="5e5ad-154">Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="5e5ad-155">Vous allez déployer les serveurs Edge avec des adresses IP publiques affectées au serveur Edge, en utilisant des programmes d’équilibrage de la charge matérielle pour distribuer la communication dans le pool.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="5e5ad-156">Au lieu d’utiliser NAT, vous utiliserez le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="5e5ad-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e5ad-158">Les scénarios de fédération vous permettent de planifier la fonctionnalité qui étendra les types de partenaires avec lesquels vos utilisateurs peuvent communiquer.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="5e5ad-159">Fédération Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e5ad-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="5e5ad-160">Fédération Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="5e5ad-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="5e5ad-161">Solution PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="5e5ad-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="5e5ad-162">Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="5e5ad-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5e5ad-163">Planification de scénarios de fédération</span><span class="sxs-lookup"><span data-stu-id="5e5ad-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="5e5ad-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planification de la Fédération entre Lync Server 2013 et Office Communications Server</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="5e5ad-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="5e5ad-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planification de la Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e5ad-167">Les services de mobilité sont fournis via le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="5e5ad-168">Les services qui permettent la mobilité pour les utilisateurs externes sont déployés sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="5e5ad-169">Vous créez ou modifiez des règles de publication existantes sur le proxy inverse afin d’activer les services de mobilité pour les utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="5e5ad-170"><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e5ad-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="5e5ad-171">Dans les scénarios suivants, les sections constituent des architectures de référence, des exemples de DNS, des définitions de ports/protocoles et des exigences en matière de certificat.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="5e5ad-172">Elles contiennent également des diagrammes pour votre DNS, des définitions de port/protocole et des besoins en termes de certificat.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="5e5ad-173">Ces diagrammes serviront de modèles que vous pourrez remplir et diffuser à d’autres équipes (par exemple, aux équipes chargées du réseau, de l’infrastructure à clé publique et du déploiement de serveur de votre organisation).</span><span class="sxs-lookup"><span data-stu-id="5e5ad-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="5e5ad-174">L’objectif des diagrammes est d’améliorer la communication et de garantir la réussite de la communication des éléments de configuration de serveur Edge requis aux personnes qui effectueront le travail de configuration proprement dit.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="5e5ad-175">Nous vous recommandons d’utiliser les diagrammes et les architectures de référence associées pour planifier votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

