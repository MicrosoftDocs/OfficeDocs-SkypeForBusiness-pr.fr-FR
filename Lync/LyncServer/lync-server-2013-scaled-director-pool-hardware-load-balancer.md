---
title: 'Lync Server 2013 : Pool directeur mis à l’échelle - Équilibreur de charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0faf0983830466b44c91532f4fd80d72abb37fd7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="acf73-102">Pool directeur mis à l’échelle - Équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acf73-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acf73-103">_**Dernière modification de la rubrique:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="acf73-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="acf73-104">Dans le cas d’un pool de Directors mis à l’échelle, lorsque plusieurs Directors sont déployés pour gérer une capacité supplémentaire et de garantir une haute disponibilité, l’équilibrage de la charge des clients et du serveur doit être distribué auprès de tous les membres du pool.</span><span class="sxs-lookup"><span data-stu-id="acf73-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="acf73-105">Un directeur héberge des services Web de la même façon qu’un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="acf73-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="acf73-106">L’équilibrage de charge matérielle est requis pour les services Web.</span><span class="sxs-lookup"><span data-stu-id="acf73-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="acf73-107">Les rubriques suivantes décrivent les considérations en matière de planification pour le déploiement d’un pool de réalisateurs à l’aide de l’équilibrage de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="acf73-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="acf73-108">Si vous envisagez d’utiliser l’équilibrage de charge matérielle et l’équilibrage de charge DNS pour le pool de directeurs, voir la rubrique [pool de répertoires mis à l’échelle-équilibrage de charge DNS et équilibrage de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) qui décrit les exigences de planification pour cette topologie.</span><span class="sxs-lookup"><span data-stu-id="acf73-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="acf73-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb] (images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="acf73-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="acf73-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="acf73-110">In This Section</span></span>

  - [<span data-ttu-id="acf73-111">Résumé des certificats - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acf73-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="acf73-112">Résumé des ports - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acf73-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="acf73-113">Résumé DNS - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acf73-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

