---
title: 'Lync Server 2013 : Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle'
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
ms.openlocfilehash: 5fe027019953175c0ac6ede51a86ad3a300c2681
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="ba74e-102">Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba74e-102">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba74e-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ba74e-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ba74e-104">Dans la topologie de pool de bords, deux serveurs Edge ou plus sont déployés sous la forme d’un pool équilibré dans le réseau de périmètre du centre de données.</span><span class="sxs-lookup"><span data-stu-id="ba74e-104">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="ba74e-105">Le niveau d’équilibrage de la charge matérielle est utilisé pour le trafic vers les interfaces de serveur Edge externe et interne.</span><span class="sxs-lookup"><span data-stu-id="ba74e-105">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="ba74e-106">Si votre organisation a besoin d’une prise en charge pour plus de 15 000 connexions client de service Edge, 1 000 les connexions de clients de service Edge pour les conférences Web actives 500 ou les sessions de service Edge A/V en parallèle, et la haute disponibilité du serveur Edge est importante, cette topologie présente les avantages de l’évolutivité et de la prise en charge du basculement.</span><span class="sxs-lookup"><span data-stu-id="ba74e-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="ba74e-107">La figure ne montre pas les directeurs, un rôle serveur facultatif déployé sur le réseau interne entre les serveurs de périphérie et vos pools ou serveurs.</span><span class="sxs-lookup"><span data-stu-id="ba74e-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="ba74e-108">.</span><span class="sxs-lookup"><span data-stu-id="ba74e-108">.</span></span> <span data-ttu-id="ba74e-109">Pour plus d’informations sur la topologie des directeurs, voir [composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="ba74e-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba74e-110">La figure affichée correspond à l’orientation et à l’adresse IP, par exemple, sans vouloir représenter les flux de communication réel avec le trafic entrant et sortant correct.</span><span class="sxs-lookup"><span data-stu-id="ba74e-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="ba74e-111">La figure représente une vue de haut niveau du trafic potentiel.</span><span class="sxs-lookup"><span data-stu-id="ba74e-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="ba74e-112">Les détails relatifs au flux de trafic tels qu’ils sont liés aux ports entrants (vers les ports d’écoute) et sortants (vers les serveurs de destination ou les clients) sont représentés dans le schéma de synthèse de port de chaque scénario.</span><span class="sxs-lookup"><span data-stu-id="ba74e-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="ba74e-113">Par exemple, le protocole TCP 443 est réellement entrant (vers le serveur de périphérie ou proxy inverse) uniquement, et n’est qu’un flux bidirectionnel à partir d’un point de vue du protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="ba74e-113">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="ba74e-114">Par ailleurs, la figure montre la nature du trafic au fur et à mesure de son changement lors de la modification de la traduction d’adresses réseau (la traduction d’adresses de destination a changé sur le trafic sortant).</span><span class="sxs-lookup"><span data-stu-id="ba74e-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="ba74e-115">Par exemple, les interfaces serveur et de pare-feu internes et externes sont affichées uniquement à des fins de référence.</span><span class="sxs-lookup"><span data-stu-id="ba74e-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="ba74e-116">Enfin, vous pouvez voir des exemples de passerelles et d’itinéraires par défaut, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="ba74e-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="ba74e-117">Notez également que le diagramme utilise la zone DNS <EM>. com</EM> pour représenter la zone DNS externe pour les serveurs de proxy inverse et Edge, et que la zone DNS <EM>.net</EM> fait référence à la zone DNS interne.</span><span class="sxs-lookup"><span data-stu-id="ba74e-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="ba74e-118">La nouveauté de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba74e-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="ba74e-119">À l’instar de l’adressage IPv4, une adresse IPv6 doit être attribuée de telle sorte que les adresses font partie de votre espace d’adressage IPv6 attribué.</span><span class="sxs-lookup"><span data-stu-id="ba74e-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="ba74e-120">Les adresses figurant dans cette rubrique sont par exemple uniquement.</span><span class="sxs-lookup"><span data-stu-id="ba74e-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="ba74e-121">Vous devez acquérir les adresses IPv6 qui fonctionneront dans votre déploiement, fournir l’étendue correcte et utilisera l’adressage interne et externe.</span><span class="sxs-lookup"><span data-stu-id="ba74e-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="ba74e-122">Windows Server fournit une fonctionnalité importante pour les opérations IPv6 de transition et IPv4 à IPv6 appelées *pile double*.</span><span class="sxs-lookup"><span data-stu-id="ba74e-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="ba74e-123">La pile double est une pile réseau séparée et distincte pour IPv4 et IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba74e-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="ba74e-124">La pile double est celle qui vous permet d’attribuer l’adresse IPv4 et IPv6 en même temps, et permet au serveur de communiquer avec d’autres hôtes et clients en fonction de la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="ba74e-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="ba74e-125">Les types d’adresse que vous utiliserez pour l’adressage IPv6 seront les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses locales de liaison IPv6 (similaires à l’adresse IP privée automatique). adresses dans Windows Server pour IPv4)</span><span class="sxs-lookup"><span data-stu-id="ba74e-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="ba74e-126">Il existe des technologies de traduction d’adresses réseau (NAT) pour IPv6 qui autorisent le protocole NAT IPv6 sur IPv4 (également appelé NAT64) et la traduction d’adresses réseau via le protocole IPv6 (appelé NAT66).</span><span class="sxs-lookup"><span data-stu-id="ba74e-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="ba74e-127">L’existence de technologies NAT signifie que les cinq scénarios présentés pour les serveurs Edge Lync Server sont toujours valides.</span><span class="sxs-lookup"><span data-stu-id="ba74e-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ba74e-128">Le protocole IPv6 est un sujet complexe et nécessite une planification soigneuse de votre équipe réseau et de votre fournisseur d’accès à Internet pour vous assurer que les adresses affectées au niveau Windows Server et au niveau Lync Server 2013 fonctionneront comme prévu.</span><span class="sxs-lookup"><span data-stu-id="ba74e-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="ba74e-129">Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba74e-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="ba74e-130">**Configuration de l’équilibrage de charge matérielle**</span><span class="sxs-lookup"><span data-stu-id="ba74e-130">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="ba74e-131">Pour plus d’informations, reportez-vous à la section « Configuration requise du système d’équilibrage de charge matérielle pour une application Microsoft Edge » dans les [composants requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ba74e-131">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="ba74e-132">**Topologie de frontière consolidée mise à l’échelle (équilibrage de charge matérielle)**</span><span class="sxs-lookup"><span data-stu-id="ba74e-132">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="ba74e-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="ba74e-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ba74e-134">Si vous utilisez le contrôle d’admission des appels (CAC), vous devez quand même affecter des adresses IPv4 à l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ba74e-134">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="ba74e-135">Le CAC utilise les adresses IPv4 et doit être disponible pour fonctionner.</span><span class="sxs-lookup"><span data-stu-id="ba74e-135">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ba74e-136">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ba74e-136">In This Section</span></span>

  - [<span data-ttu-id="ba74e-137">Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba74e-137">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="ba74e-138">Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba74e-138">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="ba74e-139">Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba74e-139">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba74e-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba74e-140">See Also</span></span>


[<span data-ttu-id="ba74e-141">Architecture d’adresse IP version 6</span><span class="sxs-lookup"><span data-stu-id="ba74e-141">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="ba74e-142">Format d’adresse monodiffusion global IPv6</span><span class="sxs-lookup"><span data-stu-id="ba74e-142">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="ba74e-143">Adresses monodiffusion IPv6 locales uniques</span><span class="sxs-lookup"><span data-stu-id="ba74e-143">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

