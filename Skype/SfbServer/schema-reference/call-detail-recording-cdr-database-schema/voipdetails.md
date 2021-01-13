---
title: Affichage VoIPDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813074"
---
# <a name="voipdetails-view"></a><span data-ttu-id="eac70-104">Affichage VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="eac70-104">VoIPDetails view</span></span>
 
<span data-ttu-id="eac70-105">La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="eac70-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="eac70-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eac70-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eac70-107">La vue VoIPDetails contient toutes les colonnes dans la vue [SessionDetails](sessiondetails-0.md) en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="eac70-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="eac70-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="eac70-108">**Column**</span></span>|<span data-ttu-id="eac70-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="eac70-109">**Data Type**</span></span>|<span data-ttu-id="eac70-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="eac70-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eac70-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="eac70-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="eac70-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="eac70-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="eac70-113">URI du téléphone de l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="eac70-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="eac70-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="eac70-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="eac70-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="eac70-116">URI du téléphone de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="eac70-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="eac70-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="eac70-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="eac70-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="eac70-119">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="eac70-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="eac70-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="eac70-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eac70-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eac70-122">Type de URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="eac70-123">Pour plus [d’informations, voir la table UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="eac70-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="eac70-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="eac70-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="eac70-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eac70-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eac70-126">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="eac70-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="eac70-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="eac70-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="eac70-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="eac70-129">URI du téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="eac70-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="eac70-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="eac70-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eac70-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eac70-132">Serveur de médiation utilisé par l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="eac70-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="eac70-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="eac70-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eac70-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eac70-135">Serveur de médiation utilisé par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="eac70-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="eac70-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="eac70-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eac70-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eac70-138">Passerelle utilisée par l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="eac70-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="eac70-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="eac70-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eac70-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eac70-141">Passerelle utilisée par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="eac70-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

