---
title: 'Lync Server 2013: routage en fonction de l’emplacement pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ee4c8f996315ede0fd0f7ccd789a73cad25c4f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f6085-102">Routage basé sur l’emplacement pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6085-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6085-103">_**Dernière modification de la rubrique:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="f6085-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="f6085-104">Le routage basé sur l’emplacement permet de limiter le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC en fonction de l’emplacement des parties de l’appel.</span><span class="sxs-lookup"><span data-stu-id="f6085-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="f6085-105">Avec la mise à jour cumulative 2 de Lync Server 2013, les règles de routage basées sur les emplacements peuvent être appliquées à des réunions Lync (par exemple, des conférences) pour empêcher le contournement du numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="f6085-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f6085-106">L’application surveille une conférence active et applique des restrictions de routage basées sur l’emplacement en fonction de l’emplacement des utilisateurs qui participent.</span><span class="sxs-lookup"><span data-stu-id="f6085-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="f6085-107">L’application de conférence de routage basée sur l’emplacement permet en outre d’appliquer des restrictions de routage basées sur les emplacements aux transferts de points de terminaison RTC.</span><span class="sxs-lookup"><span data-stu-id="f6085-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f6085-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f6085-108">In This Section</span></span>

  - [<span data-ttu-id="f6085-109">Vue d’ensemble de l’acheminement en fonction de l’emplacement pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6085-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="f6085-110">Routage par emplacement et transferts d’appels de consultation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6085-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="f6085-111">Configuration requise pour le routage sur site pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6085-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="f6085-112">Configuration du routage géodépendant pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6085-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

