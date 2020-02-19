---
title: 'Lync Server 2013 : composants requis pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a87fa004cabe90d8a4dc79771295af8fc61a2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="a6fcc-102">Composants requis pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6fcc-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6fcc-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a6fcc-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a6fcc-104">Le seul composant requis pour créer et configurer un directeur est de déployer le rôle serveur directeur.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="a6fcc-105">Pour ce faire, utilisez le générateur de topologie et définissez un seul pool d’ordinateurs ou un pool de plusieurs ordinateurs dans le nœud du pool directeur.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="a6fcc-106">Une fois que vous avez défini le directeur ou le pool Directeur, exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur qui sera directeur.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="a6fcc-107">Dans le cas d’un pool Directeur, exécutez l’Assistant Déploiement Lync Server sur chaque serveur qui sera membre du pool.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="a6fcc-108">Topologies</span><span class="sxs-lookup"><span data-stu-id="a6fcc-108">Topologies</span></span>

<span data-ttu-id="a6fcc-109">Vous pouvez implémenter un serveur directeur ou un pool directeur.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="a6fcc-110">Le directeur est toujours un serveur ou pool distinct, non colocalisé avec un autre rôle serveur dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6fcc-111">Si vous ne déployez pas les directeurs, le serveur frontal ou le pool frontal assumera le rôle de directeur.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="a6fcc-112">Un pool de directeurs doit être équilibré en charge.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="a6fcc-113">Vous pouvez effectuer l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6fcc-113">You can do one of the following:</span></span>

  - <span data-ttu-id="a6fcc-114">Créez une topologie qui utilise un équilibreur de la charge matérielle pour les services web et un équilibrage de la charge DNS (Domain Name System) pour les autres types de trafic.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="a6fcc-115">Pool directeur mis à l’ampleur-équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6fcc-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="a6fcc-116">Créez une topologie qui utilise un équilibreur de charge matérielle pour l’équilibrage de charge nécessaire pour le pool directeur.</span><span class="sxs-lookup"><span data-stu-id="a6fcc-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="a6fcc-117">Pool directeur mis à l’ampleur-équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6fcc-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

