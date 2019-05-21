---
title: Affichage VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Le mode VoIPDetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295663"
---
# <a name="voipdetails-view"></a><span data-ttu-id="a88d2-104">Affichage VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="a88d2-104">VoIPDetails view</span></span>
 
<span data-ttu-id="a88d2-105">Le mode VoIPDetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="a88d2-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="a88d2-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a88d2-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a88d2-107">Le mode VoIPDetails contient toutes les colonnes de la [vue SessionDetails](sessiondetails-0.md) , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a88d2-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a88d2-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a88d2-108">**Column**</span></span>|<span data-ttu-id="a88d2-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a88d2-109">**Data Type**</span></span>|<span data-ttu-id="a88d2-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a88d2-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a88d2-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="a88d2-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="a88d2-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a88d2-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a88d2-113">URI du téléphone de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a88d2-114">**À la une**</span><span class="sxs-lookup"><span data-stu-id="a88d2-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="a88d2-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a88d2-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a88d2-116">URI de téléphone de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="a88d2-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="a88d2-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="a88d2-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a88d2-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a88d2-119">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a88d2-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="a88d2-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="a88d2-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a88d2-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a88d2-122">Type d’URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="a88d2-123">Pour plus d’informations, voir la [table UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="a88d2-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a88d2-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="a88d2-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="a88d2-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a88d2-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a88d2-126">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a88d2-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="a88d2-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="a88d2-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a88d2-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a88d2-129">URI de téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a88d2-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="a88d2-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="a88d2-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a88d2-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a88d2-132">Serveur de médiation utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a88d2-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="a88d2-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="a88d2-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a88d2-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a88d2-135">Serveur de médiation utilisé par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="a88d2-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="a88d2-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="a88d2-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a88d2-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a88d2-138">Passerelle utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a88d2-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="a88d2-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="a88d2-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a88d2-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a88d2-141">Passerelle utilisée par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="a88d2-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

