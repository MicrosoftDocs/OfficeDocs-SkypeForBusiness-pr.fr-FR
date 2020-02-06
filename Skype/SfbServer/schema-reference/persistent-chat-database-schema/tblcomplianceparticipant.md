---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants actuels par canal et par serveur.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814642"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="41b1b-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="41b1b-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="41b1b-104">tblComplianceParticipant contient les participants actuels par canal et par serveur.</span><span class="sxs-lookup"><span data-stu-id="41b1b-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="41b1b-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="41b1b-105">**Columns**</span></span>

|<span data-ttu-id="41b1b-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="41b1b-106">**Column**</span></span>|<span data-ttu-id="41b1b-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="41b1b-107">**Type**</span></span>|<span data-ttu-id="41b1b-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="41b1b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41b1b-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="41b1b-109">channelUri</span></span>  <br/> |<span data-ttu-id="41b1b-110">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="41b1b-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="41b1b-111">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="41b1b-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="41b1b-112">userId</span><span class="sxs-lookup"><span data-stu-id="41b1b-112">userId</span></span>  <br/> |<span data-ttu-id="41b1b-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="41b1b-113">int, not null</span></span>  <br/> |<span data-ttu-id="41b1b-114">ID principal du participant (correspondant à la table tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="41b1b-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="41b1b-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="41b1b-115">joinedAt</span></span>  <br/> |<span data-ttu-id="41b1b-116">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="41b1b-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="41b1b-117">Date et heure de l’événement de jointure.</span><span class="sxs-lookup"><span data-stu-id="41b1b-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="41b1b-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="41b1b-118">partedAt</span></span>  <br/> |<span data-ttu-id="41b1b-119">bigint</span><span class="sxs-lookup"><span data-stu-id="41b1b-119">bigint</span></span>  <br/> |<span data-ttu-id="41b1b-120">NULL si le participant reste connecté.</span><span class="sxs-lookup"><span data-stu-id="41b1b-120">Null if participant is still joined.</span></span> <span data-ttu-id="41b1b-121">Horodatage du canal quittant l’événement s’il n’a pas la valeur null.</span><span class="sxs-lookup"><span data-stu-id="41b1b-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="41b1b-122">Ces entrées sont finalement supprimées lorsque tous les traducteurs traitent l’événement.</span><span class="sxs-lookup"><span data-stu-id="41b1b-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="41b1b-123">userUri</span><span class="sxs-lookup"><span data-stu-id="41b1b-123">userUri</span></span>  <br/> |<span data-ttu-id="41b1b-124">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="41b1b-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="41b1b-125">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="41b1b-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="41b1b-126">serverID</span><span class="sxs-lookup"><span data-stu-id="41b1b-126">serverID</span></span>  <br/> |<span data-ttu-id="41b1b-127">int</span><span class="sxs-lookup"><span data-stu-id="41b1b-127">int</span></span>  <br/> |<span data-ttu-id="41b1b-128">Identité du serveur (comme dans la table tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="41b1b-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="41b1b-129">ID</span><span class="sxs-lookup"><span data-stu-id="41b1b-129">sessionId</span></span>  <br/> |<span data-ttu-id="41b1b-130">bigint</span><span class="sxs-lookup"><span data-stu-id="41b1b-130">bigint</span></span>  <br/> |<span data-ttu-id="41b1b-131">Session du serveur.</span><span class="sxs-lookup"><span data-stu-id="41b1b-131">Server session.</span></span> <span data-ttu-id="41b1b-132">Il s’agit d’un nombre aléatoire généré chaque fois qu’un service de conversation démarre.</span><span class="sxs-lookup"><span data-stu-id="41b1b-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="41b1b-133">Il est utilisé pour différencier les sessions à des fins d’identification de participants orphelins.</span><span class="sxs-lookup"><span data-stu-id="41b1b-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="41b1b-134">**Clé**</span><span class="sxs-lookup"><span data-stu-id="41b1b-134">**Key**</span></span>

|<span data-ttu-id="41b1b-135">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="41b1b-135">**Column**</span></span>|<span data-ttu-id="41b1b-136">**Description**</span><span class="sxs-lookup"><span data-stu-id="41b1b-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41b1b-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="41b1b-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="41b1b-138">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="41b1b-138">Primary key.</span></span>  <br/> |
   

