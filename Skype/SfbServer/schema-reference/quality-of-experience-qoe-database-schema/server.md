---
title: Table Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table serveur est une table de prise en charge. Chaque enregistrement représente un serveur.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806132"
---
# <a name="server-table"></a><span data-ttu-id="7ac26-104">Table Server</span><span class="sxs-lookup"><span data-stu-id="7ac26-104">Server table</span></span>
 
<span data-ttu-id="7ac26-105">La table serveur est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7ac26-105">The Server table is a supporting table.</span></span> <span data-ttu-id="7ac26-106">Chaque enregistrement représente un serveur.</span><span class="sxs-lookup"><span data-stu-id="7ac26-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="7ac26-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="7ac26-107">**Column**</span></span>|<span data-ttu-id="7ac26-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="7ac26-108">**Data Type**</span></span>|<span data-ttu-id="7ac26-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="7ac26-109">**Key/Index**</span></span>|<span data-ttu-id="7ac26-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="7ac26-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ac26-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="7ac26-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="7ac26-112">int</span><span class="sxs-lookup"><span data-stu-id="7ac26-112">int</span></span>  <br/> |<span data-ttu-id="7ac26-113">Principal</span><span class="sxs-lookup"><span data-stu-id="7ac26-113">Primary</span></span>  <br/> |<span data-ttu-id="7ac26-114">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="7ac26-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="7ac26-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="7ac26-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="7ac26-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7ac26-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7ac26-117">index</span><span class="sxs-lookup"><span data-stu-id="7ac26-117">index</span></span>  <br/> |<span data-ttu-id="7ac26-118">Chaîne d’adresses MAC.</span><span class="sxs-lookup"><span data-stu-id="7ac26-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="7ac26-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="7ac26-119">**ServerType**</span></span> <br/> |<span data-ttu-id="7ac26-120">int</span><span class="sxs-lookup"><span data-stu-id="7ac26-120">int</span></span>  <br/> |<span data-ttu-id="7ac26-121">Externes</span><span class="sxs-lookup"><span data-stu-id="7ac26-121">Foreign</span></span>  <br/> |<span data-ttu-id="7ac26-122">1 : serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7ac26-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="7ac26-123">2 : service de conférence a/V Server16394 : service32769 Edge A/V : passerelle</span><span class="sxs-lookup"><span data-stu-id="7ac26-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="7ac26-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="7ac26-124">**PoolName**</span></span> <br/> |<span data-ttu-id="7ac26-125">nvarchar</span><span class="sxs-lookup"><span data-stu-id="7ac26-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="7ac26-126">Regroupement auquel appartient le serveur.</span><span class="sxs-lookup"><span data-stu-id="7ac26-126">Pool the server belongs to.</span></span> <span data-ttu-id="7ac26-127">Applicable uniquement au serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="7ac26-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="7ac26-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7ac26-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7ac26-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7ac26-129">datetime</span></span>  <br/> ||<span data-ttu-id="7ac26-130">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="7ac26-130">For internal use only.</span></span>  <br/> |
   

