---
title: Configuration requise pour l’équilibrage de charge de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 016ace11375483fbeaa59199e9f1cdae23654cd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513821"
---
# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="fa214-102">Exigences en matière d’équilibrage de charge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa214-102">Load balancing requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa214-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="fa214-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="fa214-104">Si vous disposez de pools frontaux, de pools directeurs ou de pools de serveurs Edge, vous devez déployer l’équilibrage de charge pour ces pools.</span><span class="sxs-lookup"><span data-stu-id="fa214-104">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="fa214-105">L’équilibrage de la charge distribue le trafic entre les serveurs dans un pool.</span><span class="sxs-lookup"><span data-stu-id="fa214-105">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="fa214-106">Lync Server 2013 prend en charge deux types de solutions d’équilibrage de charge pour le trafic client à serveur : l’équilibrage de charge DNS (Domain Name System) et l’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="fa214-106">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="fa214-107">L’équilibrage de charge DNS offre plusieurs avantages, notamment l’administration simplifiée, une résolution des problèmes plus efficace et la possibilité d’isoler la plupart du trafic Lync Server des problèmes potentiels d’équilibreur de charge matériel.</span><span class="sxs-lookup"><span data-stu-id="fa214-107">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="fa214-108">Déterminez la solution d’équilibrage de la charge adaptée à chaque pool de votre déploiement, en gardant à l’esprit les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="fa214-108">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="fa214-p103">Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface et l’équilibrage de la charge matérielle sur l’autre.</span><span class="sxs-lookup"><span data-stu-id="fa214-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="fa214-p104">Certains types de trafic nécessitent un programme d’équilibrage de la charge matérielle. Par exemple, le trafic HTTP requiert un programme d’équilibrage de la charge matérielle plutôt que l’équilibrage de la charge DNS. Celui-ci ne fonctionne pas avec le trafic web client-à-serveur.</span><span class="sxs-lookup"><span data-stu-id="fa214-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="fa214-114">Pour plus d’informations sur le choix d’une solution d’équilibrage de la charge matérielle, voir [Configuration requise de l’équilibreur de charge matérielle pour Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa214-114">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="fa214-115">Si vous décidez d’utiliser l’équilibrage de la charge DNS pour un pool mais que vous souhaitez quand même implémenter des programmes d’équilibrage de la charge matérielle pour certains types de trafics, tels que le trafic HTTP, l’administration des programmes d’équilibrage de la charge matérielle est grandement simplifiée.</span><span class="sxs-lookup"><span data-stu-id="fa214-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="fa214-116">Par exemple, la configuration de l’équilibreur de la charge matérielle sera plus simple, car elle ne gérera que le trafic HTTP et HTTPs, tandis que tous les autres protocoles seront gérés par l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="fa214-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="fa214-117">Pour plus d’informations, reportez-vous à la rubrique [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="fa214-117">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="fa214-118">Pour le trafic de serveur à serveur, Lync Server 2013 utilise un équilibrage de charge prenant en charge la topologie.</span><span class="sxs-lookup"><span data-stu-id="fa214-118">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="fa214-119">Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs.</span><span class="sxs-lookup"><span data-stu-id="fa214-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="fa214-120">Les administrateurs n’ont pas besoin de configurer ou de gérer ce type d’équilibrage de charge.</span><span class="sxs-lookup"><span data-stu-id="fa214-120">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="fa214-121">Si vous utilisez l’équilibrage de la charge DNS et que vous avez besoin de bloquer le trafic sur un ordinateur spécifique, il ne suffit pas de supprimer les entrées d’adresses IP du nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="fa214-121">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="fa214-122">Vous devez également supprimer l’entrée DNS pour l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fa214-122">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

