---
title: 'Lync Server 2013 : Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau'
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
ms.openlocfilehash: 188104797475b0e0b54c39b3b896478d80e5636b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a><span data-ttu-id="bfc97-102">Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfc97-102">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfc97-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="bfc97-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="bfc97-104">Si votre organisation a besoin d’une prise en charge de moins de 15 000 connexions clientes du service Edge d’accès, de 1 000 de connexions clientes Lync Server Web service et de 500 sessions A/V de haut niveau, et qu’une haute disponibilité du serveur Edge n’est pas importante, cette topologie présente les avantages d’un faible coût matériel et d’un déploiement simplifié.</span><span class="sxs-lookup"><span data-stu-id="bfc97-104">If your organization requires support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="bfc97-105">Si vous avez besoin d’une plus grande capacité ou que vous avez besoin d’une haute disponibilité, vous devez déployer une topologie de serveur Edge consolidée à l’échelle.</span><span class="sxs-lookup"><span data-stu-id="bfc97-105">If you need greater capacity or you require high availability, you need to deploy a scaled consolidated Edge Server topology.</span></span> <span data-ttu-id="bfc97-106">Pour plus d’informations, consultez l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="bfc97-106">For details, see one of the following:</span></span>

  - <span></span>  
    [<span data-ttu-id="bfc97-107">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfc97-107">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="bfc97-108">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfc97-108">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="bfc97-109">Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfc97-109">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<span data-ttu-id="bfc97-110">La figure ne montre pas les directeurs, un rôle serveur facultatif déployé sur le réseau interne entre les serveurs de périphérie et vos pools ou serveurs.</span><span class="sxs-lookup"><span data-stu-id="bfc97-110">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="bfc97-111">Pour plus d’informations sur la topologie des directeurs, voir [composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="bfc97-111">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="bfc97-112">La figure représente une seule doublure inverse.</span><span class="sxs-lookup"><span data-stu-id="bfc97-112">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bfc97-113">La figure affichée correspond à l’orientation et à l’adresse IP, par exemple, sans vouloir représenter les flux de communication réel avec le trafic entrant et sortant correct.</span><span class="sxs-lookup"><span data-stu-id="bfc97-113">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="bfc97-114">La figure représente une vue de haut niveau du trafic potentiel.</span><span class="sxs-lookup"><span data-stu-id="bfc97-114">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="bfc97-115">Les détails relatifs au flux de trafic tels qu’ils sont liés aux ports entrants (vers les ports d’écoute) et sortants (vers les serveurs de destination ou les clients) sont représentés dans le schéma de synthèse de port de chaque scénario.</span><span class="sxs-lookup"><span data-stu-id="bfc97-115">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="bfc97-116">Par exemple, le protocole TCP 443 est en fait entrant (pour le proxy Edge ou inverse) uniquement, et n’est qu’un flux bidirectionnel à partir d’un point de vue du protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="bfc97-116">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="bfc97-117">Par ailleurs, la figure montre la nature du trafic au fur et à mesure de son changement lors de la modification de la traduction d’adresses réseau (la traduction d’adresses de destination a changé sur le trafic sortant).</span><span class="sxs-lookup"><span data-stu-id="bfc97-117">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="bfc97-118">Par exemple, les interfaces serveur et de pare-feu internes et externes sont affichées uniquement à des fins de référence.</span><span class="sxs-lookup"><span data-stu-id="bfc97-118">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="bfc97-119">Enfin, vous pouvez voir des exemples de passerelles et d’itinéraires par défaut, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="bfc97-119">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="bfc97-120">Notez également que le diagramme utilise la zone DNS <EM>. com</EM> pour représenter la zone DNS externe pour les serveurs de proxy inverse et Edge, et que la zone DNS <EM>.net</EM> fait référence à la zone DNS interne.</span><span class="sxs-lookup"><span data-stu-id="bfc97-120">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="bfc97-121">La nouveauté de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6.</span><span class="sxs-lookup"><span data-stu-id="bfc97-121">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="bfc97-122">À l’instar de l’adressage IPv4, une adresse IPv6 doit être attribuée de telle sorte que les adresses font partie de votre espace d’adressage IPv6 attribué.</span><span class="sxs-lookup"><span data-stu-id="bfc97-122">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="bfc97-123">Les adresses figurant dans cette rubrique sont par exemple uniquement.</span><span class="sxs-lookup"><span data-stu-id="bfc97-123">The addresses in this topic are for example only.</span></span> <span data-ttu-id="bfc97-124">Vous devez acquérir les adresses IPv6 qui fonctionneront dans votre déploiement, fournir l’étendue correcte et utilisera l’adressage interne et externe.</span><span class="sxs-lookup"><span data-stu-id="bfc97-124">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="bfc97-125">Windows Server fournit une fonctionnalité importante pour les opérations IPv6 de transition et IPv4 à IPv6 appelées *pile double*.</span><span class="sxs-lookup"><span data-stu-id="bfc97-125">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="bfc97-126">La pile double est une pile réseau séparée et distincte pour IPv4 et IPv6.</span><span class="sxs-lookup"><span data-stu-id="bfc97-126">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="bfc97-127">La pile double est celle qui vous permet d’attribuer l’adresse IPv4 et IPv6 en même temps, et permet au serveur de communiquer avec d’autres hôtes et clients en fonction de la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="bfc97-127">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="bfc97-128">Les types d’adresse que vous utiliserez pour l’adressage IPv6 seront les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses locales de liaison IPv6 (similaires à l’adresse IP privée automatique). adresses dans Windows Server pour IPv4)</span><span class="sxs-lookup"><span data-stu-id="bfc97-128">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="bfc97-129">Il existe des technologies de traduction d’adresses réseau (NAT) pour IPv6 qui autorisent le protocole NAT IPv6 sur IPv4 (également appelé NAT64) et la traduction d’adresses réseau via le protocole IPv6 (appelé NAT66).</span><span class="sxs-lookup"><span data-stu-id="bfc97-129">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="bfc97-130">L’existence de technologies NAT signifie que les cinq scénarios présentés pour les serveurs Edge Lync Server sont toujours valides.</span><span class="sxs-lookup"><span data-stu-id="bfc97-130">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="bfc97-131">Le protocole IPv6 est un sujet complexe et nécessite une planification soigneuse de votre équipe réseau et de votre fournisseur d’accès à Internet pour vous assurer que les adresses affectées au niveau Windows Server et au niveau Lync Server 2013 fonctionneront comme prévu.</span><span class="sxs-lookup"><span data-stu-id="bfc97-131">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="bfc97-132">Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.</span><span class="sxs-lookup"><span data-stu-id="bfc97-132">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="bfc97-133">**Topologie de périphérie consolidée unique**</span><span class="sxs-lookup"><span data-stu-id="bfc97-133">**Single consolidated edge topology**</span></span>

<span data-ttu-id="bfc97-134">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span><span class="sxs-lookup"><span data-stu-id="bfc97-134">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bfc97-135">Si vous utilisez le contrôle d’admission des appels (CAC), vous devez quand même affecter des adresses IPv4 à l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bfc97-135">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="bfc97-136">Le CAC utilise les adresses IPv4 et doit être disponible pour fonctionner.</span><span class="sxs-lookup"><span data-stu-id="bfc97-136">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bfc97-137">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bfc97-137">In This Section</span></span>

  - [<span data-ttu-id="bfc97-138">Résumé des certificats - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfc97-138">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="bfc97-139">Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfc97-139">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="bfc97-140">Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfc97-140">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfc97-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bfc97-141">See Also</span></span>


[<span data-ttu-id="bfc97-142">Architecture d’adresse IP version 6</span><span class="sxs-lookup"><span data-stu-id="bfc97-142">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="bfc97-143">Format d’adresse monodiffusion global IPv6</span><span class="sxs-lookup"><span data-stu-id="bfc97-143">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="bfc97-144">Adresses monodiffusion IPv6 locales uniques</span><span class="sxs-lookup"><span data-stu-id="bfc97-144">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

