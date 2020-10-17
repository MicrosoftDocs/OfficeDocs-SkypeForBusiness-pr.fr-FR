---
title: 'Lync Server 2013 : délégation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b31224228a4f2fbdad879e43bab61292852e009c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516302"
---
# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="b5678-102">Délégation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5678-102">Delegation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5678-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="b5678-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="b5678-104">Les fonctionnalités de délégation de Lync sont affectées par le routage de Location-Based de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="b5678-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="b5678-105">Lorsqu’un délégué activé pour le routage des Location-Based passe un appel au nom d’un responsable, la stratégie de voix du délégué est utilisée pour autoriser l’appel et la stratégie de routage des communications vocales du site délégué sera utilisée pour acheminer l’appel.</span><span class="sxs-lookup"><span data-stu-id="b5678-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="b5678-106">Pour les appels RTC entrants vers un responsable, les règles applicables au transfert d’appel ou à la sonnerie simultanée s’appliquent comme décrit dans les rubriques transfert d’appel et transfert et sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="b5678-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="b5678-107">Lorsqu’un délégué définit un point de terminaison PSTN en tant que cible de la sonnerie simultanée, pour un appel entrant vers le responsable, la stratégie de routage des communications vocales du site associé à la jonction entrante est utilisée pour acheminer l’appel vers le point de terminaison PSTN du délégué.</span><span class="sxs-lookup"><span data-stu-id="b5678-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="b5678-108">Pour la délégation, il est recommandé que le gestionnaire et ses délégués associés soient généralement situés dans le même site réseau.</span><span class="sxs-lookup"><span data-stu-id="b5678-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b5678-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5678-109">See Also</span></span>


[<span data-ttu-id="b5678-110">Scénarios de routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5678-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

