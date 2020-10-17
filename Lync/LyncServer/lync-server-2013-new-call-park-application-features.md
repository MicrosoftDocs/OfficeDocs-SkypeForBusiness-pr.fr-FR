---
title: 'Lync Server 2013 : nouvelles fonctionnalités de l’application de parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Call Park application features
ms:assetid: bddff13c-92cc-47fd-bfd4-6e8bfbfed11b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412927(v=OCS.15)
ms:contentKeyID: 48185277
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4210eb5560563c9ef509bb6c4c5256f8b885a6e5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505331"
---
# <a name="new-call-park-application-features-in-lync-server-2013"></a><span data-ttu-id="e6847-102">Nouvelles fonctionnalités de l’application de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6847-102">New Call Park application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6847-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="e6847-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="e6847-104">L’application de parcage d’appel permet aux utilisateurs de voix entreprise de mettre un appel en attente, puis de les récupérer ultérieurement à partir de n’importe quel téléphone.</span><span class="sxs-lookup"><span data-stu-id="e6847-104">The Call Park application makes it possible for Enterprise Voice users to put a call on hold and then retrieve it later from any phone.</span></span> <span data-ttu-id="e6847-105">L’utilisateur qui a parqué l’appel peut composer le numéro d’orbite fourni par le parcage d’appel pour extraire l’appel parqué ou utiliser un mécanisme externe, tel que la messagerie instantanée ou un système de radiomessagerie, pour demander à d’autres utilisateurs de récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="e6847-105">The user who parked the call can either dial the orbit number provided by Call Park to retrieve the parked call or use an external mechanism, such as instant messaging (IM) or a paging system, to ask someone else to retrieve the call.</span></span>

<span data-ttu-id="e6847-106">Lync Server 2013 fournit de nouveaux mécanismes de récupération d’urgence sous la forme de processus de basculement et de restauration automatique.</span><span class="sxs-lookup"><span data-stu-id="e6847-106">Lync Server 2013 provides new disaster recovery mechanisms in the form of failover and failback processes.</span></span> <span data-ttu-id="e6847-107">Ces processus de basculement et de retour arrière prennent en charge la récupération de la fonctionnalité de parcage d’appel en permettant aux utilisateurs hébergés dans le pool principal de tirer parti de l’application de parcage d’appel du pool de sauvegarde lorsqu’une panne se produit dans le pool principal.</span><span class="sxs-lookup"><span data-stu-id="e6847-107">These failover and failback processes support recovery of Call Park functionality by allowing users who are homed in the primary pool to leverage the Call Park application of the backup pool when an outage occurs in the primary pool.</span></span> <span data-ttu-id="e6847-108">La prise en charge de la récupération d’urgence de l’application de parcage d’appel est activée dans le cadre de la configuration et du déploiement des pools frontaux couplés.</span><span class="sxs-lookup"><span data-stu-id="e6847-108">Support for disaster recovery of the Call Park application is enabled as part of the configuration and deployment of paired Front End pools.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e6847-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6847-109">See Also</span></span>


[<span data-ttu-id="e6847-110">Planification du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6847-110">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

