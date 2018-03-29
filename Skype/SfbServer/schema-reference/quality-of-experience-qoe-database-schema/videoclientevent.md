---
title: Table VideoClientEvent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Chaque enregistrement contient un événement client pour un point de terminaison dans une conversation vidéo. En règle générale, un seul appel a deux enregistrements, celui de l’appelant et celui de l’appelant.
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a><span data-ttu-id="050de-104">Table VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="050de-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="050de-105">Chaque enregistrement contient un événement client pour un point de terminaison dans une conversation vidéo.</span><span class="sxs-lookup"><span data-stu-id="050de-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="050de-106">En règle générale, un seul appel a deux enregistrements, celui de l’appelant et celui de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="050de-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="050de-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="050de-107">**Column**</span></span>|<span data-ttu-id="050de-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="050de-108">**Data Type**</span></span>|<span data-ttu-id="050de-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="050de-109">**Key/Index**</span></span>|<span data-ttu-id="050de-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="050de-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="050de-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="050de-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="050de-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="050de-112">datetime</span></span>  <br/> |<span data-ttu-id="050de-113">Principal</span><span class="sxs-lookup"><span data-stu-id="050de-113">Primary</span></span>  <br/> |<span data-ttu-id="050de-114">Référencé à partir de la [table de MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="050de-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="050de-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="050de-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="050de-116">int</span><span class="sxs-lookup"><span data-stu-id="050de-116">int</span></span>  <br/> |<span data-ttu-id="050de-117">Principal</span><span class="sxs-lookup"><span data-stu-id="050de-117">Primary</span></span>  <br/> |<span data-ttu-id="050de-118">Référencé à partir de la [table de MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="050de-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="050de-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="050de-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="050de-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="050de-120">tinyint</span></span>  <br/> |<span data-ttu-id="050de-121">Principal</span><span class="sxs-lookup"><span data-stu-id="050de-121">Primary</span></span>  <br/> |<span data-ttu-id="050de-122">Référencé à partir de la [table de MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="050de-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="050de-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="050de-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="050de-124">bit</span><span class="sxs-lookup"><span data-stu-id="050de-124">bit</span></span>  <br/> |<span data-ttu-id="050de-125">Principal</span><span class="sxs-lookup"><span data-stu-id="050de-125">Primary</span></span>  <br/> |<span data-ttu-id="050de-126">0 : les données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="050de-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="050de-127">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="050de-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="050de-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="050de-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="050de-129">Pourcentage de la session de que déclenchement de l’événement LowBandwidth pour l’état 'Bad'.</span><span class="sxs-lookup"><span data-stu-id="050de-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="050de-130">La bande passante disponible est insuffisante pour une expérience vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="050de-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="050de-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="050de-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="050de-132">Pourcentage de la session de que déclenchement de l’événement ReceiveSendQuality pour l’état 'Bad'.</span><span class="sxs-lookup"><span data-stu-id="050de-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="050de-133">Réseau de qualité en termes de perte de paquet ou instabilité est grave et a une incidence sur la qualité audio en cours de réception.</span><span class="sxs-lookup"><span data-stu-id="050de-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

