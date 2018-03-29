---
title: Table Conference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La table est une table de prise en charge. Chaque enregistrement représente une conférence ou une session de peer-to-peer.
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a><span data-ttu-id="0b2ab-104">Table Conference</span><span class="sxs-lookup"><span data-stu-id="0b2ab-104">Conference table</span></span>
 
<span data-ttu-id="0b2ab-105">La table est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0b2ab-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="0b2ab-106">Chaque enregistrement représente une conférence ou une session de peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0b2ab-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="0b2ab-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0b2ab-107">**Column**</span></span>|<span data-ttu-id="0b2ab-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0b2ab-108">**Data Type**</span></span>|<span data-ttu-id="0b2ab-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="0b2ab-109">**Key/Index**</span></span>|<span data-ttu-id="0b2ab-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0b2ab-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0b2ab-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="0b2ab-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="0b2ab-112">int</span><span class="sxs-lookup"><span data-stu-id="0b2ab-112">int</span></span>  <br/> |<span data-ttu-id="0b2ab-113">Principal</span><span class="sxs-lookup"><span data-stu-id="0b2ab-113">Primary</span></span>  <br/> |<span data-ttu-id="0b2ab-114">Numéro unique identifiant cet enregistrement de la conférence.</span><span class="sxs-lookup"><span data-stu-id="0b2ab-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="0b2ab-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="0b2ab-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="0b2ab-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0b2ab-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0b2ab-117">unique</span><span class="sxs-lookup"><span data-stu-id="0b2ab-117">unique</span></span>  <br/> |<span data-ttu-id="0b2ab-118">Conférence URI si il s’agit d’une conférence, ou DialogID si ce est une session peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0b2ab-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="0b2ab-119">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="0b2ab-119">**Checksum**</span></span> <br/> |<span data-ttu-id="0b2ab-120">int</span><span class="sxs-lookup"><span data-stu-id="0b2ab-120">int</span></span>  <br/> |<span data-ttu-id="0b2ab-121">index</span><span class="sxs-lookup"><span data-stu-id="0b2ab-121">index</span></span>  <br/> |<span data-ttu-id="0b2ab-122">Total de contrôle de la conférence URI.</span><span class="sxs-lookup"><span data-stu-id="0b2ab-122">Checksum of the conference URI.</span></span> <span data-ttu-id="0b2ab-123">Il est utilisé en interne.</span><span class="sxs-lookup"><span data-stu-id="0b2ab-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="0b2ab-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="0b2ab-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0b2ab-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0b2ab-125">datetime</span></span>  <br/> ||<span data-ttu-id="0b2ab-126">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="0b2ab-126">For internal use only.</span></span>  <br/> |
   

