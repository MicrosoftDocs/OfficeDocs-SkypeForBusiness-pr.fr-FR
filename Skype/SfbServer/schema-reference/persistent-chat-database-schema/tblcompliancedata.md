---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traitées par l’adaptateur de la conformité.
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a><span data-ttu-id="46029-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="46029-103">tblComplianceData</span></span>
 
<span data-ttu-id="46029-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traitées par l’adaptateur de la conformité.</span><span class="sxs-lookup"><span data-stu-id="46029-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="46029-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="46029-105">**Columns**</span></span>

|<span data-ttu-id="46029-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="46029-106">**Column**</span></span>|<span data-ttu-id="46029-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="46029-107">**Type**</span></span>|<span data-ttu-id="46029-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="46029-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46029-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="46029-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="46029-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="46029-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="46029-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="46029-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="46029-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="46029-112">entryDate</span></span>  <br/> |<span data-ttu-id="46029-113">smalldatetime, non null</span><span class="sxs-lookup"><span data-stu-id="46029-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="46029-114">Heure de l’insertion (peut être dans le futur pour cmplType = 9, car l’entrée est simplement un espace réservé dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="46029-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="46029-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="46029-115">cmplType</span></span>  <br/> |<span data-ttu-id="46029-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="46029-116">int, not null</span></span>  <br/> | <span data-ttu-id="46029-117">Type d’événement de conformité :</span><span class="sxs-lookup"><span data-stu-id="46029-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="46029-118">1 : chat</span><span class="sxs-lookup"><span data-stu-id="46029-118">1: Chat</span></span> <br/>  <span data-ttu-id="46029-119">2 : backchat</span><span class="sxs-lookup"><span data-stu-id="46029-119">2: Backchat</span></span> <br/>  <span data-ttu-id="46029-120">3 : téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="46029-120">3: File download</span></span> <br/>  <span data-ttu-id="46029-121">4 : téléchargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="46029-121">4: File upload</span></span> <br/>  <span data-ttu-id="46029-122">9 : transfert de fichiers provisoire</span><span class="sxs-lookup"><span data-stu-id="46029-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="46029-123">10 : chat suppression (avec remplacement)</span><span class="sxs-lookup"><span data-stu-id="46029-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="46029-124">11 : purge de conversation</span><span class="sxs-lookup"><span data-stu-id="46029-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="46029-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="46029-125">cmplTime</span></span>  <br/> |<span data-ttu-id="46029-126">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="46029-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="46029-127">Horodatage de l’événement.</span><span class="sxs-lookup"><span data-stu-id="46029-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="46029-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="46029-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="46029-129">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="46029-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="46029-130">Chaîne identifiant universel (URI).</span><span class="sxs-lookup"><span data-stu-id="46029-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="46029-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="46029-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="46029-132">bigint</span><span class="sxs-lookup"><span data-stu-id="46029-132">bigint</span></span>  <br/> |<span data-ttu-id="46029-133">Chat ID (correspondant à la table de tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="46029-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="46029-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="46029-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="46029-135">int, non null</span><span class="sxs-lookup"><span data-stu-id="46029-135">int, not null</span></span>  <br/> |<span data-ttu-id="46029-136">ID d’entité de l’affiche (correspondant à la table de tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="46029-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="46029-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="46029-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="46029-138">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="46029-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="46029-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="46029-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="46029-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="46029-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="46029-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="46029-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="46029-142">Messages (codage dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="46029-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="46029-143">**Clé**</span><span class="sxs-lookup"><span data-stu-id="46029-143">**Key**</span></span>

|<span data-ttu-id="46029-144">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="46029-144">**Column**</span></span>|<span data-ttu-id="46029-145">**Description**</span><span class="sxs-lookup"><span data-stu-id="46029-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46029-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="46029-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="46029-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="46029-147">Primary key.</span></span>  <br/> |
   

