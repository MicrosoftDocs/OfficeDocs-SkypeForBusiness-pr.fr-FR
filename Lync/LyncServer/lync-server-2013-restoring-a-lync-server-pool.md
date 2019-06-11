---
title: 'Lync Server 2013: restauration d’un pool de serveurs Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4035ddb27b77e165d612be9e35cbb02970892c8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="0df04-102">Restauration d’un pool de serveurs Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0df04-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0df04-103">_**Dernière modification de la rubrique:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="0df04-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="0df04-104">Votre déploiement de Lync Server est susceptible de comprendre les types de pools suivants:</span><span class="sxs-lookup"><span data-stu-id="0df04-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="0df04-105">serveur frontal</span><span class="sxs-lookup"><span data-stu-id="0df04-105">Front End Server</span></span>

  - <span data-ttu-id="0df04-106">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="0df04-106">Mediation Server</span></span>

  - <span data-ttu-id="0df04-107">serveur de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="0df04-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="0df04-108">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="0df04-108">Edge Server</span></span>

<span data-ttu-id="0df04-109">Si un pool entier rencontre une panne, procédez comme suit pour chaque serveur membre du pool.</span><span class="sxs-lookup"><span data-stu-id="0df04-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="0df04-110">Dans le cas d’une réserve frontale, restaurez d’abord le serveur principal, puis restaurez chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="0df04-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="0df04-111">Pour plus d’informations, reportez-vous à la rubrique [restauration d’un serveur principal Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) et [restauration d’un serveur membre Enterprise Edition dans Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="0df04-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="0df04-112">Pour tous les autres types de pools, restaurez chaque serveur membre.</span><span class="sxs-lookup"><span data-stu-id="0df04-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="0df04-113">Pour plus d’informations, reportez-vous à la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="0df04-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

