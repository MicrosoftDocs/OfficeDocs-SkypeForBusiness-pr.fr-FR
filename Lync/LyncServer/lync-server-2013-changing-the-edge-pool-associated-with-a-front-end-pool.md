---
title: 'Lync Server 2013 : Modification du pool de serveurs Edge associé à un pool de serveurs frontaux'
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
ms.openlocfilehash: 736ed552a51182102310f4e10eb28472b251eb22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="da696-102">Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da696-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da696-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="da696-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="da696-104">Si un pool de bords est en panne alors que le pool frontal sur le même site est toujours en cours d’exécution, vous devez définir le pool frontal pour qu’il utilise un pool de bords sur un autre site jusqu’à ce que le pool de frontière en panne soit restauré.</span><span class="sxs-lookup"><span data-stu-id="da696-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="da696-105">Modification de la liste de serveurs Edge associée à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="da696-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="da696-106">Dans le générateur de topologie, accédez au nom de la réserve frontale que vous devez modifier.</span><span class="sxs-lookup"><span data-stu-id="da696-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="da696-107">Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="da696-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="da696-108">Dans la section **associations** , sous **associer le pool de bords (pour les composants multimédias)**, utilisez la zone de liste déroulante pour sélectionner le pool de bords avec lequel vous voulez associer ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="da696-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="da696-109">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="da696-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da696-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da696-110">See Also</span></span>


[<span data-ttu-id="da696-111">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da696-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

