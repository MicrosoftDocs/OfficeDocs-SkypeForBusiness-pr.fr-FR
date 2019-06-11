---
title: 'Lync Server 2013 : Déviation du trafic multimédia et serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="8cf26-102">Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cf26-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cf26-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8cf26-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8cf26-104">La fonctionnalité de contournement de média est une fonctionnalité de serveur Lync qui permet à un administrateur de configurer le routage des appels pour qu’il passe directement entre le point de terminaison de l’utilisateur et la passerelle RTC (réseau téléphonique commuté) sans traverser le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="8cf26-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="8cf26-105">La dérivation de médias améliore la qualité des appels en réduisant la latence, la traduction inutile, le risque de perte de paquets et le nombre de points de défaillance potentiels.</span><span class="sxs-lookup"><span data-stu-id="8cf26-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="8cf26-106">Dans le cas où un site distant dépourvu d’un serveur de médiation est connecté à un site central par le biais d’un ou de plusieurs liens WAN dotés de la bande passante contrainte, le contournement du contenu multimédia limite les exigences de bande passante en permettant à un client distant tout d’abord, le lien réseau étendu doit être transmis à un serveur de médiation sur le site central. Cette réduction du traitement des contenus multimédias complète également la capacité du serveur de médiation à contrôler plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="8cf26-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="8cf26-p102">La déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement. Si la déviation du trafic multimédia est utilisée pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="8cf26-p102">Media bypass and call admission control (CAC) are mutually exclusive. If media bypass is employed for a call, CAC is not performed for that call. The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8cf26-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8cf26-110">See Also</span></span>


[<span data-ttu-id="8cf26-111">Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cf26-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="8cf26-112">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cf26-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

