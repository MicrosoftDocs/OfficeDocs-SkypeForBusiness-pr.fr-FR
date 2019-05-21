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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table serveur est une table de prise en charge. Chaque enregistrement représente un serveur.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294711"
---
# <a name="server-table"></a><span data-ttu-id="72b6a-104">Table Server</span><span class="sxs-lookup"><span data-stu-id="72b6a-104">Server table</span></span>
 
<span data-ttu-id="72b6a-105">La table serveur est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="72b6a-105">The Server table is a supporting table.</span></span> <span data-ttu-id="72b6a-106">Chaque enregistrement représente un serveur.</span><span class="sxs-lookup"><span data-stu-id="72b6a-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="72b6a-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="72b6a-107">**Column**</span></span>|<span data-ttu-id="72b6a-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="72b6a-108">**Data Type**</span></span>|<span data-ttu-id="72b6a-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="72b6a-109">**Key/Index**</span></span>|<span data-ttu-id="72b6a-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="72b6a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="72b6a-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="72b6a-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="72b6a-112">int</span><span class="sxs-lookup"><span data-stu-id="72b6a-112">int</span></span>  <br/> |<span data-ttu-id="72b6a-113">Principal</span><span class="sxs-lookup"><span data-stu-id="72b6a-113">Primary</span></span>  <br/> |<span data-ttu-id="72b6a-114">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="72b6a-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="72b6a-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="72b6a-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="72b6a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="72b6a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="72b6a-117">index</span><span class="sxs-lookup"><span data-stu-id="72b6a-117">index</span></span>  <br/> |<span data-ttu-id="72b6a-118">Chaîne d’adresses MAC.</span><span class="sxs-lookup"><span data-stu-id="72b6a-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="72b6a-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="72b6a-119">**ServerType**</span></span> <br/> |<span data-ttu-id="72b6a-120">int</span><span class="sxs-lookup"><span data-stu-id="72b6a-120">int</span></span>  <br/> |<span data-ttu-id="72b6a-121">Externes</span><span class="sxs-lookup"><span data-stu-id="72b6a-121">Foreign</span></span>  <br/> |<span data-ttu-id="72b6a-122">1: serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="72b6a-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="72b6a-123">2: service de conférence a/V Server16394: service32769 Edge A/V: passerelle</span><span class="sxs-lookup"><span data-stu-id="72b6a-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="72b6a-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="72b6a-124">**PoolName**</span></span> <br/> |<span data-ttu-id="72b6a-125">nvarchar</span><span class="sxs-lookup"><span data-stu-id="72b6a-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="72b6a-126">Regroupement auquel appartient le serveur.</span><span class="sxs-lookup"><span data-stu-id="72b6a-126">Pool the server belongs to.</span></span> <span data-ttu-id="72b6a-127">Applicable uniquement au serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="72b6a-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="72b6a-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="72b6a-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="72b6a-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="72b6a-129">datetime</span></span>  <br/> ||<span data-ttu-id="72b6a-130">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="72b6a-130">For internal use only.</span></span>  <br/> |
   

