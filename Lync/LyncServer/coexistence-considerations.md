---
title: Considérations relatives à la coexistence
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b31b8f3e534fc7b060f194f84310050a0386d8c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="b1e38-102">Considérations relatives à la coexistence</span><span class="sxs-lookup"><span data-stu-id="b1e38-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1e38-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b1e38-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b1e38-104">Après la migration, seul un pool de serveurs Lync Server 2013, persistent chat existe et vous pouvez mettre hors service votre déploiement hérité.</span><span class="sxs-lookup"><span data-stu-id="b1e38-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="b1e38-105">Avant la fin de la migration et avant que vous n’ayez désactivé entièrement votre déploiement actuel du serveur de conversation de groupe, vous pouvez avoir l’un des déploiements suivants :</span><span class="sxs-lookup"><span data-stu-id="b1e38-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="b1e38-106">Lync Server 2013, pool de serveurs de conversation permanente, qui doit être hébergé sur un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1e38-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="b1e38-107">Lync Server 2010, pool de conversation de groupe, qui doit être hébergé sur un pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b1e38-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="b1e38-108">Pool de conversation de groupe Office Communications Server 2007 R2, qui doit être hébergé sur un pool Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b1e38-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="b1e38-109">Ces déploiements peuvent exister côte à côte.</span><span class="sxs-lookup"><span data-stu-id="b1e38-109">These deployments can exist side by side.</span></span> <span data-ttu-id="b1e38-110">Toutefois, les catégories, les salles et les compléments d’un déploiement n’interagissent pas avec ceux du déploiement associé.</span><span class="sxs-lookup"><span data-stu-id="b1e38-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="b1e38-111">À l’aide de la configuration manuelle, un client hérité (client de conversation de groupe) peut se connecter à un pool à la fois pour Office Communications Server 2007 R2, Lync Server 2010, Group chat ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1e38-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="b1e38-112">Le Lync 2013 (client) ne peut interagir qu’avec le pool de serveurs Lync Server 2013, persistent chat, pas avec les pools de serveurs de conversation de groupe hérités.</span><span class="sxs-lookup"><span data-stu-id="b1e38-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="b1e38-113">Pour utiliser la conversation permanente dans un Lync 2013 (client), l’utilisateur doit être hébergé sur Lync 2013 et activé par la stratégie.</span><span class="sxs-lookup"><span data-stu-id="b1e38-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

