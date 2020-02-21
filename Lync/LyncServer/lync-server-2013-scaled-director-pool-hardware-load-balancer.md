---
title: 'Lync Server 2013 : pool directeur mis à l’envergure-équilibreur de charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 178408e29e794fe39241920d715e271fc84f1c17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="f1b28-102">Pool directeur mis à l’ampleur-équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b28-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1b28-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f1b28-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f1b28-104">Un pool directeur mis à l’ampleur, dans lequel plusieurs directeurs sont déployés pour gérer les capacités supplémentaires et offrir une haute disponibilité, nécessite un équilibrage de charge pour distribuer la communication client et serveur à tous les membres du pool.</span><span class="sxs-lookup"><span data-stu-id="f1b28-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="f1b28-105">Un directeur héberge des services Web de la même manière qu’un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f1b28-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="f1b28-106">L’équilibrage de la charge matérielle est requis pour les services web.</span><span class="sxs-lookup"><span data-stu-id="f1b28-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="f1b28-107">Les rubriques suivantes décrivent les considérations relatives à la planification du déploiement d’un pool directeur à l’aide de l’équilibrage de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="f1b28-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="f1b28-108">Si vous envisagez d’utiliser l’équilibrage de charge matérielle et l’équilibrage de charge DNS pour le pool Directeur, consultez la rubrique [pool directeur mis à l’esprit-équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) , qui décrit les exigences de planification de cette topologie.</span><span class="sxs-lookup"><span data-stu-id="f1b28-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="f1b28-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="f1b28-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f1b28-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f1b28-110">In This Section</span></span>

  - [<span data-ttu-id="f1b28-111">Résumé des certificats-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b28-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="f1b28-112">Résumé des ports-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b28-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="f1b28-113">Résumé DNS-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b28-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

