---
title: 'Lync Server 2013 : routage inter-Trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a9feb818f48317f9a3dddd78a70700e3f6ccfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="d045a-102">Routage inter-Trunk dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d045a-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d045a-103">_**Dernière modification de la rubrique :** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="d045a-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="d045a-104">Lync Server 2013 fournit une gestion de session de base grâce à la prise en charge du routage intertrunk.</span><span class="sxs-lookup"><span data-stu-id="d045a-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="d045a-105">Cette nouvelle fonctionnalité permet à Lync Server de fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval.</span><span class="sxs-lookup"><span data-stu-id="d045a-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="d045a-106">Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="d045a-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="d045a-107">De la même façon, Lync Server peut interconnecter au moins deux systèmes IP-PBX pour que les appels puissent être placés et reçus entre les téléphones PBX des différents systèmes IP PBX.</span><span class="sxs-lookup"><span data-stu-id="d045a-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="d045a-108">La figure suivante illustre Lync Server 2013 permettant une interconnexion entre une passerelle RTC et un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="d045a-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="d045a-109">![Diagramme IP-PBX/Passerelle RTC connectant Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagramme IP-PBX/Passerelle RTC connectant Lync Server")</span><span class="sxs-lookup"><span data-stu-id="d045a-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="d045a-110">La figure suivante illustre Lync Server 2013 connectant deux systèmes PBX IP.</span><span class="sxs-lookup"><span data-stu-id="d045a-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="d045a-111">![Diagramme IP-PBX/Passerelle RTC interconnectant Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramme IP-PBX/Passerelle RTC interconnectant Lync Server")</span><span class="sxs-lookup"><span data-stu-id="d045a-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

