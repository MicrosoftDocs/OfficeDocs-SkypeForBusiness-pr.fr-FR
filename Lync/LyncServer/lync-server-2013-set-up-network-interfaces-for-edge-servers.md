---
title: 'Lync Server 2013 : configuration des interfaces réseau pour les serveurs Edge'
description: 'Lync Server 2013 : configurez les interfaces réseau pour les serveurs Edge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 576ca8670a34be022e3df0a699edaf0df10f5b70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550470"
---
# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="3a54c-103">Configuration des interfaces réseau pour les serveurs Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a54c-103">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a54c-104">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3a54c-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3a54c-105">Chaque serveur Edge est un ordinateur multirésident doté d’interfaces internes et externes.</span><span class="sxs-lookup"><span data-stu-id="3a54c-105">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="3a54c-106">Les paramètres DNS (Domain Name System) de l’adaptateur varient selon qu’il y a des serveurs DNS dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="3a54c-106">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="3a54c-107">Si les serveurs DNS existent dans le périmètre, ils doivent disposer d’une zone contenant un ou plusieurs enregistrements DNS A pour le serveur ou le pool du tronçon suivant (c’est-à-dire un directeur ou un pool frontal désigné), et pour les requêtes externes, ils reportent sur des recherches de noms à d’autres serveurs DNS publics.</span><span class="sxs-lookup"><span data-stu-id="3a54c-107">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="3a54c-108">S’il n’existe aucun serveur DNS dans le périmètre, le ou les serveurs de périphérie utilisent des serveurs DNS externes pour résoudre les recherches de noms Internet et chaque serveur Edge utilise un hôte pour résoudre les noms de serveur du tronçon suivant en adresses IP.</span><span class="sxs-lookup"><span data-stu-id="3a54c-108">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" /><span data-ttu-id="3a54c-110">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="3a54c-110">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3a54c-111">Pour des raisons de sécurité, nous vous recommandons de ne pas faire en sorte que vos serveurs Edge accèdent à un serveur DNS situé sur le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="3a54c-111">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="3a54c-112">Pour configurer des interfaces avec des serveurs DNS dans le réseau de périmètre</span><span class="sxs-lookup"><span data-stu-id="3a54c-112">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="3a54c-113">Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface côté interne et une pour l’interface côté externe.</span><span class="sxs-lookup"><span data-stu-id="3a54c-113">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3a54c-114">Les sous-réseaux interne et externe ne doivent pas être routables entre eux.</span><span class="sxs-lookup"><span data-stu-id="3a54c-114">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="3a54c-115">Sur l’interface externe, configurez trois adresses IP statiques sur le réseau de périmètre externe (également appelé DMZ, zone démilitarisée et sous-réseau filtré), puis pointez la passerelle par défaut vers l’interface interne du pare-feu externe.</span><span class="sxs-lookup"><span data-stu-id="3a54c-115">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="3a54c-116">Configurez les paramètres DNS de la carte pour qu’ils pointent vers une paire de serveurs DNS de périmètre.</span><span class="sxs-lookup"><span data-stu-id="3a54c-116">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a54c-117">Il est possible d’utiliser une seule adresse IP pour cette interface, mais pour ce faire, vous devez modifier les affectations de Port aux valeurs non standard.</span><span class="sxs-lookup"><span data-stu-id="3a54c-117">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="3a54c-118">Vous déterminez cela lorsque vous créez la topologie dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3a54c-118">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="3a54c-119">Sur l’interface interne, configurez une adresse IP statique sur le sous-réseau du réseau de périmètre interne et ne définissez pas de passerelle par défaut.</span><span class="sxs-lookup"><span data-stu-id="3a54c-119">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="3a54c-120">Configurez les paramètres DNS de la carte pour qu’ils pointent vers au moins un serveur DNS, de préférence une paire de serveurs DNS de périmètre.</span><span class="sxs-lookup"><span data-stu-id="3a54c-120">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="3a54c-121">Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes où résident les clients, Lync Server 2013 et les serveurs de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="3a54c-121">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="3a54c-122">Pour configurer des interfaces sans serveurs DNS dans le réseau de périmètre</span><span class="sxs-lookup"><span data-stu-id="3a54c-122">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="3a54c-123">Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface côté interne et une pour l’interface côté externe.</span><span class="sxs-lookup"><span data-stu-id="3a54c-123">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3a54c-124">Les sous-réseaux interne et externe ne doivent pas être routables entre eux.</span><span class="sxs-lookup"><span data-stu-id="3a54c-124">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="3a54c-125">Sur l’interface externe, configurez trois adresses IP statiques sur le sous-réseau du réseau de périmètre externe.</span><span class="sxs-lookup"><span data-stu-id="3a54c-125">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="3a54c-126">Vous configurez également la passerelle par défaut sur l’interface externe.</span><span class="sxs-lookup"><span data-stu-id="3a54c-126">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="3a54c-127">Par exemple, définissez le routeur accessible sur Internet ou le pare-feu externe comme passerelle par défaut.</span><span class="sxs-lookup"><span data-stu-id="3a54c-127">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="3a54c-128">Configurez les paramètres DNS pour qu’ils pointent vers un serveur DNS, de préférence vers une paire de serveurs DNS externes.</span><span class="sxs-lookup"><span data-stu-id="3a54c-128">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a54c-129">Il est possible, mais pas recommandé, de n’utiliser qu’une seule adresse IP pour l’interface externe.</span><span class="sxs-lookup"><span data-stu-id="3a54c-129">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="3a54c-130">Pour permettre cette opération, vous devez modifier les affectations de Port aux valeurs non standard, et loin du port 443 par défaut, généralement « pare-feu » pour la communication client.</span><span class="sxs-lookup"><span data-stu-id="3a54c-130">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="3a54c-131">Vous déterminez le paramètre de l’adresse IP et les paramètres de port lors de la création de la topologie dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3a54c-131">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="3a54c-132">Sur l’interface interne, configurez une adresse IP statique sur le sous-réseau du réseau de périmètre interne et ne définissez pas de passerelle par défaut.</span><span class="sxs-lookup"><span data-stu-id="3a54c-132">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="3a54c-133">Laissez les paramètres DNS de la carte vides.</span><span class="sxs-lookup"><span data-stu-id="3a54c-133">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="3a54c-134">Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes où résident les clients ou serveurs Lync exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a54c-134">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="3a54c-135">Modifiez le fichier hôte sur chaque serveur Edge de sorte qu’il contienne un enregistrement pour le serveur du tronçon suivant ou l’adresse IP virtuelle (VIP) (l’enregistrement sera le directeur, le serveur Standard Edition ou un pool frontal configuré en tant qu’adresse du tronçon suivant du serveur Edge dans le générateur de topologie).</span><span class="sxs-lookup"><span data-stu-id="3a54c-135">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="3a54c-136">Si vous utilisez l’équilibrage de la charge DNS, incluez une ligne pour chaque membre du pool du tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="3a54c-136">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

