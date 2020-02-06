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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814662"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="bebf1-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="bebf1-103">tblComplianceData</span></span>
 
<span data-ttu-id="bebf1-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.</span><span class="sxs-lookup"><span data-stu-id="bebf1-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="bebf1-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="bebf1-105">**Columns**</span></span>

|<span data-ttu-id="bebf1-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="bebf1-106">**Column**</span></span>|<span data-ttu-id="bebf1-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="bebf1-107">**Type**</span></span>|<span data-ttu-id="bebf1-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="bebf1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bebf1-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="bebf1-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="bebf1-110">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="bebf1-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="bebf1-111">ID de l’événement.</span><span class="sxs-lookup"><span data-stu-id="bebf1-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="bebf1-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="bebf1-112">entryDate</span></span>  <br/> |<span data-ttu-id="bebf1-113">smalldatetime, pas null</span><span class="sxs-lookup"><span data-stu-id="bebf1-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="bebf1-114">Temps d’insertion (peut-être lointain dans le cas de cmplType = 9, car l’entrée n’est qu’un espace réservé dans le cas présent).</span><span class="sxs-lookup"><span data-stu-id="bebf1-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="bebf1-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="bebf1-115">cmplType</span></span>  <br/> |<span data-ttu-id="bebf1-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="bebf1-116">int, not null</span></span>  <br/> | <span data-ttu-id="bebf1-117">Type d’événement de conformité :</span><span class="sxs-lookup"><span data-stu-id="bebf1-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="bebf1-118">1 : conversation</span><span class="sxs-lookup"><span data-stu-id="bebf1-118">1: Chat</span></span> <br/>  <span data-ttu-id="bebf1-119">2 : discussions</span><span class="sxs-lookup"><span data-stu-id="bebf1-119">2: Backchat</span></span> <br/>  <span data-ttu-id="bebf1-120">3 : Téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="bebf1-120">3: File download</span></span> <br/>  <span data-ttu-id="bebf1-121">4 : Téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="bebf1-121">4: File upload</span></span> <br/>  <span data-ttu-id="bebf1-122">9 : transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="bebf1-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="bebf1-123">10 : suppression d’une discussion (avec remplacer)</span><span class="sxs-lookup"><span data-stu-id="bebf1-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="bebf1-124">11 : suppression de conversation</span><span class="sxs-lookup"><span data-stu-id="bebf1-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="bebf1-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="bebf1-125">cmplTime</span></span>  <br/> |<span data-ttu-id="bebf1-126">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="bebf1-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="bebf1-127">Date et heure de l’événement.</span><span class="sxs-lookup"><span data-stu-id="bebf1-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="bebf1-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="bebf1-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="bebf1-129">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="bebf1-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="bebf1-130">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="bebf1-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="bebf1-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="bebf1-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="bebf1-132">bigint</span><span class="sxs-lookup"><span data-stu-id="bebf1-132">bigint</span></span>  <br/> |<span data-ttu-id="bebf1-133">ID de conversation (correspondant à la table tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="bebf1-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="bebf1-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="bebf1-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="bebf1-135">ent, non null</span><span class="sxs-lookup"><span data-stu-id="bebf1-135">int, not null</span></span>  <br/> |<span data-ttu-id="bebf1-136">ID principal de l’affiche (correspondant à la table tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="bebf1-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="bebf1-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="bebf1-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="bebf1-138">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="bebf1-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="bebf1-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bebf1-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="bebf1-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="bebf1-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="bebf1-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="bebf1-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="bebf1-142">Le message (Encoding dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="bebf1-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="bebf1-143">**Clé**</span><span class="sxs-lookup"><span data-stu-id="bebf1-143">**Key**</span></span>

|<span data-ttu-id="bebf1-144">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="bebf1-144">**Column**</span></span>|<span data-ttu-id="bebf1-145">**Description**</span><span class="sxs-lookup"><span data-stu-id="bebf1-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bebf1-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="bebf1-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="bebf1-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="bebf1-147">Primary key.</span></span>  <br/> |
   

