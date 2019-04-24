---
title: Vue voipdetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vue voipdetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212704"
---
# <a name="voipdetails-view"></a><span data-ttu-id="c877e-104">Vue voipdetails</span><span class="sxs-lookup"><span data-stu-id="c877e-104">VoIPDetails view</span></span>
 
<span data-ttu-id="c877e-105">La vue voipdetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="c877e-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="c877e-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c877e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c877e-107">La vue voipdetails contient toutes les colonnes dans la [vue SessionDetails](sessiondetails-0.md) en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c877e-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="c877e-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c877e-108">**Column**</span></span>|<span data-ttu-id="c877e-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c877e-109">**Data Type**</span></span>|<span data-ttu-id="c877e-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c877e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c877e-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="c877e-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="c877e-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c877e-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c877e-113">URI du téléphone de l’utilisateur ayant démarré la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c877e-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="c877e-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="c877e-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c877e-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c877e-116">URI du téléphone de l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="c877e-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="c877e-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="c877e-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c877e-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c877e-119">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c877e-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="c877e-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="c877e-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c877e-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c877e-122">Type d’URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="c877e-123">Consultez la [table UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="c877e-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c877e-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="c877e-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="c877e-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c877e-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c877e-126">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c877e-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="c877e-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="c877e-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c877e-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c877e-129">URI du téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c877e-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="c877e-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="c877e-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c877e-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c877e-132">Serveur de médiation utilisé par l’utilisateur ayant démarré la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c877e-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="c877e-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="c877e-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c877e-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c877e-135">Serveur de médiation utilisé par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="c877e-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="c877e-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="c877e-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c877e-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c877e-138">Passerelle utilisée par l’utilisateur ayant démarré la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c877e-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="c877e-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="c877e-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c877e-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c877e-141">Passerelle utilisée par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="c877e-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

