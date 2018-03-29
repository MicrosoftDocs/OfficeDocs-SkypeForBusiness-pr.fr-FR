---
title: tblComplianceParticipant
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants en cours par canal et par serveur.
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="f25df-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="f25df-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="f25df-104">tblComplianceParticipant contient les participants en cours par canal et par serveur.</span><span class="sxs-lookup"><span data-stu-id="f25df-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="f25df-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="f25df-105">**Columns**</span></span>

|<span data-ttu-id="f25df-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f25df-106">**Column**</span></span>|<span data-ttu-id="f25df-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="f25df-107">**Type**</span></span>|<span data-ttu-id="f25df-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="f25df-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f25df-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="f25df-109">channelUri</span></span>  <br/> |<span data-ttu-id="f25df-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="f25df-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f25df-111">Chaîne identifiant universel (URI).</span><span class="sxs-lookup"><span data-stu-id="f25df-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="f25df-112">ID utilisateur</span><span class="sxs-lookup"><span data-stu-id="f25df-112">userId</span></span>  <br/> |<span data-ttu-id="f25df-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="f25df-113">int, not null</span></span>  <br/> |<span data-ttu-id="f25df-114">ID principal du participant (correspondant à la table de tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="f25df-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="f25df-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="f25df-115">joinedAt</span></span>  <br/> |<span data-ttu-id="f25df-116">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="f25df-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="f25df-117">Horodatage de l’événement joint.</span><span class="sxs-lookup"><span data-stu-id="f25df-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="f25df-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="f25df-118">partedAt</span></span>  <br/> |<span data-ttu-id="f25df-119">bigint</span><span class="sxs-lookup"><span data-stu-id="f25df-119">bigint</span></span>  <br/> |<span data-ttu-id="f25df-120">Valeur null si le participant est rejoint encore.</span><span class="sxs-lookup"><span data-stu-id="f25df-120">Null if participant is still joined.</span></span> <span data-ttu-id="f25df-121">L’horodatage du canal en laissant des événements si elle est non null.</span><span class="sxs-lookup"><span data-stu-id="f25df-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="f25df-122">Ces entrées sont finalement supprimées lorsque tous les traducteurs de traitent l’événement.</span><span class="sxs-lookup"><span data-stu-id="f25df-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="f25df-123">userUri</span><span class="sxs-lookup"><span data-stu-id="f25df-123">userUri</span></span>  <br/> |<span data-ttu-id="f25df-124">nvarchar(255), non null</span><span class="sxs-lookup"><span data-stu-id="f25df-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="f25df-125">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f25df-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="f25df-126">serverID</span><span class="sxs-lookup"><span data-stu-id="f25df-126">serverID</span></span>  <br/> |<span data-ttu-id="f25df-127">int</span><span class="sxs-lookup"><span data-stu-id="f25df-127">int</span></span>  <br/> |<span data-ttu-id="f25df-128">Identité du serveur (comme dans la table de tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="f25df-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="f25df-129">ID de session</span><span class="sxs-lookup"><span data-stu-id="f25df-129">sessionId</span></span>  <br/> |<span data-ttu-id="f25df-130">bigint</span><span class="sxs-lookup"><span data-stu-id="f25df-130">bigint</span></span>  <br/> |<span data-ttu-id="f25df-131">Session du serveur.</span><span class="sxs-lookup"><span data-stu-id="f25df-131">Server session.</span></span> <span data-ttu-id="f25df-132">Il s’agit d’un nombre aléatoire généré à chaque démarrage d’un service de conversation.</span><span class="sxs-lookup"><span data-stu-id="f25df-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="f25df-133">Il est utilisé pour différencier les sessions pour identifier les participants orphelins.</span><span class="sxs-lookup"><span data-stu-id="f25df-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="f25df-134">**Clé**</span><span class="sxs-lookup"><span data-stu-id="f25df-134">**Key**</span></span>

|<span data-ttu-id="f25df-135">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f25df-135">**Column**</span></span>|<span data-ttu-id="f25df-136">**Description**</span><span class="sxs-lookup"><span data-stu-id="f25df-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f25df-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="f25df-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="f25df-138">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f25df-138">Primary key.</span></span>  <br/> |
   

