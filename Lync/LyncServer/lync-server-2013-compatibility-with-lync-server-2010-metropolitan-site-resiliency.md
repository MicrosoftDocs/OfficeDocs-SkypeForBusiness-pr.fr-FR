---
title: Compatibilité de Lync Server 2013 avec la résistance de sites métropolitains Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395ec568ebafea5c7a06e19340ff5ad10158ffb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="f7a2e-102">Résistance de sites métropolitains Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f7a2e-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a2e-103">_**Dernière modification de la rubrique :** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="f7a2e-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="f7a2e-104">La solution de résilience de site métropolitaine prise en charge pour Lync Server 2010 n’est pas prise en charge pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7a2e-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="f7a2e-105">Cette solution impliquait le fractionnement d’un pool frontal unique entre deux centres de données dans la même zone métropolitaine.</span><span class="sxs-lookup"><span data-stu-id="f7a2e-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="f7a2e-106">La solution de résilience du site métropolitain a été conçue pour être récupérée suite à la perte d’un datacenter complet.</span><span class="sxs-lookup"><span data-stu-id="f7a2e-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="f7a2e-107">Lorsque vous étendez votre réserve sur deux centres de serveurs, vous placez en général la moitié de vos extrémités au sein d’un centre de ressources et l’autre moitié dans le deuxième centre de ressources.</span><span class="sxs-lookup"><span data-stu-id="f7a2e-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="f7a2e-108">Si vous perdez l’intégralité d’un centre de données, vous avez perdu la moitié de vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="f7a2e-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="f7a2e-109">Cela peut poser des problèmes avec le nouveau modèle de système distribué pour les pools front-end dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7a2e-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="f7a2e-110">Pour plus d’informations, reportez-vous à la rubrique [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="f7a2e-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

