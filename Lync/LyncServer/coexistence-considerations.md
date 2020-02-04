---
title: Remarques liées à la coexistence
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
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="f220f-102">Remarques liées à la coexistence</span><span class="sxs-lookup"><span data-stu-id="f220f-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f220f-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f220f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f220f-104">Après la migration, vous n’aurez qu’un seul Lync Server 2013, le pool de serveurs de conversation permanent et vous pourrez désactiver votre déploiement hérité.</span><span class="sxs-lookup"><span data-stu-id="f220f-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="f220f-105">Avant la fin de la migration et avant d’avoir désactivé entièrement le déploiement de votre serveur de discussion de groupe actuel, il est possible que vous disposiez de l’un des déploiements suivants :</span><span class="sxs-lookup"><span data-stu-id="f220f-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="f220f-106">Lync Server 2013, pool de serveurs de chat permanent, qui doit être hébergé sur un pool 2013 serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="f220f-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="f220f-107">Lync Server 2010, pool de discussion de groupe, qui doit être hébergé sur un pool 2010 serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="f220f-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="f220f-108">Pool de discussion de groupe Office Communications Server 2007 R2, qui doit être hébergé sur un pool Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f220f-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="f220f-109">Ces déploiements peuvent exister côte à côte.</span><span class="sxs-lookup"><span data-stu-id="f220f-109">These deployments can exist side by side.</span></span> <span data-ttu-id="f220f-110">Toutefois, les catégories, les salles et les compléments dans un seul déploiement n’interagissent pas avec celles du déploiement associé.</span><span class="sxs-lookup"><span data-stu-id="f220f-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="f220f-111">À l’aide de la configuration manuelle, un client hérité (client de discussion de groupe) peut se connecter à un pool à la fois pour Office Communications Server 2007 R2, Lync Server 2010, discussion de groupe ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f220f-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="f220f-112">Le client Lync 2013 (client) peut interagir uniquement avec Lync Server 2013, le pool de serveurs de chat permanent, et non avec les pools de serveurs de chat de groupe hérités.</span><span class="sxs-lookup"><span data-stu-id="f220f-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="f220f-113">Pour utiliser la conversation permanente dans une 2013 Lync (client), l’utilisateur doit être hébergé sur Lync 2013 et activé par la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f220f-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

