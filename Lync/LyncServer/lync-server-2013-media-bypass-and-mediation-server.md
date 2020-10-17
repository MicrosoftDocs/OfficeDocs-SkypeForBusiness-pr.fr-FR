---
title: 'Lync Server 2013 : contournement de média et serveur de médiation'
description: 'Lync Server 2013 : contournement de média et serveur de médiation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb005d3d52fa9e5a38fdf56a65dfcbd73616d87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556430"
---
# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="987d9-103">Contournement de média et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="987d9-103">Media bypass and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="987d9-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="987d9-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="987d9-105">La déviation du trafic multimédia est une fonctionnalité Lync Server qui permet à un administrateur de configurer le routage des appels pour qu’il circule directement entre le point de terminaison de l’utilisateur et la passerelle PSTN sans traverser le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="987d9-105">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="987d9-106">La déviation du trafic multimédia améliore la qualité des appels en réduisant la latence, la traduction inutile, la perte de paquets possible et le nombre de points de défaillance potentiels.</span><span class="sxs-lookup"><span data-stu-id="987d9-106">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="987d9-107">Lorsqu’un site distant sans serveur de médiation est connecté à un site central par une ou plusieurs liaisons de réseau étendu avec une bande passante limitée, le contournement de média diminue la bande passante requise en permettant à un client situé sur un site distant de circuler directement vers sa passerelle locale sans avoir préalablement à passer par la liaison de réseau étendu à un serveur de médiation sur le site central. Cette réduction du traitement multimédia complète également la capacité du serveur de médiation à contrôler plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="987d9-107">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="987d9-p102">Le contournement de média et le contrôle d’admission des appels s’excluent mutuellement. Si le contournement de média est utilisé pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="987d9-p102">Media bypass and call admission control (CAC) are mutually exclusive. If media bypass is employed for a call, CAC is not performed for that call. The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="987d9-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="987d9-111">See Also</span></span>


[<span data-ttu-id="987d9-112">Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="987d9-112">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="987d9-113">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="987d9-113">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

