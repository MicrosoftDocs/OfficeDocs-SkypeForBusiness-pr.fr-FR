---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants actifs, par canal et par serveur.
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809744"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="54225-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="54225-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="54225-104">tblComplianceParticipant contient les participants actifs, par canal et par serveur.</span><span class="sxs-lookup"><span data-stu-id="54225-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="54225-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="54225-105">**Columns**</span></span>

|<span data-ttu-id="54225-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="54225-106">**Column**</span></span>|<span data-ttu-id="54225-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="54225-107">**Type**</span></span>|<span data-ttu-id="54225-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="54225-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54225-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="54225-109">channelUri</span></span>  <br/> |<span data-ttu-id="54225-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="54225-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="54225-111">URI (Uniform Resource Identifier) du canal.</span><span class="sxs-lookup"><span data-stu-id="54225-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="54225-112">userId</span><span class="sxs-lookup"><span data-stu-id="54225-112">userId</span></span>  <br/> |<span data-ttu-id="54225-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="54225-113">int, not null</span></span>  <br/> |<span data-ttu-id="54225-114">ID Principal du participant (correspondant à la table tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="54225-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="54225-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="54225-115">joinedAt</span></span>  <br/> |<span data-ttu-id="54225-116">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="54225-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="54225-117">Horodatage de l’événement qui se joint.</span><span class="sxs-lookup"><span data-stu-id="54225-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="54225-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="54225-118">partedAt</span></span>  <br/> |<span data-ttu-id="54225-119">bigint</span><span class="sxs-lookup"><span data-stu-id="54225-119">bigint</span></span>  <br/> |<span data-ttu-id="54225-p101">Null si le participant est encore joint. Horodatage de l’événement qui quitte le canal s’il n’est pas null.</span><span class="sxs-lookup"><span data-stu-id="54225-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="54225-122">Ces entrées finissent par être supprimées lorsque tous les traducteurs traitent l’événement.</span><span class="sxs-lookup"><span data-stu-id="54225-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="54225-123">userUri</span><span class="sxs-lookup"><span data-stu-id="54225-123">userUri</span></span>  <br/> |<span data-ttu-id="54225-124">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="54225-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="54225-125">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="54225-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="54225-126">serverID</span><span class="sxs-lookup"><span data-stu-id="54225-126">serverID</span></span>  <br/> |<span data-ttu-id="54225-127">int</span><span class="sxs-lookup"><span data-stu-id="54225-127">int</span></span>  <br/> |<span data-ttu-id="54225-128">Identité du serveur (comme dans tblServerIdentity.serverID table).</span><span class="sxs-lookup"><span data-stu-id="54225-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="54225-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="54225-129">sessionId</span></span>  <br/> |<span data-ttu-id="54225-130">bigint</span><span class="sxs-lookup"><span data-stu-id="54225-130">bigint</span></span>  <br/> |<span data-ttu-id="54225-p102">Session du serveur. Il s’agit d’un nombre aléatoire généré chaque fois que le service de conversation démarre. Il sert à différencier les sessions dans le but d’identifier les participants orphelins.</span><span class="sxs-lookup"><span data-stu-id="54225-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="54225-134">**Clé**</span><span class="sxs-lookup"><span data-stu-id="54225-134">**Key**</span></span>

|<span data-ttu-id="54225-135">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="54225-135">**Column**</span></span>|<span data-ttu-id="54225-136">**Description**</span><span class="sxs-lookup"><span data-stu-id="54225-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="54225-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="54225-137">Primary key.</span></span>  <br/> |
   

