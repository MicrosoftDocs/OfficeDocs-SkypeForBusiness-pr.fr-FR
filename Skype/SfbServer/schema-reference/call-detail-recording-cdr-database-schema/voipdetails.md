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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Le mode VoIPDetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814772"
---
# <a name="voipdetails-view"></a><span data-ttu-id="ea42b-104">Affichage VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="ea42b-104">VoIPDetails view</span></span>
 
<span data-ttu-id="ea42b-105">Le mode VoIPDetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="ea42b-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="ea42b-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea42b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea42b-107">Le mode VoIPDetails contient toutes les colonnes de la [vue SessionDetails](sessiondetails-0.md) , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ea42b-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="ea42b-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ea42b-108">**Column**</span></span>|<span data-ttu-id="ea42b-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="ea42b-109">**Data Type**</span></span>|<span data-ttu-id="ea42b-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="ea42b-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea42b-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="ea42b-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="ea42b-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ea42b-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ea42b-113">URI du téléphone de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ea42b-114">**À la une**</span><span class="sxs-lookup"><span data-stu-id="ea42b-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="ea42b-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ea42b-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ea42b-116">URI de téléphone de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="ea42b-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="ea42b-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="ea42b-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ea42b-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ea42b-119">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ea42b-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="ea42b-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="ea42b-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea42b-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ea42b-122">Type d’URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="ea42b-123">Pour plus d’informations, voir la [table UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="ea42b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ea42b-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="ea42b-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="ea42b-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea42b-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ea42b-126">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ea42b-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="ea42b-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="ea42b-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ea42b-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ea42b-129">URI de téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ea42b-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="ea42b-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="ea42b-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea42b-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ea42b-132">Serveur de médiation utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ea42b-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="ea42b-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="ea42b-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea42b-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ea42b-135">Serveur de médiation utilisé par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="ea42b-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="ea42b-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="ea42b-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea42b-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ea42b-138">Passerelle utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ea42b-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="ea42b-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="ea42b-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea42b-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ea42b-141">Passerelle utilisée par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="ea42b-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

