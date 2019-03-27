---
title: Table Conference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La table de conférence est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874038"
---
# <a name="conference-table"></a><span data-ttu-id="4b3ad-104">Table Conference</span><span class="sxs-lookup"><span data-stu-id="4b3ad-104">Conference table</span></span>
 
<span data-ttu-id="4b3ad-105">La table de conférence est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4b3ad-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="4b3ad-106">Chaque enregistrement représente une conférence ou une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4b3ad-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="4b3ad-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4b3ad-107">**Column**</span></span>|<span data-ttu-id="4b3ad-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="4b3ad-108">**Data Type**</span></span>|<span data-ttu-id="4b3ad-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="4b3ad-109">**Key/Index**</span></span>|<span data-ttu-id="4b3ad-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="4b3ad-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b3ad-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="4b3ad-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="4b3ad-112">int</span><span class="sxs-lookup"><span data-stu-id="4b3ad-112">int</span></span>  <br/> |<span data-ttu-id="4b3ad-113">Principal</span><span class="sxs-lookup"><span data-stu-id="4b3ad-113">Primary</span></span>  <br/> |<span data-ttu-id="4b3ad-114">Numéro unique identifiant cet enregistrement de conférence.</span><span class="sxs-lookup"><span data-stu-id="4b3ad-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="4b3ad-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="4b3ad-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="4b3ad-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4b3ad-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4b3ad-117">unique</span><span class="sxs-lookup"><span data-stu-id="4b3ad-117">unique</span></span>  <br/> |<span data-ttu-id="4b3ad-118">Conférence URI s’il s’agit une conférence, ou DialogID s’il est une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4b3ad-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="4b3ad-119">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="4b3ad-119">**Checksum**</span></span> <br/> |<span data-ttu-id="4b3ad-120">int</span><span class="sxs-lookup"><span data-stu-id="4b3ad-120">int</span></span>  <br/> |<span data-ttu-id="4b3ad-121">index</span><span class="sxs-lookup"><span data-stu-id="4b3ad-121">index</span></span>  <br/> |<span data-ttu-id="4b3ad-122">Somme de contrôle de l’URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="4b3ad-122">Checksum of the conference URI.</span></span> <span data-ttu-id="4b3ad-123">Il est utilisé en interne.</span><span class="sxs-lookup"><span data-stu-id="4b3ad-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="4b3ad-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4b3ad-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4b3ad-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="4b3ad-125">datetime</span></span>  <br/> ||<span data-ttu-id="4b3ad-126">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="4b3ad-126">For internal use only.</span></span>  <br/> |
   

