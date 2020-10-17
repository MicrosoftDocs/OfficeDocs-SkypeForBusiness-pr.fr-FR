---
title: 'Lync Server 2013 : contrôle d’admission des appels sur un réseau MPLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efed0826aa35a557628dd64bfdcea9bc22ced28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535177"
---
# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="b6277-102">Contrôle d’admission des appels sur un réseau MPLS avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6277-102">Call admission control on an MPLS network with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6277-103">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="b6277-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="b6277-p101">Dans un réseau MPLS (Multiprotocol Label Switching), tous les sites sont connectés par un maillage. C’est-à-dire que tous les sites sont connectés directement au segment principal MPLS du fournisseur de services Internet, chaque site recevant la bande passante à utiliser sur une liaison WAN au cloud MPLS. Il n’y a aucun concentrateur réseau ou site central pour contrôler le routage IP. La figure suivante montre un réseau simple basé sur la technologie MPLS.</span><span class="sxs-lookup"><span data-stu-id="b6277-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="b6277-108">**Exemple de réseau MPLS**</span><span class="sxs-lookup"><span data-stu-id="b6277-108">**Example MPLS network**</span></span>

<span data-ttu-id="b6277-109">![CAC avec MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC avec MPLS")</span><span class="sxs-lookup"><span data-stu-id="b6277-109">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="b6277-p102">Pour déployer le contrôle d’admission des appels dans un réseau MPLS, vous devez créer une région sur le réseau pour représenter le cloud MPLS et créer un site réseau pour représenter chaque site satellite MPLS. La figure suivante montre comment la région et les sites du réseau doivent être configurés pour représenter le réseau MPLS exemple dans la figure précédente. Les limites globales de bande passante et de session de bande passante sont ensuite basées sur la capacité de la liaison WAN de chaque site vers la région qui représente le cloud MPLS.</span><span class="sxs-lookup"><span data-stu-id="b6277-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="b6277-113">**Région et sites d’un réseau MPLS**</span><span class="sxs-lookup"><span data-stu-id="b6277-113">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="b6277-114">![Schéma de contrôle d’admission des appels (CAC, Call Admission Control) avec MPLS](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Schéma de contrôle d’admission des appels (CAC, Call Admission Control) avec MPLS")</span><span class="sxs-lookup"><span data-stu-id="b6277-114">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

