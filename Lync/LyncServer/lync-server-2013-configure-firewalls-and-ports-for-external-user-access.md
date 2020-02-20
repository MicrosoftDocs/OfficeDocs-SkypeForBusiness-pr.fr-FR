---
title: 'Lync Server 2013 : configuration des pare-feu et des ports pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308aa75c2d2877f9d2fe2b79df66856756586f20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="8e2ea-102">Configurer les pare-feu et les ports pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e2ea-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e2ea-103">_**Dernière modification de la rubrique :** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="8e2ea-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="8e2ea-104">Vous devez configurer les pare-feu et les ports des serveurs Edge, des serveurs proxy inverses et éventuellement des programmes d’équilibrage de la charge matérielle (pour un déploiement mis à l’échelle sans équilibrage de la charge DNS).</span><span class="sxs-lookup"><span data-stu-id="8e2ea-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="8e2ea-105">Cette section fournit des informations sur la configuration requise des pare-feu et des ports pour tous les composants de serveur Edge, ainsi que la configuration des ports de pare-feu pour les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="8e2ea-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="8e2ea-106">Pour plus d’informations sur la configuration des ports pour les serveurs proxy inverses, voir [Setting up Reverse Proxy Servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span><span class="sxs-lookup"><span data-stu-id="8e2ea-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="8e2ea-107">Si vous déployez une topologie Edge à l’adaptation et que vous utilisez l’équilibrage de la charge matérielle au lieu de l’équilibrage de la charge DNS, reportez-vous à la section Edge consolidé avec montée en charge des programmes d’équilibrage de la charge matérielle [dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) dans la documentation de planification pour plus d’informations sur la configuration des ports pour les programmes d’équilibrage</span><span class="sxs-lookup"><span data-stu-id="8e2ea-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8e2ea-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e2ea-108">See Also</span></span>


[<span data-ttu-id="8e2ea-109">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e2ea-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

