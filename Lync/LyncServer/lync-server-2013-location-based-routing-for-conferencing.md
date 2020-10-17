---
title: 'Lync Server 2013 : routage des Location-Based pour les conférences'
description: 'Lync Server 2013 : Location-Based routage des conférences.'
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
ms.openlocfilehash: 979c835e03bbf87c9a9bf86b030cb9a8f4e138e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554850"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f90ee-103">Routage des Location-Baseds pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f90ee-103">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f90ee-104">_**Dernière modification de la rubrique :** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="f90ee-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="f90ee-105">Location-Based le routage permet de limiter le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC en fonction de l’emplacement des parties dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="f90ee-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="f90ee-106">Avec la mise à jour cumulative 2 de Lync Server 2013, les règles de routage des Location-Based peuvent être appliquées à des réunions Lync (par exemple, des conférences) pour empêcher le contournement des appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="f90ee-106">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f90ee-107">L’application surveille une conférence active et applique des restrictions de routage Location-Based en fonction de l’emplacement des utilisateurs qui y participent.</span><span class="sxs-lookup"><span data-stu-id="f90ee-107">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="f90ee-108">L’application de conférence de routage de Location-Based permet également d’appliquer des restrictions de routage Location-Based aux transferts consultatifs impliquant des points de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="f90ee-108">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f90ee-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f90ee-109">In This Section</span></span>

  - [<span data-ttu-id="f90ee-110">Vue d’ensemble du routage des Location-Based pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f90ee-110">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="f90ee-111">Routage basé sur l’emplacement et transferts d’appels consultatifs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f90ee-111">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="f90ee-112">Configuration requise pour le routage des Location-Based pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f90ee-112">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="f90ee-113">Configuration du routage des Location-Based pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f90ee-113">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

