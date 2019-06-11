---
title: 'Lync Server 2013 : Routage interjonctions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="5724d-102">Routage interjonctions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5724d-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5724d-103">_**Dernière modification de la rubrique:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="5724d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5724d-104">Lync Server 2013 peut interconnecter un PBX IP à une passerelle RTC (réseau téléphonique commuté) pour que les appels d’un téléphone PBX puissent être routés vers le RTC et que les appels RTC entrants puissent être routés vers un téléphone PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="5724d-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="5724d-105">De la même façon, Lync Server 2013 peut interconnecter au moins deux systèmes IP-PBX pour que les appels puissent être placés et reçus entre les téléphones PBX des différents systèmes IP PBX.</span><span class="sxs-lookup"><span data-stu-id="5724d-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="5724d-106">Cette fonctionnalité de routage intertrunk peut être configurée à l’aide de la cmdlet Lync Server Management Shell, **Set-CsTrunkConfiguration**, avec le nouveau paramètre PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="5724d-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="5724d-107">Ce paramètre spécifie l’ensemble d’enregistrements d’utilisation RTC à utiliser.</span><span class="sxs-lookup"><span data-stu-id="5724d-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="5724d-108">Un Trunk utilise cette utilisation PSTN pour déterminer un itinéraire et acheminer tous les appels entrants en conséquence.</span><span class="sxs-lookup"><span data-stu-id="5724d-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="5724d-109">Le diagramme suivant illustre Lync Server 2013 permettant une interconnexion entre une passerelle RTC et un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="5724d-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="5724d-110">**Routage intertrunk entre passerelle et PBX IP**</span><span class="sxs-lookup"><span data-stu-id="5724d-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="5724d-111">![Lync Server Connection RTC passerelle/PBX IP] (images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server Connection RTC passerelle/PBX IP")</span><span class="sxs-lookup"><span data-stu-id="5724d-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="5724d-112">Le diagramme suivant illustre Lync Server 2013 qui interconnecte deux systèmes PBX IP.</span><span class="sxs-lookup"><span data-stu-id="5724d-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="5724d-113">**Routage intertrunk entre deux PBX IP**</span><span class="sxs-lookup"><span data-stu-id="5724d-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="5724d-114">![Diagramme de systèmes IP-Pax d’interconnexion de Lync Server] (images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramme de systèmes IP-Pax d’interconnexion de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="5724d-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

