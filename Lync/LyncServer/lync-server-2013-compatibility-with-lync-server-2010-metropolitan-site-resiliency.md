---
title: Compatibilité de Lync Server 2013 avec la résistance de site métropolitain de Lync Server 2010
description: Compatibilité de Lync Server 2013 avec la résistance de site métropolitain de Lync Server 2010.
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
ms.openlocfilehash: ec72f261ac593b24bad13dcd400f495ba7ba0722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576930"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="65706-103">Résilience de site métropolitain Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="65706-103">Lync Server 2010 metropolitan site resiliency</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65706-104">_**Dernière modification de la rubrique :** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="65706-104">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="65706-105">La solution de résistance de site métropolitain prise en charge pour Lync Server 2010 n’est pas prise en charge pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65706-105">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="65706-106">Cette solution nécessitait qu’un seul pool frontal couvre deux centres de données au sein de la même zone métropolitaine.</span><span class="sxs-lookup"><span data-stu-id="65706-106">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="65706-107">La solution de résistance de site métropolitain a été conçue pour effectuer une récupération à partir de la perte d’un centre de déplacement complet.</span><span class="sxs-lookup"><span data-stu-id="65706-107">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="65706-108">Lorsque vous englobez votre pool sur deux centres de ressources, vous placez généralement la moitié de vos serveurs frontaux dans un centre de de serveurs et l’autre moitié dans le deuxième centre de ressources.</span><span class="sxs-lookup"><span data-stu-id="65706-108">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="65706-109">Si vous perdez l’intégralité d’un centre de données, vous avez perdu la moitié de vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="65706-109">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="65706-110">Cela peut entraîner des problèmes avec le nouveau modèle de système distribué pour les pools frontaux dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65706-110">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="65706-111">Pour plus d’informations, voir [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="65706-111">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

