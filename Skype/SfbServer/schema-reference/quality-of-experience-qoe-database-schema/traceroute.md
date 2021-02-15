---
title: Table TraceRoute
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La table TraceRoute contient les informations de routage émanant des appels. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831319"
---
# <a name="traceroute-table"></a><span data-ttu-id="4ef87-104">Table TraceRoute</span><span class="sxs-lookup"><span data-stu-id="4ef87-104">TraceRoute table</span></span>
 
<span data-ttu-id="4ef87-105">La table TraceRoute contient les informations de routage émanant des appels.</span><span class="sxs-lookup"><span data-stu-id="4ef87-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="4ef87-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4ef87-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4ef87-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4ef87-107">**Column**</span></span>|<span data-ttu-id="4ef87-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="4ef87-108">**Data Type**</span></span>|<span data-ttu-id="4ef87-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="4ef87-109">**Key/Index**</span></span>|<span data-ttu-id="4ef87-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="4ef87-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ef87-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="4ef87-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="4ef87-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="4ef87-112">datetime</span></span>  <br/> |<span data-ttu-id="4ef87-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="4ef87-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4ef87-114">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4ef87-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="4ef87-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="4ef87-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="4ef87-116">int</span><span class="sxs-lookup"><span data-stu-id="4ef87-116">int</span></span>  <br/> |<span data-ttu-id="4ef87-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="4ef87-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4ef87-118">Identificateur unique utilisé pour faire la distinction entre plusieurs appels qui peuvent avoir commencé à la même date et à la même heure.</span><span class="sxs-lookup"><span data-stu-id="4ef87-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="4ef87-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="4ef87-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="4ef87-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ef87-120">tinyint</span></span>  <br/> |<span data-ttu-id="4ef87-121">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="4ef87-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4ef87-p103">Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="4ef87-p103">Represents the type of video line used in the call. Allowed values are:</span></span>  <br/> <span data-ttu-id="4ef87-124">0 - Audio</span><span class="sxs-lookup"><span data-stu-id="4ef87-124">0 - Audio</span></span>  <br/> <span data-ttu-id="4ef87-125">1 - Vidéo</span><span class="sxs-lookup"><span data-stu-id="4ef87-125">1 - Video</span></span>  <br/> <span data-ttu-id="4ef87-126">2 - Vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="4ef87-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="4ef87-127">3 - Partage d’application/bureau</span><span class="sxs-lookup"><span data-stu-id="4ef87-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="4ef87-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="4ef87-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="4ef87-129">bit</span><span class="sxs-lookup"><span data-stu-id="4ef87-129">bit</span></span>  <br/> |<span data-ttu-id="4ef87-130">Primaire</span><span class="sxs-lookup"><span data-stu-id="4ef87-130">Primary</span></span>  <br/> |<span data-ttu-id="4ef87-131">Système d’extrémité qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="4ef87-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="4ef87-132">**Saut**</span><span class="sxs-lookup"><span data-stu-id="4ef87-132">**Hop**</span></span> <br/> |<span data-ttu-id="4ef87-133">int</span><span class="sxs-lookup"><span data-stu-id="4ef87-133">int</span></span>  <br/> ||<span data-ttu-id="4ef87-134">Tronçon de réseau.</span><span class="sxs-lookup"><span data-stu-id="4ef87-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="4ef87-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="4ef87-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="4ef87-136">int</span><span class="sxs-lookup"><span data-stu-id="4ef87-136">int</span></span>  <br/> |<span data-ttu-id="4ef87-137">Étranger</span><span class="sxs-lookup"><span data-stu-id="4ef87-137">Foreign</span></span>  <br/> |<span data-ttu-id="4ef87-138">Identificateur unique de l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="4ef87-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="4ef87-139">Les informations d’adresse IP sont stockées dans la [table IPAddress.](ipaddress.md)</span><span class="sxs-lookup"><span data-stu-id="4ef87-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="4ef87-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="4ef87-140">**RTT**</span></span> <br/> |<span data-ttu-id="4ef87-141">int</span><span class="sxs-lookup"><span data-stu-id="4ef87-141">int</span></span>  <br/> ||<span data-ttu-id="4ef87-p105">Durée de boucle. La durée de boucle mesure le temps nécessaire pour qu’un paquet vocal atteigne sa destination, puis renvoie une notification indiquant qu’il a été reçu.</span><span class="sxs-lookup"><span data-stu-id="4ef87-p105">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

