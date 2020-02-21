---
title: 'Lync Server 2013 : scénarios pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e82794de791ce53e3a87dce374cbdc860f27040
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="ed6a7-102">Scénarios pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6a7-102">Scenarios for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed6a7-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ed6a7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ed6a7-104">Un directeur est un serveur exécutant un logiciel de communication Microsoft Lync Server 2013 pouvant authentifier les demandes des utilisateurs, mais qui n’héberge pas de comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ed6a7-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="ed6a7-105">Le directeur héberge également des services Web similaires au serveur frontal et authentifiera les demandes de ticket Web et fournira d’autres services.</span><span class="sxs-lookup"><span data-stu-id="ed6a7-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed6a7-106">Si vous déployez des directeurs, vous devez publier les services Web Director en externe via le proxy inverse, ainsi que les services Web du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="ed6a7-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="ed6a7-107">Les rubriques suivantes décrivent le processus de planification pour les topologies de directeur possibles.</span><span class="sxs-lookup"><span data-stu-id="ed6a7-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed6a7-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ed6a7-108">In This Section</span></span>

  - [<span data-ttu-id="ed6a7-109">Vue d’ensemble du directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6a7-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="ed6a7-110">Composants requis pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6a7-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="ed6a7-111">Configuration matérielle et logicielle requise pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6a7-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="ed6a7-112">Directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6a7-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="ed6a7-113">Pool directeur mis à l’ampleur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6a7-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed6a7-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed6a7-114">See Also</span></span>


[<span data-ttu-id="ed6a7-115">Topologies prises en charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6a7-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="ed6a7-116">Plateformes matérielles de serveur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6a7-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

