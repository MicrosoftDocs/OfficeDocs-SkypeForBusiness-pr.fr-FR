---
title: 'Lync Server 2013 : configuration des pare-feu et des ports pour l’accès des utilisateurs externes'
description: 'Lync Server 2013 : configurez les pare-feu et les ports pour l’accès des utilisateurs externes.'
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
ms.openlocfilehash: 68ccb382c3b3632b113b2b0a36846500700c1b9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553270"
---
# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="39c9a-103">Configurer les pare-feu et les ports pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39c9a-103">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39c9a-104">_**Dernière modification de la rubrique :** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="39c9a-104">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="39c9a-105">Vous devez configurer les pare-feu et les ports des serveurs Edge, des serveurs proxy inverses et éventuellement des programmes d’équilibrage de la charge matérielle (pour un déploiement mis à l’échelle sans équilibrage de la charge DNS).</span><span class="sxs-lookup"><span data-stu-id="39c9a-105">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="39c9a-106">Cette section fournit des informations sur la configuration requise des pare-feu et des ports pour tous les composants de serveur Edge, ainsi que la configuration des ports de pare-feu pour les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="39c9a-106">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="39c9a-107">Pour plus d’informations sur la configuration des ports pour les serveurs proxy inverses, voir [Setting up Reverse Proxy Servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span><span class="sxs-lookup"><span data-stu-id="39c9a-107">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="39c9a-108">Si vous déployez une topologie Edge à l’adaptation et que vous utilisez l’équilibrage de la charge matérielle au lieu de l’équilibrage de la charge DNS, reportez-vous à la section Edge consolidé avec montée en charge des programmes d’équilibrage de la charge matérielle [dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) dans la documentation de planification pour plus d’informations sur la configuration des ports pour les programmes d’équilibrage</span><span class="sxs-lookup"><span data-stu-id="39c9a-108">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="39c9a-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39c9a-109">See Also</span></span>


[<span data-ttu-id="39c9a-110">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39c9a-110">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

