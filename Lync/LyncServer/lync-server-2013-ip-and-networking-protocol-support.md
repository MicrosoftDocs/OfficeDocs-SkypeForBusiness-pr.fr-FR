---
title: 'Lync Server 2013 : Prise en charge du protocole IP et de gestion réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a35395c9bb7eb8d90e5618ba6afde17defdbbcfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="25e43-102">Prise en charge du protocole IP et de gestion réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25e43-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25e43-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="25e43-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="25e43-104">Lync Server 2013 prend en charge les protocoles IP et réseau suivants:</span><span class="sxs-lookup"><span data-stu-id="25e43-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="25e43-105">**Protocoles IP.**    Lync Server 2013 prend en charge les protocoles IP version 4 (IPv4) ou IP version 6 (IPv6) pour le réseau du serveur.</span><span class="sxs-lookup"><span data-stu-id="25e43-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25e43-106">Lync Server 2013 peut fonctionner dans un réseau doté d’une pile IP double activée.</span><span class="sxs-lookup"><span data-stu-id="25e43-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="25e43-107">**Protocoles de transport SIP.**    De manière générale, le protocole SIP peut utiliser au moins trois types de transport: protocole UDP (User Datagram Protocol), protocole TCP (Transmission Control Protocol) et TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="25e43-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="25e43-108">Dans la configuration de transport SIP par défaut, le protocole TLS s’exécute sur TCP.</span><span class="sxs-lookup"><span data-stu-id="25e43-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="25e43-109">TLS est utilisé au sein du réseau Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25e43-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="25e43-110">Au bord du réseau, Lync Server 2013 peut interagir via TCP.</span><span class="sxs-lookup"><span data-stu-id="25e43-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="25e43-111">Lync Server 2013 ne prend pas en charge le protocole UDP pour les transports SIP, car il ne respecte pas les normes minimales pour la sécurité, la fiabilité et l’évolutivité des communications d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="25e43-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="25e43-112">Pour plus d’informations, reportez-vous à l’article de blog NextHop, «au protocole UDP ou pas à UDP [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369), qui est la question «à.</span><span class="sxs-lookup"><span data-stu-id="25e43-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25e43-113">Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.</span><span class="sxs-lookup"><span data-stu-id="25e43-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

