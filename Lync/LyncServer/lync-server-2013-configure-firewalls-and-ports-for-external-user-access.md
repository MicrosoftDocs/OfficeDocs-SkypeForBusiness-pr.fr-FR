---
title: 'Lync Server 2013 : Configuration des pare-feux et des ports pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142488d35c3d5afa988be11baa688849065df066
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="6c333-102">Configuration des pare-feux et des ports pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c333-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c333-103">_**Dernière modification de la rubrique:** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="6c333-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="6c333-104">Pour configurer des pare-feu et des ports, vous devez les configurer pour les serveurs de périphérie, des serveurs proxy inversés et éventuellement des équilibreurs de charge matérielle (pour un déploiement mis à l’échelle qui n’utilise pas l’équilibrage de charge DNS).</span><span class="sxs-lookup"><span data-stu-id="6c333-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="6c333-105">Cette section fournit des informations sur les exigences en matière de pare-feu et de port pour tous les composants Edge Server et la configuration des ports de pare-feu pour les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="6c333-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="6c333-106">Pour plus d’informations sur la configuration des ports pour les serveurs proxy inverse, voir [configuration de serveurs proxy inverse pour Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6c333-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="6c333-107">Si vous déployez une topologie latérale mise à l’échelle et que vous utilisez l’équilibrage de charge matérielle au lieu de l’équilibrage de charge DNS, voir [périphérie consolidée à l’échelle du matériel dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) dans la documentation de planification pour plus d’informations sur la configuration ports pour les équilibreurs de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="6c333-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6c333-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c333-108">See Also</span></span>


[<span data-ttu-id="6c333-109">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c333-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

