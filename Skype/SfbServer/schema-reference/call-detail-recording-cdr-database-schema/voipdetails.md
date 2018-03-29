---
title: Vue de VoIPDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vue VoIPDetails stocke des informations sur les sessions d’homologue à homologue, où au moins un utilisateur est un utilisateur de VoIP. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a><span data-ttu-id="e6155-104">Vue de VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="e6155-104">VoIPDetails view</span></span>
 
<span data-ttu-id="e6155-105">La vue VoIPDetails stocke des informations sur les sessions d’homologue à homologue, où au moins un utilisateur est un utilisateur de VoIP.</span><span class="sxs-lookup"><span data-stu-id="e6155-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="e6155-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6155-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6155-107">La vue VoIPDetails contient toutes les colonnes dans la [vue de le SessionDetails](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e6155-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="e6155-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e6155-108">**Column**</span></span>|<span data-ttu-id="e6155-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e6155-109">**Data Type**</span></span>|<span data-ttu-id="e6155-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e6155-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6155-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="e6155-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="e6155-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e6155-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e6155-113">URI de l’utilisateur qui a démarré la session du téléphone.</span><span class="sxs-lookup"><span data-stu-id="e6155-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="e6155-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="e6155-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="e6155-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e6155-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e6155-116">URI de l’utilisateur qui a rejoint la session du téléphone.</span><span class="sxs-lookup"><span data-stu-id="e6155-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="e6155-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="e6155-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="e6155-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e6155-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e6155-119">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="e6155-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="e6155-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="e6155-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="e6155-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6155-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6155-122">Type d’URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="e6155-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="e6155-123">Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="e6155-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e6155-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="e6155-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="e6155-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6155-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6155-126">Clients de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="e6155-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="e6155-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="e6155-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="e6155-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e6155-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e6155-129">URI de l’utilisateur qui a déconnecté la session du téléphone.</span><span class="sxs-lookup"><span data-stu-id="e6155-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="e6155-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="e6155-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="e6155-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6155-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6155-132">Serveur de médiation utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="e6155-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="e6155-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="e6155-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="e6155-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6155-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6155-135">Serveur de médiation utilisé par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="e6155-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="e6155-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="e6155-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="e6155-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6155-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6155-138">Passerelle utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="e6155-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="e6155-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="e6155-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="e6155-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6155-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6155-141">Passerelle utilisée par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="e6155-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

