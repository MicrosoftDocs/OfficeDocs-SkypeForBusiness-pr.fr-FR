---
title: 'Lync Server 2013 : prise en charge du protocole IP et du réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d413c53f8f6600170cf7ec7bfdcca8b052101eca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="1a0bf-102">Prise en charge des protocoles IP et réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a0bf-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a0bf-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1a0bf-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1a0bf-104">Lync Server 2013 prend en charge les protocoles IP et de mise en réseau suivants :</span><span class="sxs-lookup"><span data-stu-id="1a0bf-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="1a0bf-105">**Protocoles IP.**    Lync Server 2013 prend en charge IP version 4 (IPv4) ou IP version 6 (IPv6) pour le réseau de serveurs.</span><span class="sxs-lookup"><span data-stu-id="1a0bf-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a0bf-106">Lync Server 2013 peut fonctionner dans un réseau avec une pile IP double activée.</span><span class="sxs-lookup"><span data-stu-id="1a0bf-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="1a0bf-107">**Protocoles de transport SIP.**    De manière générique, SIP peut utiliser au moins trois types de transport : UDP (User Datagram Protocol), TCP (Transmission Control Protocol) et TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="1a0bf-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="1a0bf-108">Dans la configuration de transport SIP par défaut, le protocole TLS prévaut sur TCP.</span><span class="sxs-lookup"><span data-stu-id="1a0bf-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="1a0bf-109">TLS est utilisé dans le réseau Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a0bf-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="1a0bf-110">Sur le serveur Edge du réseau, Lync Server 2013 peut interagir sur TCP.</span><span class="sxs-lookup"><span data-stu-id="1a0bf-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="1a0bf-111">Lync Server 2013 ne prend pas en charge le protocole UDP pour le transport SIP car il ne respecte pas les normes minimales pour la sécurité, la fiabilité et l’évolutivité des communications d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a0bf-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="1a0bf-112">Pour plus d’informations, reportez-vous à l’article du blog NextHop, « vers UDP, ou non à UDP [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369), qui est la question » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1a0bf-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a0bf-113">Le contenu de chaque blog et les URL correspondantes peuvent faire l'objet de modifications sans préavis.</span><span class="sxs-lookup"><span data-stu-id="1a0bf-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

