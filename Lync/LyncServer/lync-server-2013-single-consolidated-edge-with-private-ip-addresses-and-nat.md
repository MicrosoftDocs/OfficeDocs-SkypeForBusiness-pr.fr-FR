---
title: 'Lync Server 2013 : serveur Edge consolidé unique avec adresses IP privées et NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c3ea97529fc32417a34dde175c75ab434fdbf0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a><span data-ttu-id="09427-102">Serveur Edge consolidé unique avec des adresses IP privées et une interface NAT dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09427-102">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09427-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="09427-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="09427-104">Si votre organisation requiert la prise en charge de moins de 15 000 connexions client du service Edge d’accès, 1 000 connexions client de service de conférence Web Lync Server actives et 500 sessions Edge A/V simultanées, et que la haute disponibilité du serveur Edge n’est pas importante, cette topologie offre les avantages d’un coût matériel inférieur et d’un déploiement plus simple.</span><span class="sxs-lookup"><span data-stu-id="09427-104">If your organization requires support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="09427-105">Si vous avez besoin d’une plus grande capacité ou si vous avez besoin d’une haute disponibilité, vous devez déployer une topologie de serveur Edge consolidée à l’adaptation.</span><span class="sxs-lookup"><span data-stu-id="09427-105">If you need greater capacity or you require high availability, you need to deploy a scaled consolidated Edge Server topology.</span></span> <span data-ttu-id="09427-106">Pour plus d’informations, reportez-vous à l’un des articles suivants :</span><span class="sxs-lookup"><span data-stu-id="09427-106">For details, see one of the following:</span></span>

  - <span></span>  
    [<span data-ttu-id="09427-107">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09427-107">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="09427-108">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09427-108">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="09427-109">Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09427-109">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<span data-ttu-id="09427-110">Le schéma n’affiche pas les directeurs, un rôle de serveur facultatif déployé sur le réseau interne entre les serveurs Edge et vos pools ou serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="09427-110">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="09427-111">Pour plus d’informations sur la topologie pour les directeurs, reportez-vous à la rubrique [composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="09427-111">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="09427-112">La figure représente un proxy inverse seul.</span><span class="sxs-lookup"><span data-stu-id="09427-112">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09427-113">La figure présente l’orientation et un exemple d’adressage IP, mais ne représente pas des flux de communication réels avec les trafics entrant et sortant corrects.</span><span class="sxs-lookup"><span data-stu-id="09427-113">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="09427-114">Cette figure représente une vue générale d’un trafic.</span><span class="sxs-lookup"><span data-stu-id="09427-114">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="09427-115">Les détails relatifs à un flux de trafic, en termes de trafic entrant (vers les ports d’écoute) et sortant (vers les serveurs ou clients de destination) sont indiqués dans le diagramme Résumé des ports de chaque scénario.</span><span class="sxs-lookup"><span data-stu-id="09427-115">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="09427-116">Par exemple, TCP 443 est un port entrant uniquement (vers le serveur Edge ou le proxy inverse), et est un flux à double-sens du point de vue du protocole (TCP).</span><span class="sxs-lookup"><span data-stu-id="09427-116">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="09427-117">De plus, la figure montre la nature du trafic si elle change quand NAT (traduction d’adresses réseau) se produit (l’adresse de destination est modifiée à l’entrée, l’adresse source est modifiée à la sortie).</span><span class="sxs-lookup"><span data-stu-id="09427-117">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="09427-118">Des exemples de pare-feu externe et interne et des interfaces serveur sont indiqués à titre d’information uniquement.</span><span class="sxs-lookup"><span data-stu-id="09427-118">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="09427-119">Enfin, un exemple de passerelle par défaut et de relations d’itinéraire est expliqué.</span><span class="sxs-lookup"><span data-stu-id="09427-119">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="09427-120">Notez également que le diagramme utilise la zone DNS <EM>. com</EM> pour représenter la zone DNS externe pour les serveurs de proxy inverse et Edge, et que la zone DNS <EM>.net</EM> fait référence à la zone DNS interne.</span><span class="sxs-lookup"><span data-stu-id="09427-120">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="09427-121">La nouveauté de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6.</span><span class="sxs-lookup"><span data-stu-id="09427-121">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="09427-122">Tout comme pour l’adressage IPv4, les adresses IPv6 doivent être assignées afin qu’elles fassent partie de l’espace d’adressage IPv6 assigné.</span><span class="sxs-lookup"><span data-stu-id="09427-122">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="09427-123">Les adresses de cette rubrique sont des exemples.</span><span class="sxs-lookup"><span data-stu-id="09427-123">The addresses in this topic are for example only.</span></span> <span data-ttu-id="09427-124">Vous devez obtenir des adresses IPv6 qui fonctionnent dans votre déploiement, fournissent la bonne portée et interagissent avec l’adressage interne et externe.</span><span class="sxs-lookup"><span data-stu-id="09427-124">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="09427-125">Windows Server offre une fonctionnalité importante pour les opérations de transition IPv6 et IPv4 vers IPv6, appelée *pile double*.</span><span class="sxs-lookup"><span data-stu-id="09427-125">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="09427-126">La double pile est une pile réseau séparée et distincte pour IPv4 et pour IPv6.</span><span class="sxs-lookup"><span data-stu-id="09427-126">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="09427-127">La double pile est ce qui vous permet d’assigner l’adressage pour IPv4 et IPv6 simultanément, et permet au serveur de communiquer avec d’autres hôtes et clients en fonction de leur configuration.</span><span class="sxs-lookup"><span data-stu-id="09427-127">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="09427-128">Les types d’adresses standard que vous utiliserez pour l’adressage IPv6 seront les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses de lien local IPv6 (semblables à l’adresse IP privée automatique adresses dans Windows Server pour IPv4)</span><span class="sxs-lookup"><span data-stu-id="09427-128">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="09427-129">Des technologies NAT (traduction d’adresses réseau) pour IPv6 existent qui permettent la traduction NAT IPv6 en IPv4 (appelée NAT64) et NAT IPv6 en IPv6 (appelée NAT66).</span><span class="sxs-lookup"><span data-stu-id="09427-129">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="09427-130">L’existence de technologies NAT signifie que les cinq scénarios présentés pour les serveurs Edge Lync Server sont toujours valides.</span><span class="sxs-lookup"><span data-stu-id="09427-130">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="09427-131">IPv6 est une rubrique complexe qui nécessite une planification soignée avec votre équipe réseau et votre fournisseur Internet afin de s’assurer que les adresses que vous affectez au niveau de Windows Server et de Lync Server 2013 fonctionneront comme prévu.</span><span class="sxs-lookup"><span data-stu-id="09427-131">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="09427-132">Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.</span><span class="sxs-lookup"><span data-stu-id="09427-132">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="09427-133">**Topologie Edge consolidée unique**</span><span class="sxs-lookup"><span data-stu-id="09427-133">**Single consolidated edge topology**</span></span>

<span data-ttu-id="09427-134">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span><span class="sxs-lookup"><span data-stu-id="09427-134">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="09427-135">Si vous utilisez le contrôle d’admission des appels (CAC), vous devez toujours attribuer des adresses IPv4 à l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="09427-135">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="09427-136">CAC utilise les adresses IPv4 et elles doivent être disponibles pour qu’il puisse fonctionner.</span><span class="sxs-lookup"><span data-stu-id="09427-136">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09427-137">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="09427-137">In This Section</span></span>

  - [<span data-ttu-id="09427-138">Résumé des certificats-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09427-138">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="09427-139">Résumé des ports-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09427-139">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="09427-140">Résumé des enregistrements DNS-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09427-140">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="09427-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09427-141">See Also</span></span>


[<span data-ttu-id="09427-142">Architecture d’adressage IP version 6</span><span class="sxs-lookup"><span data-stu-id="09427-142">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="09427-143">Format d’adresse unicast global IPv6</span><span class="sxs-lookup"><span data-stu-id="09427-143">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="09427-144">Adresses unicast IPv6 locales uniques</span><span class="sxs-lookup"><span data-stu-id="09427-144">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

