---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants actifs par canal et par serveur.
ms.openlocfilehash: 6644796d88f303c6614cbd73d98224fe0e41eabb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929937"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="3e237-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="3e237-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="3e237-104">tblComplianceParticipant contient les participants actifs par canal et par serveur.</span><span class="sxs-lookup"><span data-stu-id="3e237-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="3e237-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="3e237-105">**Columns**</span></span>

|<span data-ttu-id="3e237-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3e237-106">**Column**</span></span>|<span data-ttu-id="3e237-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="3e237-107">**Type**</span></span>|<span data-ttu-id="3e237-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="3e237-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3e237-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="3e237-109">channelUri</span></span>  <br/> |<span data-ttu-id="3e237-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="3e237-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3e237-111">Canal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="3e237-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="3e237-112">nom d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="3e237-112">userId</span></span>  <br/> |<span data-ttu-id="3e237-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="3e237-113">int, not null</span></span>  <br/> |<span data-ttu-id="3e237-114">ID principal du participant (correspondant à la table tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="3e237-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="3e237-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="3e237-115">joinedAt</span></span>  <br/> |<span data-ttu-id="3e237-116">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="3e237-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="3e237-117">Horodatage de l’événement qui se joint.</span><span class="sxs-lookup"><span data-stu-id="3e237-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="3e237-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="3e237-118">partedAt</span></span>  <br/> |<span data-ttu-id="3e237-119">bigint</span><span class="sxs-lookup"><span data-stu-id="3e237-119">bigint</span></span>  <br/> |<span data-ttu-id="3e237-120">Null si le participant est toujours lié.</span><span class="sxs-lookup"><span data-stu-id="3e237-120">Null if participant is still joined.</span></span> <span data-ttu-id="3e237-121">La date et l’heure du canal en laissant événement si non null.</span><span class="sxs-lookup"><span data-stu-id="3e237-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="3e237-122">Ces entrées sont finissent par être supprimées lorsque tous les traducteurs traitent l’événement.</span><span class="sxs-lookup"><span data-stu-id="3e237-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="3e237-123">userUri</span><span class="sxs-lookup"><span data-stu-id="3e237-123">userUri</span></span>  <br/> |<span data-ttu-id="3e237-124">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="3e237-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="3e237-125">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e237-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="3e237-126">serverID</span><span class="sxs-lookup"><span data-stu-id="3e237-126">serverID</span></span>  <br/> |<span data-ttu-id="3e237-127">int</span><span class="sxs-lookup"><span data-stu-id="3e237-127">int</span></span>  <br/> |<span data-ttu-id="3e237-128">Identité du serveur (comme dans tblServerIdentity.serverID table).</span><span class="sxs-lookup"><span data-stu-id="3e237-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="3e237-129">ID de session</span><span class="sxs-lookup"><span data-stu-id="3e237-129">sessionId</span></span>  <br/> |<span data-ttu-id="3e237-130">bigint</span><span class="sxs-lookup"><span data-stu-id="3e237-130">bigint</span></span>  <br/> |<span data-ttu-id="3e237-131">Session de serveur.</span><span class="sxs-lookup"><span data-stu-id="3e237-131">Server session.</span></span> <span data-ttu-id="3e237-132">Il s’agit d’un nombre aléatoire généré chaque fois qu’un service de conversation démarre.</span><span class="sxs-lookup"><span data-stu-id="3e237-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="3e237-133">Il est utilisé pour différencier les sessions en vue d’identifier les participants orphelins.</span><span class="sxs-lookup"><span data-stu-id="3e237-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="3e237-134">**Clé**</span><span class="sxs-lookup"><span data-stu-id="3e237-134">**Key**</span></span>

|<span data-ttu-id="3e237-135">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3e237-135">**Column**</span></span>|<span data-ttu-id="3e237-136">**Description**</span><span class="sxs-lookup"><span data-stu-id="3e237-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e237-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="3e237-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="3e237-138">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="3e237-138">Primary key.</span></span>  <br/> |
   

