---
title: Table VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un seul appel a deux enregistrements, l’autre pour l’appelant et l’autre pour l’appelé.
ms.openlocfilehash: 58179630534733985e062bbe0fafa1bbfd8499db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906825"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="b7423-104">Table VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="b7423-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="b7423-105">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo.</span><span class="sxs-lookup"><span data-stu-id="b7423-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="b7423-106">En règle générale, un seul appel a deux enregistrements, l’autre pour l’appelant et l’autre pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b7423-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="b7423-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b7423-107">**Column**</span></span>|<span data-ttu-id="b7423-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b7423-108">**Data Type**</span></span>|<span data-ttu-id="b7423-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b7423-109">**Key/Index**</span></span>|<span data-ttu-id="b7423-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b7423-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7423-111">**Paramètre ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="b7423-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="b7423-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b7423-112">datetime</span></span>  <br/> |<span data-ttu-id="b7423-113">Principal</span><span class="sxs-lookup"><span data-stu-id="b7423-113">Primary</span></span>  <br/> |<span data-ttu-id="b7423-114">Référencé depuis la [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="b7423-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b7423-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="b7423-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="b7423-116">int</span><span class="sxs-lookup"><span data-stu-id="b7423-116">int</span></span>  <br/> |<span data-ttu-id="b7423-117">Principal</span><span class="sxs-lookup"><span data-stu-id="b7423-117">Primary</span></span>  <br/> |<span data-ttu-id="b7423-118">Référencé depuis la [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="b7423-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b7423-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="b7423-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="b7423-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7423-120">tinyint</span></span>  <br/> |<span data-ttu-id="b7423-121">Principal</span><span class="sxs-lookup"><span data-stu-id="b7423-121">Primary</span></span>  <br/> |<span data-ttu-id="b7423-122">Référencé depuis la [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="b7423-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b7423-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="b7423-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="b7423-124">bit</span><span class="sxs-lookup"><span data-stu-id="b7423-124">bit</span></span>  <br/> |<span data-ttu-id="b7423-125">Principal</span><span class="sxs-lookup"><span data-stu-id="b7423-125">Primary</span></span>  <br/> |<span data-ttu-id="b7423-126">0 : données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="b7423-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="b7423-127">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="b7423-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="b7423-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="b7423-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="b7423-129">Pourcentage de la session qu'a été déclenché l’événement LowBandwidth pour l’état « Incorrect ».</span><span class="sxs-lookup"><span data-stu-id="b7423-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="b7423-130">La bande passante disponible est insuffisante pour une expérience vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="b7423-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="b7423-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="b7423-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="b7423-132">Pourcentage de session de que l’événement ReceiveSendQuality a été déclenché pour l’état « Incorrect ».</span><span class="sxs-lookup"><span data-stu-id="b7423-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="b7423-133">Qualité du réseau en termes de perte de gigue ou de paquets est lourde et a un impact sur la qualité de l’audio reçu.</span><span class="sxs-lookup"><span data-stu-id="b7423-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

