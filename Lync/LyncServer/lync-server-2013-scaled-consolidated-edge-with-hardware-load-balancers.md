---
title: 'Lync Server 2013 : serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a961b6eabb85e135b1cfb36cf5738cbf757b547
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="7bf82-102">Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bf82-102">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bf82-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="7bf82-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="7bf82-104">Dans la topologie de pool de serveurs Edge, deux ou plusieurs serveurs Edge sont déployés en tant que pool à charge équilibrée dans le réseau de périmètre du centre de données.</span><span class="sxs-lookup"><span data-stu-id="7bf82-104">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="7bf82-105">L’équilibrage de la charge matérielle est utilisé pour le trafic vers les interfaces de serveur Edge externe et interne.</span><span class="sxs-lookup"><span data-stu-id="7bf82-105">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="7bf82-106">Si votre organisation doit prendre en charge plus de 15 000 connexions client du service Edge d’accès, 1 000 connexions client de service Edge de conférence Web actives ou 500 sessions de service Edge A/V simultanées, et que la haute disponibilité du serveur Edge est importante, cette topologie offre des avantages en termes d’extensibilité et de basculement.</span><span class="sxs-lookup"><span data-stu-id="7bf82-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="7bf82-107">Le schéma n’affiche pas les directeurs, un rôle de serveur facultatif déployé sur le réseau interne entre les serveurs Edge et vos pools ou serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="7bf82-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="7bf82-108">.</span><span class="sxs-lookup"><span data-stu-id="7bf82-108">.</span></span> <span data-ttu-id="7bf82-109">Pour plus d’informations sur la topologie pour les directeurs, reportez-vous à la rubrique [composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="7bf82-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7bf82-110">La figure présente l’orientation et un exemple d’adressage IP, mais ne représente pas des flux de communication réels avec les trafics entrant et sortant corrects.</span><span class="sxs-lookup"><span data-stu-id="7bf82-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="7bf82-111">Cette figure représente une vue générale d’un trafic.</span><span class="sxs-lookup"><span data-stu-id="7bf82-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="7bf82-112">Les détails relatifs à un flux de trafic, en termes de trafic entrant (vers les ports d’écoute) et sortant (vers les serveurs ou clients de destination) sont indiqués dans le diagramme Résumé des ports de chaque scénario.</span><span class="sxs-lookup"><span data-stu-id="7bf82-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="7bf82-113">Par exemple, le protocole TCP 443 est réellement entrant (vers le serveur Edge ou proxy inverse) uniquement, et n’est qu’un flux bidirectionnel à partir d’un point de vue du protocole (TCP).</span><span class="sxs-lookup"><span data-stu-id="7bf82-113">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="7bf82-114">De plus, la figure montre la nature du trafic si elle change quand NAT (traduction d’adresses réseau) se produit (l’adresse de destination est modifiée à l’entrée, l’adresse source est modifiée à la sortie).</span><span class="sxs-lookup"><span data-stu-id="7bf82-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="7bf82-115">Des exemples de pare-feu externe et interne et des interfaces serveur sont indiqués à titre d’information uniquement.</span><span class="sxs-lookup"><span data-stu-id="7bf82-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="7bf82-116">Enfin, un exemple de passerelle par défaut et de relations d’itinéraire est expliqué.</span><span class="sxs-lookup"><span data-stu-id="7bf82-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="7bf82-117">Notez également que le diagramme utilise la zone DNS <EM>. com</EM> pour représenter la zone DNS externe pour les serveurs de proxy inverse et Edge, et que la zone DNS <EM>.net</EM> fait référence à la zone DNS interne.</span><span class="sxs-lookup"><span data-stu-id="7bf82-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="7bf82-118">La nouveauté de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6.</span><span class="sxs-lookup"><span data-stu-id="7bf82-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="7bf82-119">Tout comme pour l’adressage IPv4, les adresses IPv6 doivent être assignées afin qu’elles fassent partie de l’espace d’adressage IPv6 assigné.</span><span class="sxs-lookup"><span data-stu-id="7bf82-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="7bf82-120">Les adresses de cette rubrique sont des exemples.</span><span class="sxs-lookup"><span data-stu-id="7bf82-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="7bf82-121">Vous devez obtenir des adresses IPv6 qui fonctionnent dans votre déploiement, fournissent la bonne portée et interagissent avec l’adressage interne et externe.</span><span class="sxs-lookup"><span data-stu-id="7bf82-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="7bf82-122">Windows Server offre une fonctionnalité importante pour les opérations de transition IPv6 et IPv4 vers IPv6, appelée *pile double*.</span><span class="sxs-lookup"><span data-stu-id="7bf82-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="7bf82-123">La double pile est une pile réseau séparée et distincte pour IPv4 et pour IPv6.</span><span class="sxs-lookup"><span data-stu-id="7bf82-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="7bf82-124">La double pile est ce qui vous permet d’assigner l’adressage pour IPv4 et IPv6 simultanément, et permet au serveur de communiquer avec d’autres hôtes et clients en fonction de leur configuration.</span><span class="sxs-lookup"><span data-stu-id="7bf82-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="7bf82-125">Les types d’adresses standard que vous utiliserez pour l’adressage IPv6 seront les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses de lien local IPv6 (semblables à l’adresse IP privée automatique adresses dans Windows Server pour IPv4)</span><span class="sxs-lookup"><span data-stu-id="7bf82-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="7bf82-126">Des technologies NAT (traduction d’adresses réseau) pour IPv6 existent qui permettent la traduction NAT IPv6 en IPv4 (appelée NAT64) et NAT IPv6 en IPv6 (appelée NAT66).</span><span class="sxs-lookup"><span data-stu-id="7bf82-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="7bf82-127">L’existence de technologies NAT signifie que les cinq scénarios présentés pour les serveurs Edge Lync Server sont toujours valides.</span><span class="sxs-lookup"><span data-stu-id="7bf82-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7bf82-128">IPv6 est une rubrique complexe qui nécessite une planification soignée avec votre équipe réseau et votre fournisseur Internet afin de s’assurer que les adresses que vous affectez au niveau de Windows Server et de Lync Server 2013 fonctionneront comme prévu.</span><span class="sxs-lookup"><span data-stu-id="7bf82-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="7bf82-129">Consultez les liens à la fin de cette rubrique pour des ressources supplémentaires sur l’adressage IPv6 et la planification.</span><span class="sxs-lookup"><span data-stu-id="7bf82-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="7bf82-130">**Configuration du programme d’équilibrage de la charge matérielle**</span><span class="sxs-lookup"><span data-stu-id="7bf82-130">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="7bf82-131">Pour plus d’informations, reportez-vous à la section « Configuration requise pour l’équilibreur de charge matérielle pour les serveurs Edge A/V » dans [composants requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7bf82-131">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="7bf82-132">**Topologie Edge consolidée mise à l’échelle (avec charge matérielle équilibrée)**</span><span class="sxs-lookup"><span data-stu-id="7bf82-132">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="7bf82-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="7bf82-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7bf82-134">Si vous utilisez le contrôle d’admission des appels (CAC), vous devez toujours attribuer des adresses IPv4 à l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7bf82-134">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="7bf82-135">CAC utilise les adresses IPv4 et elles doivent être disponibles pour qu’il puisse fonctionner.</span><span class="sxs-lookup"><span data-stu-id="7bf82-135">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7bf82-136">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7bf82-136">In This Section</span></span>

  - [<span data-ttu-id="7bf82-137">Résumé des certificats-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bf82-137">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="7bf82-138">Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bf82-138">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="7bf82-139">Résumé des enregistrements DNS-serveur Edge consolidé ajusté avec programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bf82-139">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7bf82-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7bf82-140">See Also</span></span>


[<span data-ttu-id="7bf82-141">Architecture d’adressage IP version 6</span><span class="sxs-lookup"><span data-stu-id="7bf82-141">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="7bf82-142">Format d’adresse unicast global IPv6</span><span class="sxs-lookup"><span data-stu-id="7bf82-142">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="7bf82-143">Adresses unicast IPv6 locales uniques</span><span class="sxs-lookup"><span data-stu-id="7bf82-143">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

