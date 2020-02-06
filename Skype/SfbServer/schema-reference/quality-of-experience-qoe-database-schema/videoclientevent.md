---
title: Table VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804992"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="43317-104">Table VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="43317-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="43317-105">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo.</span><span class="sxs-lookup"><span data-stu-id="43317-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="43317-106">En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="43317-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="43317-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="43317-107">**Column**</span></span>|<span data-ttu-id="43317-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="43317-108">**Data Type**</span></span>|<span data-ttu-id="43317-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="43317-109">**Key/Index**</span></span>|<span data-ttu-id="43317-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="43317-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43317-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="43317-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="43317-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="43317-112">datetime</span></span>  <br/> |<span data-ttu-id="43317-113">Principal</span><span class="sxs-lookup"><span data-stu-id="43317-113">Primary</span></span>  <br/> |<span data-ttu-id="43317-114">Fait référence à partir de la [table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="43317-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="43317-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="43317-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="43317-116">int</span><span class="sxs-lookup"><span data-stu-id="43317-116">int</span></span>  <br/> |<span data-ttu-id="43317-117">Principal</span><span class="sxs-lookup"><span data-stu-id="43317-117">Primary</span></span>  <br/> |<span data-ttu-id="43317-118">Fait référence à partir de la [table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="43317-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="43317-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="43317-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="43317-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="43317-120">tinyint</span></span>  <br/> |<span data-ttu-id="43317-121">Principal</span><span class="sxs-lookup"><span data-stu-id="43317-121">Primary</span></span>  <br/> |<span data-ttu-id="43317-122">Fait référence à partir de la [table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="43317-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="43317-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="43317-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="43317-124">bit</span><span class="sxs-lookup"><span data-stu-id="43317-124">bit</span></span>  <br/> |<span data-ttu-id="43317-125">Principal</span><span class="sxs-lookup"><span data-stu-id="43317-125">Primary</span></span>  <br/> |<span data-ttu-id="43317-126">0 : données du destinataire</span><span class="sxs-lookup"><span data-stu-id="43317-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="43317-127">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="43317-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="43317-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="43317-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="43317-129">Pourcentage de session de déclenchement de l’événement LowBandwidth pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="43317-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="43317-130">La bande passante disponible est insuffisante pour obtenir une utilisation vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="43317-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="43317-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="43317-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="43317-132">Pourcentage de session de déclenchement de l’événement ReceiveSendQuality pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="43317-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="43317-133">La qualité du réseau en termes de gigue ou de perte de paquets est sévère et a un impact sur la qualité du son reçu.</span><span class="sxs-lookup"><span data-stu-id="43317-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

