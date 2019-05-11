---
title: Vue voipdetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vue voipdetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 6fb1dede975e59c0ae56fe9872472310c914f685
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930028"
---
# <a name="voipdetails-view"></a><span data-ttu-id="e679f-104">Vue voipdetails</span><span class="sxs-lookup"><span data-stu-id="e679f-104">VoIPDetails view</span></span>
 
<span data-ttu-id="e679f-105">La vue voipdetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="e679f-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="e679f-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e679f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e679f-107">La vue voipdetails contient toutes les colonnes dans la [vue SessionDetails](sessiondetails-0.md) en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e679f-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="e679f-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e679f-108">**Column**</span></span>|<span data-ttu-id="e679f-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e679f-109">**Data Type**</span></span>|<span data-ttu-id="e679f-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e679f-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e679f-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="e679f-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="e679f-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e679f-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e679f-113">URI du téléphone de l’utilisateur ayant démarré la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="e679f-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="e679f-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="e679f-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e679f-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e679f-116">URI du téléphone de l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="e679f-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="e679f-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="e679f-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e679f-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e679f-119">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="e679f-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="e679f-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="e679f-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e679f-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e679f-122">Type d’URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="e679f-123">Consultez la [table UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="e679f-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e679f-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="e679f-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="e679f-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e679f-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e679f-126">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="e679f-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="e679f-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="e679f-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e679f-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e679f-129">URI du téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="e679f-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="e679f-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="e679f-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e679f-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e679f-132">Serveur de médiation utilisé par l’utilisateur ayant démarré la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="e679f-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="e679f-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="e679f-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e679f-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e679f-135">Serveur de médiation utilisé par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="e679f-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="e679f-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="e679f-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e679f-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e679f-138">Passerelle utilisée par l’utilisateur ayant démarré la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="e679f-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="e679f-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="e679f-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e679f-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e679f-141">Passerelle utilisée par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="e679f-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

