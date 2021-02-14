---
title: Table Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table Server est une table de prise en charge. Chaque enregistrement représente un serveur.
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802704"
---
# <a name="server-table"></a><span data-ttu-id="b38d8-104">Table Server</span><span class="sxs-lookup"><span data-stu-id="b38d8-104">Server table</span></span>
 
<span data-ttu-id="b38d8-105">La table Server est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="b38d8-105">The Server table is a supporting table.</span></span> <span data-ttu-id="b38d8-106">Chaque enregistrement représente un serveur.</span><span class="sxs-lookup"><span data-stu-id="b38d8-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="b38d8-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b38d8-107">**Column**</span></span>|<span data-ttu-id="b38d8-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b38d8-108">**Data Type**</span></span>|<span data-ttu-id="b38d8-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b38d8-109">**Key/Index**</span></span>|<span data-ttu-id="b38d8-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b38d8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b38d8-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="b38d8-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="b38d8-112">int</span><span class="sxs-lookup"><span data-stu-id="b38d8-112">int</span></span>  <br/> |<span data-ttu-id="b38d8-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="b38d8-113">Primary</span></span>  <br/> |<span data-ttu-id="b38d8-114">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="b38d8-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="b38d8-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="b38d8-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="b38d8-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b38d8-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b38d8-117">Index</span><span class="sxs-lookup"><span data-stu-id="b38d8-117">index</span></span>  <br/> |<span data-ttu-id="b38d8-118">Chaîne d’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="b38d8-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="b38d8-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="b38d8-119">**ServerType**</span></span> <br/> |<span data-ttu-id="b38d8-120">int</span><span class="sxs-lookup"><span data-stu-id="b38d8-120">int</span></span>  <br/> |<span data-ttu-id="b38d8-121">Étranger</span><span class="sxs-lookup"><span data-stu-id="b38d8-121">Foreign</span></span>  <br/> |<span data-ttu-id="b38d8-122">1 : serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="b38d8-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="b38d8-123">2 : Serveur de conférence A/V16394 : service Edge A/V32769 : passerelle</span><span class="sxs-lookup"><span data-stu-id="b38d8-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="b38d8-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="b38d8-124">**PoolName**</span></span> <br/> |<span data-ttu-id="b38d8-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="b38d8-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="b38d8-126">Pool à qui appartient le serveur.</span><span class="sxs-lookup"><span data-stu-id="b38d8-126">Pool the server belongs to.</span></span> <span data-ttu-id="b38d8-127">Applicable uniquement pour le serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="b38d8-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="b38d8-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b38d8-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b38d8-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b38d8-129">datetime</span></span>  <br/> ||<span data-ttu-id="b38d8-130">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="b38d8-130">For internal use only.</span></span>  <br/> |
   

