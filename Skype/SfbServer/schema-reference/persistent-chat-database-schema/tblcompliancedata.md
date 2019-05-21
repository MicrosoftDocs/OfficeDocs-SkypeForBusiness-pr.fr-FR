---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295509"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="ad064-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="ad064-103">tblComplianceData</span></span>
 
<span data-ttu-id="ad064-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.</span><span class="sxs-lookup"><span data-stu-id="ad064-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="ad064-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="ad064-105">**Columns**</span></span>

|<span data-ttu-id="ad064-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ad064-106">**Column**</span></span>|<span data-ttu-id="ad064-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="ad064-107">**Type**</span></span>|<span data-ttu-id="ad064-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="ad064-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ad064-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="ad064-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="ad064-110">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="ad064-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="ad064-111">ID de l’événement.</span><span class="sxs-lookup"><span data-stu-id="ad064-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="ad064-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="ad064-112">entryDate</span></span>  <br/> |<span data-ttu-id="ad064-113">smalldatetime, pas null</span><span class="sxs-lookup"><span data-stu-id="ad064-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="ad064-114">Temps d’insertion (peut-être lointain dans le cas de cmplType = 9, car l’entrée n’est qu’un espace réservé dans le cas présent).</span><span class="sxs-lookup"><span data-stu-id="ad064-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="ad064-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="ad064-115">cmplType</span></span>  <br/> |<span data-ttu-id="ad064-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="ad064-116">int, not null</span></span>  <br/> | <span data-ttu-id="ad064-117">Type d’événement de conformité:</span><span class="sxs-lookup"><span data-stu-id="ad064-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="ad064-118">1: conversation</span><span class="sxs-lookup"><span data-stu-id="ad064-118">1: Chat</span></span> <br/>  <span data-ttu-id="ad064-119">2: discussions</span><span class="sxs-lookup"><span data-stu-id="ad064-119">2: Backchat</span></span> <br/>  <span data-ttu-id="ad064-120">3: Téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="ad064-120">3: File download</span></span> <br/>  <span data-ttu-id="ad064-121">4: Téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="ad064-121">4: File upload</span></span> <br/>  <span data-ttu-id="ad064-122">9: transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="ad064-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="ad064-123">10: suppression d’une discussion (avec remplacer)</span><span class="sxs-lookup"><span data-stu-id="ad064-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="ad064-124">11: suppression de conversation</span><span class="sxs-lookup"><span data-stu-id="ad064-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="ad064-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="ad064-125">cmplTime</span></span>  <br/> |<span data-ttu-id="ad064-126">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="ad064-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="ad064-127">Date et heure de l’événement.</span><span class="sxs-lookup"><span data-stu-id="ad064-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="ad064-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="ad064-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="ad064-129">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="ad064-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ad064-130">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="ad064-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="ad064-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="ad064-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="ad064-132">bigint</span><span class="sxs-lookup"><span data-stu-id="ad064-132">bigint</span></span>  <br/> |<span data-ttu-id="ad064-133">ID de conversation (correspondant à la table tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="ad064-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="ad064-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="ad064-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="ad064-135">ent, non null</span><span class="sxs-lookup"><span data-stu-id="ad064-135">int, not null</span></span>  <br/> |<span data-ttu-id="ad064-136">ID principal de l’affiche (correspondant à la table tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="ad064-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="ad064-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="ad064-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="ad064-138">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="ad064-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ad064-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ad064-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="ad064-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="ad064-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="ad064-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ad064-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="ad064-142">Le message (Encoding dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="ad064-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="ad064-143">**Clé**</span><span class="sxs-lookup"><span data-stu-id="ad064-143">**Key**</span></span>

|<span data-ttu-id="ad064-144">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ad064-144">**Column**</span></span>|<span data-ttu-id="ad064-145">**Description**</span><span class="sxs-lookup"><span data-stu-id="ad064-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad064-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="ad064-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="ad064-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ad064-147">Primary key.</span></span>  <br/> |
   

