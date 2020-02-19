---
title: 'Lync Server 2013 : paramètres réseau pour les fonctionnalités avancées de voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51950080d5f1c9aca2e94fe64f9e1d440da97b59
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="0bf1e-102">Paramètres réseau pour les fonctionnalités avancées de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf1e-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bf1e-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="0bf1e-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="0bf1e-104">Lync Server dispose de trois fonctionnalités voix entreprise avancées : le contrôle d’admission des appels (CAC), les services d’urgence (E9-1-1) et la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="0bf1e-105">Ces fonctionnalités partagent certaines exigences de configuration pour les régions réseau, les sites réseau et l’Association de chaque sous-réseau dans la topologie Lync Server avec un site réseau.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="0bf1e-106">Pour plus d’informations sur la planification du déploiement de ces fonctionnalités, voir :</span><span class="sxs-lookup"><span data-stu-id="0bf1e-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="0bf1e-107">Planification du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf1e-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="0bf1e-108">Planification des services d’urgence (E9-1-1) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf1e-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="0bf1e-109">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf1e-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="0bf1e-110">Pour plus d’informations sur le déploiement de chacune de ces fonctionnalités, reportez-vous à la rubrique [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0bf1e-111">Cette rubrique fournit une vue d’ensemble des exigences de configuration communes aux trois fonctionnalités avancées de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="0bf1e-112">Régions réseau</span><span class="sxs-lookup"><span data-stu-id="0bf1e-112">Network Regions</span></span>

<span data-ttu-id="0bf1e-113">Une région réseau est un concentrateur réseau ou un segment réseau principal utilisé uniquement dans la configuration du service Contrôle d’admission des appels, du système E9-1-1 et du contournement de média.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bf1e-114">Les régions réseau sont différentes des régions de conférence rendez-vous Lync Server, qui sont requises pour associer des numéros d’accès de conférence rendez-vous avec un ou plusieurs plans de numérotation Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="0bf1e-115">Pour plus d’informations sur les régions de conférence rendez-vous, voir Configuration requise pour les conférences rendez <A href="lync-server-2013-dial-in-conferencing-requirements.md">-vous dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="0bf1e-116">Le contrôle d’admission des appels exige que toutes les régions réseau aient un site central Lync Server associé, qui gère le trafic multimédia au sein de la région (autrement dit, il prend des décisions en fonction des stratégies que vous avez configurées, qu’il s’agisse d’une session audio ou vidéo en temps réel). être établie).</span><span class="sxs-lookup"><span data-stu-id="0bf1e-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="0bf1e-117">Les sites centraux de Lync Server ne représentent pas les emplacements géographiques, mais plutôt des groupes logiques de serveurs configurés en tant que pool ou ensemble de pools.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="0bf1e-118">Pour plus d’informations sur les sites centraux, voir [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="0bf1e-119">Voir également les [topologies prises en charge dans Lync Server 2013](lync-server-2013-supported-topologies.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="0bf1e-120">Pour configurer une région réseau, vous pouvez utiliser l’onglet **régions** de la section **Configuration réseau** du panneau de configuration Lync Server ou exécuter les cmdlets **New-applet csnetworkregion** ou **Set-applet csnetworkregion** Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="0bf1e-121">Pour obtenir des instructions, voir [Create or Modify a Network Region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) dans la documentation de déploiement, ou reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="0bf1e-122">Les mêmes définitions de région réseau sont partagées par les trois fonctionnalités voix entreprise avancées.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="0bf1e-123">Si vous avez créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin d’en créer de nouvelles pour les autres fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="0bf1e-124">Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="0bf1e-125">Par exemple, si vous avez créé des régions réseau pour le système E9-1-1 (qui ne nécessite pas de site central associé) et que vous déployez ultérieurement le contrôle d’admission des appels, vous devez modifier chacune des définitions de région réseau pour spécifier un site central.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="0bf1e-126">Pour associer un site central Lync Server à une région réseau, vous spécifiez le nom du site central, soit en utilisant la section **Configuration réseau** du panneau de configuration Lync Server, soit en exécutant les cmdlets applet csnetworkregion ou **Set-applet csnetworkregion** de l’environnement **de** commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="0bf1e-127">Pour obtenir des instructions, voir [Create or Modify a Network Region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) dans la documentation de déploiement, ou reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="0bf1e-128">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="0bf1e-128">Network Sites</span></span>

<span data-ttu-id="0bf1e-p107">Un site réseau représente un emplacement géographique, tel qu’une succursale, un bureau régional ou un bureau principal. Chaque site réseau doit être associé à une région réseau spécifique.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bf1e-131">Les sites réseau sont utilisés uniquement par les fonctionnalités avancées de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="0bf1e-132">Ils ne sont pas identiques aux sites de succursale que vous configurez dans votre topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="0bf1e-133">Pour plus d’informations sur les sites de succursale, voir <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="0bf1e-134">Voir également les <A href="lync-server-2013-supported-topologies.md">topologies prises en charge dans Lync Server 2013</A> dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="0bf1e-135">Pour configurer un site réseau et l’associer à une région réseau, vous pouvez utiliser la section **Configuration réseau** du panneau de configuration Lync Server ou exécuter les cmdlets **New-applet csnetworksite** ou **Set-applet csnetworksite** de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="0bf1e-136">Pour plus d’informations, voir [Create or Modify a Network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) dans la documentation de déploiement, ou reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="0bf1e-137">Identifier les sous-réseaux IP</span><span class="sxs-lookup"><span data-stu-id="0bf1e-137">Identify IP Subnets</span></span>

<span data-ttu-id="0bf1e-p110">Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="0bf1e-p111">Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille généralement à Détroit, se rend dans les bureaux de New York pour suivre une formation, allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages allouées à New York (par exemple, 172.29.80.103).</span><span class="sxs-lookup"><span data-stu-id="0bf1e-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0bf1e-142">Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="0bf1e-143">Un client Lync prend son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associé.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="0bf1e-144">Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="0bf1e-145">Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="0bf1e-146">(Si vous déployez le contrôle d’admission des appels, mais pas le contournement de média, le contrôle d’admission des appels fonctionnera correctement même si vous configurez des sous-réseaux virtuels.)</span><span class="sxs-lookup"><span data-stu-id="0bf1e-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="0bf1e-147">Par exemple, si un client Lync se connecte sur un ordinateur avec l’adresse IP 172.29.81.57 avec un masque de sous-réseau IP 255.255.255.0, il demandera l’ID de contournement associé au sous-réseau 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="0bf1e-148">Si le sous-réseau est défini comme 172.29.0.0/16, bien que le client appartienne au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="0bf1e-149">Par conséquent, il est important que l’administrateur entre des sous-réseaux exactement comme fournis par les clients Lync (qui sont configurés avec des sous-réseaux pendant la configuration du réseau, de façon statique ou par le protocole DHCP).</span><span class="sxs-lookup"><span data-stu-id="0bf1e-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="0bf1e-150">Association de sous-réseaux à des sites réseau</span><span class="sxs-lookup"><span data-stu-id="0bf1e-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="0bf1e-151">Chaque sous-réseau dans le réseau d’entreprise doit être associé à un site réseau (c’est-à-dire que chaque sous-réseau doit être associé à un emplacement géographique).</span><span class="sxs-lookup"><span data-stu-id="0bf1e-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="0bf1e-152">Cette association de sous-réseaux active les fonctionnalités avancées de voix entreprise pour localiser les points de terminaison géographiquement.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="0bf1e-153">Par exemple, la localisation des points de terminaison permet au contrôle d’admission des appels de réguler le flux de données audio et vidéo en temps réel qui transitent vers et depuis le site réseau.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="0bf1e-154">Pour associer des sous-réseaux à des sites réseau, vous pouvez utiliser la section **Configuration réseau** du panneau de configuration Lync Server ou vous pouvez utiliser Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="0bf1e-155">Pour obtenir des instructions, voir [associer un sous-réseau à un site réseau dans Lync server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) dans la documentation de déploiement, ou reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf1e-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0bf1e-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0bf1e-156">See Also</span></span>


[<span data-ttu-id="0bf1e-157">Planification du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf1e-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="0bf1e-158">Planification des services d’urgence (E9-1-1) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf1e-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="0bf1e-159">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf1e-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

