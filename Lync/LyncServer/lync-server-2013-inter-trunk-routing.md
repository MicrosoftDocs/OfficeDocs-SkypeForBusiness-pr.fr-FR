---
title: 'Lync Server 2013 : routage entre les jonctions'
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
ms.openlocfilehash: af9fd674a83eed898eddc47f8cc95114a29d54b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="1cd0f-102">Routage entre les jonctions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cd0f-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cd0f-103">_**Dernière modification de la rubrique :** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="1cd0f-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="1cd0f-104">Lync Server 2013 fournit une gestion de session de base par le biais de la prise en charge du routage interjonction.</span><span class="sxs-lookup"><span data-stu-id="1cd0f-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="1cd0f-105">Cette nouvelle fonctionnalité permet à Lync Server de fournir des fonctionnalités de contrôle d’appel aux systèmes téléphoniques en aval.</span><span class="sxs-lookup"><span data-stu-id="1cd0f-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="1cd0f-106">Le routage interjonction peut interconnecter un PBX IP à une passerelle de réseau téléphonique commuté (PSTN) afin que les appels provenant d’un téléphone PBX (Private Branch Exchange) puissent être acheminés vers le RTC et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="1cd0f-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="1cd0f-107">De même, Lync Server peut interconnecter deux ou plusieurs systèmes IP-PBX afin que les appels puissent être passés et reçus entre les téléphones PBX à partir des différents systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="1cd0f-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="1cd0f-108">La figure suivante illustre Lync Server 2013 fournissant une interconnexion entre une passerelle PSTN et un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="1cd0f-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="1cd0f-109">![Diagramme de passerelle RTC/IP-PBX de connexion Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagramme de passerelle RTC/IP-PBX de connexion Lync Server")</span><span class="sxs-lookup"><span data-stu-id="1cd0f-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="1cd0f-110">La figure suivante illustre la connexion de Lync Server 2013 à deux systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="1cd0f-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="1cd0f-111">![Diagramme de systèmes IP-PAX d’interconnexion de Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramme de systèmes IP-PAX d’interconnexion de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="1cd0f-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

