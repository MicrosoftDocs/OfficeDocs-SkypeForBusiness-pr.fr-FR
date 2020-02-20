---
title: 'Lync Server 2013 : routage interjonction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce206c0f20dc00c6abc1304db8c1f933cbefdbca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="a2778-102">Routage interjonctions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2778-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2778-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a2778-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a2778-104">Lync Server 2013 peut interconnecter un PBX IP à une passerelle de réseau téléphonique commuté (PSTN) de sorte que les appels provenant d’un téléphone PBX puissent être acheminés vers le RTC et que les appels RTC entrants puissent être acheminés vers un téléphone PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="a2778-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="a2778-105">De même, Lync Server 2013 peut interconnecter deux systèmes IP-PBX ou plus afin que les appels puissent être passés et reçus entre les téléphones PBX à partir des différents systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="a2778-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="a2778-106">Cette fonctionnalité de routage interjonction peut être configurée à l’aide de la cmdlet Lync Server Management Shell, **Set-applet cstrunkconfiguration**, avec le nouveau paramètre PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="a2778-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="a2778-107">Ce paramètre spécifie l’ensemble d’enregistrements d’utilisation PSTN à utiliser.</span><span class="sxs-lookup"><span data-stu-id="a2778-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="a2778-108">Une jonction fait appel à cette utilisation PSTN pour déterminer un itinéraire et pour acheminer tous les appels entrants en conséquence.</span><span class="sxs-lookup"><span data-stu-id="a2778-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="a2778-109">Le diagramme suivant illustre Lync Server 2013 fournissant une interconnexion entre une passerelle PSTN et un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="a2778-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="a2778-110">**Routage d’inter-jonctions entre la passerelle et le système IP-PBX**</span><span class="sxs-lookup"><span data-stu-id="a2778-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="a2778-111">![Diagramme de passerelle RTC/IP-PBX de connexion Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagramme de passerelle RTC/IP-PBX de connexion Lync Server")</span><span class="sxs-lookup"><span data-stu-id="a2778-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="a2778-112">Le diagramme suivant illustre Lync Server 2013 interconnectant deux systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="a2778-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="a2778-113">**Routage d’inter-jonctions entre deux systèmes IP-PBXs**</span><span class="sxs-lookup"><span data-stu-id="a2778-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="a2778-114">![Diagramme de systèmes IP-PAX d’interconnexion de Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramme de systèmes IP-PAX d’interconnexion de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="a2778-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

