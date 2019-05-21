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
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294551"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="8a880-104">Table VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="8a880-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="8a880-105">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo.</span><span class="sxs-lookup"><span data-stu-id="8a880-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="8a880-106">En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8a880-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="8a880-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8a880-107">**Column**</span></span>|<span data-ttu-id="8a880-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="8a880-108">**Data Type**</span></span>|<span data-ttu-id="8a880-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="8a880-109">**Key/Index**</span></span>|<span data-ttu-id="8a880-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="8a880-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8a880-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="8a880-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="8a880-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8a880-112">datetime</span></span>  <br/> |<span data-ttu-id="8a880-113">Principal</span><span class="sxs-lookup"><span data-stu-id="8a880-113">Primary</span></span>  <br/> |<span data-ttu-id="8a880-114">Fait référence à partir de la [table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="8a880-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="8a880-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="8a880-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="8a880-116">int</span><span class="sxs-lookup"><span data-stu-id="8a880-116">int</span></span>  <br/> |<span data-ttu-id="8a880-117">Principal</span><span class="sxs-lookup"><span data-stu-id="8a880-117">Primary</span></span>  <br/> |<span data-ttu-id="8a880-118">Fait référence à partir de la [table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="8a880-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="8a880-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="8a880-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="8a880-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="8a880-120">tinyint</span></span>  <br/> |<span data-ttu-id="8a880-121">Principal</span><span class="sxs-lookup"><span data-stu-id="8a880-121">Primary</span></span>  <br/> |<span data-ttu-id="8a880-122">Fait référence à partir de la [table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="8a880-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="8a880-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="8a880-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="8a880-124">bit</span><span class="sxs-lookup"><span data-stu-id="8a880-124">bit</span></span>  <br/> |<span data-ttu-id="8a880-125">Principal</span><span class="sxs-lookup"><span data-stu-id="8a880-125">Primary</span></span>  <br/> |<span data-ttu-id="8a880-126">0: données du destinataire</span><span class="sxs-lookup"><span data-stu-id="8a880-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="8a880-127">1: données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="8a880-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="8a880-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="8a880-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="8a880-129">Pourcentage de session de déclenchement de l’événement LowBandwidth pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="8a880-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="8a880-130">La bande passante disponible est insuffisante pour obtenir une utilisation vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="8a880-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="8a880-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="8a880-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="8a880-132">Pourcentage de session de déclenchement de l’événement ReceiveSendQuality pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="8a880-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="8a880-133">La qualité du réseau en termes de gigue ou de perte de paquets est sévère et a un impact sur la qualité du son reçu.</span><span class="sxs-lookup"><span data-stu-id="8a880-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

