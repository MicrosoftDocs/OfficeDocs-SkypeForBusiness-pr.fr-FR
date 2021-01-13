---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des traducteurs inscrits.
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809854"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="ce8c5-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="ce8c5-103">tblComplianceData</span></span>
 
<span data-ttu-id="ce8c5-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des traducteurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="ce8c5-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="ce8c5-105">**Columns**</span></span>

|<span data-ttu-id="ce8c5-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ce8c5-106">**Column**</span></span>|<span data-ttu-id="ce8c5-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="ce8c5-107">**Type**</span></span>|<span data-ttu-id="ce8c5-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="ce8c5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ce8c5-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="ce8c5-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="ce8c5-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="ce8c5-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="ce8c5-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="ce8c5-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="ce8c5-112">entryDate</span></span>  <br/> |<span data-ttu-id="ce8c5-113">smalldatetime, non null</span><span class="sxs-lookup"><span data-stu-id="ce8c5-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="ce8c5-114">Moment de l’insertion (peut être éloigné dans le futur pour cmplType=9, car l’entrée est juste un espace réservé dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="ce8c5-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="ce8c5-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="ce8c5-115">cmplType</span></span>  <br/> |<span data-ttu-id="ce8c5-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="ce8c5-116">int, not null</span></span>  <br/> | <span data-ttu-id="ce8c5-117">Type d’événement de conformité :</span><span class="sxs-lookup"><span data-stu-id="ce8c5-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="ce8c5-118">1: Conversation</span><span class="sxs-lookup"><span data-stu-id="ce8c5-118">1: Chat</span></span> <br/>  <span data-ttu-id="ce8c5-119">2: Sauvegarde de conversation</span><span class="sxs-lookup"><span data-stu-id="ce8c5-119">2: Backchat</span></span> <br/>  <span data-ttu-id="ce8c5-120">3: Téléchargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="ce8c5-120">3: File download</span></span> <br/>  <span data-ttu-id="ce8c5-121">4: Chargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="ce8c5-121">4: File upload</span></span> <br/>  <span data-ttu-id="ce8c5-122">9: Transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="ce8c5-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="ce8c5-123">10: Suppression de conversation (avec remplacement)</span><span class="sxs-lookup"><span data-stu-id="ce8c5-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="ce8c5-124">11: Purge des conversations</span><span class="sxs-lookup"><span data-stu-id="ce8c5-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="ce8c5-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="ce8c5-125">cmplTime</span></span>  <br/> |<span data-ttu-id="ce8c5-126">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="ce8c5-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="ce8c5-127">Horodatage pour l’événement.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="ce8c5-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="ce8c5-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="ce8c5-129">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="ce8c5-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ce8c5-130">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="ce8c5-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="ce8c5-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="ce8c5-132">bigint</span><span class="sxs-lookup"><span data-stu-id="ce8c5-132">bigint</span></span>  <br/> |<span data-ttu-id="ce8c5-133">ID de conversation (correspondant à la table tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="ce8c5-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="ce8c5-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="ce8c5-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="ce8c5-135">int, non null</span><span class="sxs-lookup"><span data-stu-id="ce8c5-135">int, not null</span></span>  <br/> |<span data-ttu-id="ce8c5-136">ID principal de l’affiche (correspondant à la table tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="ce8c5-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="ce8c5-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="ce8c5-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="ce8c5-138">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="ce8c5-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ce8c5-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="ce8c5-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="ce8c5-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="ce8c5-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ce8c5-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="ce8c5-142">Message (le codage dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="ce8c5-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="ce8c5-143">**Clé**</span><span class="sxs-lookup"><span data-stu-id="ce8c5-143">**Key**</span></span>

|<span data-ttu-id="ce8c5-144">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ce8c5-144">**Column**</span></span>|<span data-ttu-id="ce8c5-145">**Description**</span><span class="sxs-lookup"><span data-stu-id="ce8c5-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce8c5-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="ce8c5-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="ce8c5-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-147">Primary key.</span></span>  <br/> |
   

