---
title: 'Lync Server 2013 : routage des Location-Based pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03e216e80b50bd7b2d5c0515700c4f1cd7260f22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513801"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="d1169-102">Routage des Location-Baseds pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1169-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1169-103">_**Dernière modification de la rubrique :** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="d1169-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="d1169-104">Location-Based le routage permet de limiter le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC en fonction de l’emplacement des parties dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="d1169-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="d1169-105">Avec la mise à jour cumulative 2 de Lync Server 2013, les règles de routage des Location-Based peuvent être appliquées à des réunions Lync (par exemple, des conférences) pour empêcher le contournement des appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="d1169-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="d1169-106">L’application surveille une conférence active et applique des restrictions de routage Location-Based en fonction de l’emplacement des utilisateurs qui y participent.</span><span class="sxs-lookup"><span data-stu-id="d1169-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="d1169-107">L’application de conférence de routage de Location-Based permet également d’appliquer des restrictions de routage Location-Based aux transferts consultatifs impliquant des points de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="d1169-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d1169-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d1169-108">In This Section</span></span>

  - [<span data-ttu-id="d1169-109">Vue d’ensemble du routage des Location-Based pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1169-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="d1169-110">Routage basé sur l’emplacement et transferts d’appels consultatifs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1169-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="d1169-111">Configuration requise pour le routage des Location-Based pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1169-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="d1169-112">Configuration du routage des Location-Based pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1169-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

