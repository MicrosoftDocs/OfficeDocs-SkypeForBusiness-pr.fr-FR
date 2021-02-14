---
title: Table VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelé.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821394"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="17f50-104">Table VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="17f50-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="17f50-105">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f50-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="17f50-106">En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="17f50-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="17f50-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="17f50-107">**Column**</span></span>|<span data-ttu-id="17f50-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="17f50-108">**Data Type**</span></span>|<span data-ttu-id="17f50-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="17f50-109">**Key/Index**</span></span>|<span data-ttu-id="17f50-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="17f50-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="17f50-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="17f50-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="17f50-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="17f50-112">datetime</span></span>  <br/> |<span data-ttu-id="17f50-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="17f50-113">Primary</span></span>  <br/> |<span data-ttu-id="17f50-114">Référencé à partir de [la table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="17f50-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="17f50-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="17f50-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="17f50-116">int</span><span class="sxs-lookup"><span data-stu-id="17f50-116">int</span></span>  <br/> |<span data-ttu-id="17f50-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="17f50-117">Primary</span></span>  <br/> |<span data-ttu-id="17f50-118">Référencé à partir de [la table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="17f50-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="17f50-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="17f50-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="17f50-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="17f50-120">tinyint</span></span>  <br/> |<span data-ttu-id="17f50-121">Primaire</span><span class="sxs-lookup"><span data-stu-id="17f50-121">Primary</span></span>  <br/> |<span data-ttu-id="17f50-122">Référencé à partir de [la table MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="17f50-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="17f50-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="17f50-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="17f50-124">bit</span><span class="sxs-lookup"><span data-stu-id="17f50-124">bit</span></span>  <br/> |<span data-ttu-id="17f50-125">Primaire</span><span class="sxs-lookup"><span data-stu-id="17f50-125">Primary</span></span>  <br/> |<span data-ttu-id="17f50-126">0 : données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="17f50-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="17f50-127">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="17f50-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="17f50-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="17f50-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="17f50-129">Pourcentage de session où l’événement LowBandwidth a été déclenché pour l’état « Bad ».</span><span class="sxs-lookup"><span data-stu-id="17f50-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="17f50-130">La bande passante disponible est insuffisante pour une expérience vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="17f50-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="17f50-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="17f50-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="17f50-132">Pourcentage de session où l’événement ReceiveSendQuality a été déclenché pour l’état « Bad ».</span><span class="sxs-lookup"><span data-stu-id="17f50-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="17f50-133">La qualité du réseau en termes de gigue ou de perte de paquets est grave et a un impact sur la qualité de l’audio reçu.</span><span class="sxs-lookup"><span data-stu-id="17f50-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

