---
title: Table TraceRoute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La table TraceRoute contient les informations de routage des appels. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805112"
---
# <a name="traceroute-table"></a><span data-ttu-id="3513d-104">Table TraceRoute</span><span class="sxs-lookup"><span data-stu-id="3513d-104">TraceRoute table</span></span>
 
<span data-ttu-id="3513d-105">La table TraceRoute contient les informations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="3513d-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="3513d-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3513d-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3513d-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3513d-107">**Column**</span></span>|<span data-ttu-id="3513d-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="3513d-108">**Data Type**</span></span>|<span data-ttu-id="3513d-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="3513d-109">**Key/Index**</span></span>|<span data-ttu-id="3513d-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="3513d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3513d-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="3513d-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="3513d-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3513d-112">datetime</span></span>  <br/> |<span data-ttu-id="3513d-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="3513d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3513d-114">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="3513d-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="3513d-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="3513d-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="3513d-116">int</span><span class="sxs-lookup"><span data-stu-id="3513d-116">int</span></span>  <br/> |<span data-ttu-id="3513d-117">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="3513d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3513d-118">Identificateur unique permettant de faire la distinction entre plusieurs appels qui pouvaient avoir commencé à la même date et en même temps.</span><span class="sxs-lookup"><span data-stu-id="3513d-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="3513d-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="3513d-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="3513d-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="3513d-120">tinyint</span></span>  <br/> |<span data-ttu-id="3513d-121">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="3513d-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3513d-122">Représente le type de ligne vidéo utilisée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="3513d-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="3513d-123">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3513d-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="3513d-124">0-audio</span><span class="sxs-lookup"><span data-stu-id="3513d-124">0 - Audio</span></span>  <br/> <span data-ttu-id="3513d-125">1-vidéo</span><span class="sxs-lookup"><span data-stu-id="3513d-125">1 - Video</span></span>  <br/> <span data-ttu-id="3513d-126">2-vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="3513d-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="3513d-127">3-partage de bureau et d’application</span><span class="sxs-lookup"><span data-stu-id="3513d-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="3513d-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="3513d-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="3513d-129">bit</span><span class="sxs-lookup"><span data-stu-id="3513d-129">bit</span></span>  <br/> |<span data-ttu-id="3513d-130">Principal</span><span class="sxs-lookup"><span data-stu-id="3513d-130">Primary</span></span>  <br/> |<span data-ttu-id="3513d-131">Point de terminaison ayant placé l’appel.</span><span class="sxs-lookup"><span data-stu-id="3513d-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="3513d-132">**Relais**</span><span class="sxs-lookup"><span data-stu-id="3513d-132">**Hop**</span></span> <br/> |<span data-ttu-id="3513d-133">int</span><span class="sxs-lookup"><span data-stu-id="3513d-133">int</span></span>  <br/> ||<span data-ttu-id="3513d-134">Tronçon réseau/</span><span class="sxs-lookup"><span data-stu-id="3513d-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="3513d-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="3513d-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="3513d-136">int</span><span class="sxs-lookup"><span data-stu-id="3513d-136">int</span></span>  <br/> |<span data-ttu-id="3513d-137">Externes</span><span class="sxs-lookup"><span data-stu-id="3513d-137">Foreign</span></span>  <br/> |<span data-ttu-id="3513d-138">Identificateur unique de l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="3513d-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="3513d-139">Les informations d’adresse IP sont stockées dans la [table IPAddress](ipaddress.md).</span><span class="sxs-lookup"><span data-stu-id="3513d-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="3513d-140">**TEMPS**</span><span class="sxs-lookup"><span data-stu-id="3513d-140">**RTT**</span></span> <br/> |<span data-ttu-id="3513d-141">int</span><span class="sxs-lookup"><span data-stu-id="3513d-141">int</span></span>  <br/> ||<span data-ttu-id="3513d-142">Durée de l’aller-retour.</span><span class="sxs-lookup"><span data-stu-id="3513d-142">Roundtrip time.</span></span> <span data-ttu-id="3513d-143">Le temps d’aller-retour mesure la durée pendant laquelle un paquet vocal atteint sa destination et renvoie la notification de réception.</span><span class="sxs-lookup"><span data-stu-id="3513d-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

