---
title: Pool directeur mis à l’ampleur-équilibrage de charge DNS et équilibreur de charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af050cbef7c75bb7b403dc4ef74c4750a9e8b3c3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="b2c26-102">Pool directeur mis à l’ampleur-équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2c26-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2c26-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b2c26-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b2c26-104">Un pool directeur mis à l’ampleur, dans lequel plusieurs directeurs sont déployés pour gérer les capacités supplémentaires et pour fournir une haute disponibilité, nécessite un équilibrage de charge pour distribuer la communication client et serveur à tous les membres du pool.</span><span class="sxs-lookup"><span data-stu-id="b2c26-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="b2c26-105">Un directeur héberge des services Web de la même manière qu’un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b2c26-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="b2c26-106">Vous pouvez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS (Domain Name System) et l’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="b2c26-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="b2c26-107">L’équilibrage de la charge matérielle est nécessaire pour les services web et l’équilibrage de la charge DNS seul ne procure pas les fonctionnalités requises pour les services web.</span><span class="sxs-lookup"><span data-stu-id="b2c26-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="b2c26-108">Les rubriques suivantes décrivent les considérations relatives à la planification du déploiement d’un pool directeur à l’aide de l’équilibrage de charge DNS en association avec l’équilibrage de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="b2c26-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="b2c26-109">Si vous envisagez d’utiliser l’équilibrage de charge matérielle, mais pas l’équilibrage de charge DNS pour le pool Directeur, reportez-vous à la rubrique [pool directord directord-équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) qui décrit les exigences de planification pour cette topologie.</span><span class="sxs-lookup"><span data-stu-id="b2c26-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="b2c26-110">![Pool directeur mis à l’échelle](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool directeur mis à l’échelle")</span><span class="sxs-lookup"><span data-stu-id="b2c26-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b2c26-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b2c26-111">In This Section</span></span>

  - [<span data-ttu-id="b2c26-112">Résumé des certificats-charge DNS et charge matérielle équilibrée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2c26-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="b2c26-113">Résumé des ports-équilibrage de charge DNS et charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2c26-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="b2c26-114">Résumé des enregistrements DNS-charge DNS et charge matérielle équilibrée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2c26-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

