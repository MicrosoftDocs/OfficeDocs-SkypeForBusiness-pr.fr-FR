---
title: 'Lync Server 2013 : composants et topologies pour la jonction SIP'
description: 'Lync Server 2013 : composants et topologies pour la jonction SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d9c826539084a539d3efe7f143c335ec6d8f62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549520"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="42b66-103">Composants et topologies pour la jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b66-103">Components and topologies for SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42b66-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="42b66-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="42b66-105">La figure suivante illustre la topologie de jonction SIP dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42b66-105">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="42b66-106">**Topologie de jonction SIP**</span><span class="sxs-lookup"><span data-stu-id="42b66-106">**SIP trunking topology**</span></span>

<span data-ttu-id="42b66-107">![Topologie de jonction SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologie de jonction SIP")</span><span class="sxs-lookup"><span data-stu-id="42b66-107">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="42b66-p101">Comme le montre le diagramme, un réseau privé virtuel (VPN) IP est utilisé pour la connectivité entre le réseau d’entreprise et le fournisseur de services de réseau téléphonique commuté. L’objectif de ce réseau privé est de fournir la connectivité IP, d’améliorer la sécurité et (éventuellement) d’obtenir des garanties de qualité de service. En raison de la nature d’un VPN, vous n’avez pas besoin d’utiliser TLS pour le trafic de signalisation SIP, ni SRTP pour le trafic multimédia. De ce fait, les connexions entre l’entreprise et le fournisseur de services consistent en des connexions TCP ordinaires pour SIP et des connexions RTP ordinaires (avec le protocole UDP) pour les médias traités par tunnel via un réseau VPN IP. Veillez à ce que tous les pare-feu situés entre les routeurs VPN disposent de ports ouverts pour permettre aux routeurs VPN de communiquer. Par ailleurs, les adresses IP des périmètres externes des routeurs VPN doivent être publiquement routables.</span><span class="sxs-lookup"><span data-stu-id="42b66-p101">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="42b66-113">Contactez votre fournisseur de services pour déterminer s’il fournit la prise en charge pour la disponibilité élevée, notamment le basculement.</span><span class="sxs-lookup"><span data-stu-id="42b66-113">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="42b66-114">Si c’est le cas, vous devrez déterminer les procédures pour la configurer.</span><span class="sxs-lookup"><span data-stu-id="42b66-114">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="42b66-115">Par exemple, avez-vous besoin de configurer une seule adresse IP et une jonction SIP sur chaque serveur de médiation, ou devez-vous configurer plusieurs jonctions SIP sur chaque serveur de médiation ?</span><span class="sxs-lookup"><span data-stu-id="42b66-115">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="42b66-116">Si vous disposez de plusieurs sites centraux, demandez également à votre fournisseur de services s’il a la possibilité d’activer les connexions vers et à partir d’un autre site central.</span><span class="sxs-lookup"><span data-stu-id="42b66-116">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="42b66-117">Pour la jonction SIP, nous vous recommandons vivement de déployer les serveurs de médiation autonomes.</span><span class="sxs-lookup"><span data-stu-id="42b66-117">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="42b66-118">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Defining Peers in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="42b66-118">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="42b66-119">Sécurisation du serveur de médiation pour la jonction SIP</span><span class="sxs-lookup"><span data-stu-id="42b66-119">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="42b66-p104">Pour des raisons de sécurité, vous devriez configurer un réseau local virtuel (VLAN) pour chaque connexion entre deux routeurs VPN. Le processus courant de configuration d’un VLAN varie d’un fabricant de routeur à l’autre. Pour plus d’informations, contactez le fournisseur de votre routeur.</span><span class="sxs-lookup"><span data-stu-id="42b66-p104">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="42b66-123">Nous vous conseillons de suivre les directives suivantes :</span><span class="sxs-lookup"><span data-stu-id="42b66-123">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="42b66-124">Configurez un réseau local virtuel (VLAN) entre le serveur de médiation et le routeur VPN dans le réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré).</span><span class="sxs-lookup"><span data-stu-id="42b66-124">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="42b66-125">N’autorisez pas le transfert des paquets de diffusions ou de multidiffusions entre le routeur et le réseau local virtuel.</span><span class="sxs-lookup"><span data-stu-id="42b66-125">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="42b66-126">Bloquez toutes les règles de routage qui acheminent le trafic du routeur vers n’importe où mais sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="42b66-126">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="42b66-127">Si vous utilisez un serveur VPN, bous vous conseillons de suivre les directives suivantes :</span><span class="sxs-lookup"><span data-stu-id="42b66-127">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="42b66-128">Configurez un réseau local virtuel entre le serveur VPN et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="42b66-128">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="42b66-129">N’autorisez pas la transmission des paquets de diffusions ou de multidiffusions du serveur VPN vers le réseau local virtuel.</span><span class="sxs-lookup"><span data-stu-id="42b66-129">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="42b66-130">Bloquez toute règle de routage qui achemine le trafic de serveur VPN vers n’importe quel emplacement, mais sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="42b66-130">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="42b66-131">Chiffrez les données sur le réseau privé virtuel (VPN) à l’aide de l’encapsulation générique de routage (GRE).</span><span class="sxs-lookup"><span data-stu-id="42b66-131">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

