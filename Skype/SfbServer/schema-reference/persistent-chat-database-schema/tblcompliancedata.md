---
title: tblComplianceData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885820"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="a0a31-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="a0a31-103">tblComplianceData</span></span>
 
<span data-ttu-id="a0a31-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.</span><span class="sxs-lookup"><span data-stu-id="a0a31-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="a0a31-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="a0a31-105">**Columns**</span></span>

|<span data-ttu-id="a0a31-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a0a31-106">**Column**</span></span>|<span data-ttu-id="a0a31-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="a0a31-107">**Type**</span></span>|<span data-ttu-id="a0a31-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a0a31-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0a31-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a0a31-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="a0a31-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="a0a31-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="a0a31-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="a0a31-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="a0a31-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="a0a31-112">entryDate</span></span>  <br/> |<span data-ttu-id="a0a31-113">smalldatetime, non null</span><span class="sxs-lookup"><span data-stu-id="a0a31-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="a0a31-114">Heure d’insertion (peut être éloigné dans le futur pour cmplType = 9, car l’entrée est juste un espace réservé dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="a0a31-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="a0a31-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="a0a31-115">cmplType</span></span>  <br/> |<span data-ttu-id="a0a31-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="a0a31-116">int, not null</span></span>  <br/> | <span data-ttu-id="a0a31-117">Type d’événement de conformité :</span><span class="sxs-lookup"><span data-stu-id="a0a31-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="a0a31-118">1 : conversation</span><span class="sxs-lookup"><span data-stu-id="a0a31-118">1: Chat</span></span> <br/>  <span data-ttu-id="a0a31-119">2 : sauvegarde de conversation</span><span class="sxs-lookup"><span data-stu-id="a0a31-119">2: Backchat</span></span> <br/>  <span data-ttu-id="a0a31-120">3 : téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="a0a31-120">3: File download</span></span> <br/>  <span data-ttu-id="a0a31-121">4 : téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="a0a31-121">4: File upload</span></span> <br/>  <span data-ttu-id="a0a31-122">9 : transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="a0a31-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="a0a31-123">10 : suppression (avec remplacement) de conversation</span><span class="sxs-lookup"><span data-stu-id="a0a31-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="a0a31-124">11 : purge des conversations</span><span class="sxs-lookup"><span data-stu-id="a0a31-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="a0a31-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="a0a31-125">cmplTime</span></span>  <br/> |<span data-ttu-id="a0a31-126">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="a0a31-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="a0a31-127">Horodatage de l’événement.</span><span class="sxs-lookup"><span data-stu-id="a0a31-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="a0a31-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="a0a31-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="a0a31-129">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="a0a31-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a0a31-130">Canal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="a0a31-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="a0a31-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="a0a31-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="a0a31-132">bigint</span><span class="sxs-lookup"><span data-stu-id="a0a31-132">bigint</span></span>  <br/> |<span data-ttu-id="a0a31-133">ID de conversation (correspondant à la table tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="a0a31-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="a0a31-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="a0a31-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="a0a31-135">int, non null</span><span class="sxs-lookup"><span data-stu-id="a0a31-135">int, not null</span></span>  <br/> |<span data-ttu-id="a0a31-136">ID principal de l’affiche (correspondant à la table tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="a0a31-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="a0a31-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="a0a31-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="a0a31-138">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="a0a31-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a0a31-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a0a31-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="a0a31-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="a0a31-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="a0a31-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a0a31-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="a0a31-142">Message (codage dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="a0a31-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="a0a31-143">**Clé**</span><span class="sxs-lookup"><span data-stu-id="a0a31-143">**Key**</span></span>

|<span data-ttu-id="a0a31-144">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a0a31-144">**Column**</span></span>|<span data-ttu-id="a0a31-145">**Description**</span><span class="sxs-lookup"><span data-stu-id="a0a31-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a0a31-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a0a31-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="a0a31-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a0a31-147">Primary key.</span></span>  <br/> |
   

