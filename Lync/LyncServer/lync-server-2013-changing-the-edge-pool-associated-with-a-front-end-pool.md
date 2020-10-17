---
title: 'Lync Server 2013 : modification du pool de serveurs Edge associé à un pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32404f911766da3ea0f47b74011b4806edbca231
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517881"
---
# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="56d95-102">Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56d95-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56d95-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="56d95-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="56d95-104">Si un pool de serveurs Edge est défaillant mais que le pool de serveurs frontaux du même site fonctionne encore, vous devrez définir le pool de serveurs frontaux pour qu’il utilise le pool de serveurs Edge d’un autre site jusqu’à ce que le pool de serveurs Edge défaillant soit restauré.</span><span class="sxs-lookup"><span data-stu-id="56d95-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="56d95-105">Changement du pool de serveurs Edge associé à un pool de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="56d95-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="56d95-106">Dans le Générateur de topologie, accédez au nom du pool de serveurs frontaux que vous devez changer.</span><span class="sxs-lookup"><span data-stu-id="56d95-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="56d95-107">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="56d95-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="56d95-108">Dans la section **Associations**, sous **Associer le pool de serveurs Edge (pour les composants multimédias)**, utilisez la zone de liste déroulante pour sélectionner le pool de serveurs Edge que vous voulez associer à ce pool de serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="56d95-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="56d95-109">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="56d95-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56d95-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56d95-110">See Also</span></span>


[<span data-ttu-id="56d95-111">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56d95-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

