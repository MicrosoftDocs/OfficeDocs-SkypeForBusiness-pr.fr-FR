---
title: Table Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table du serveur est une table de prise en charge. Chaque enregistrement représente un serveur.
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a><span data-ttu-id="45072-104">Table Server</span><span class="sxs-lookup"><span data-stu-id="45072-104">Server table</span></span>
 
<span data-ttu-id="45072-105">La table du serveur est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="45072-105">The Server table is a supporting table.</span></span> <span data-ttu-id="45072-106">Chaque enregistrement représente un serveur.</span><span class="sxs-lookup"><span data-stu-id="45072-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="45072-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="45072-107">**Column**</span></span>|<span data-ttu-id="45072-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="45072-108">**Data Type**</span></span>|<span data-ttu-id="45072-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="45072-109">**Key/Index**</span></span>|<span data-ttu-id="45072-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="45072-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45072-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="45072-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="45072-112">int</span><span class="sxs-lookup"><span data-stu-id="45072-112">int</span></span>  <br/> |<span data-ttu-id="45072-113">Principal</span><span class="sxs-lookup"><span data-stu-id="45072-113">Primary</span></span>  <br/> |<span data-ttu-id="45072-114">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="45072-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="45072-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="45072-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="45072-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="45072-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="45072-117">index</span><span class="sxs-lookup"><span data-stu-id="45072-117">index</span></span>  <br/> |<span data-ttu-id="45072-118">Chaîne de l’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="45072-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="45072-119">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="45072-119">**ServerType**</span></span> <br/> |<span data-ttu-id="45072-120">int</span><span class="sxs-lookup"><span data-stu-id="45072-120">int</span></span>  <br/> |<span data-ttu-id="45072-121">Étrangère</span><span class="sxs-lookup"><span data-stu-id="45072-121">Foreign</span></span>  <br/> |<span data-ttu-id="45072-122">1 : serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="45072-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="45072-123">2 : A / V Conferencing Server16394 : A / V Edge service32769 : passerelle</span><span class="sxs-lookup"><span data-stu-id="45072-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="45072-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="45072-124">**PoolName**</span></span> <br/> |<span data-ttu-id="45072-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="45072-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="45072-126">Pool qu'auquel appartient le serveur.</span><span class="sxs-lookup"><span data-stu-id="45072-126">Pool the server belongs to.</span></span> <span data-ttu-id="45072-127">Uniquement applicable pour les A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="45072-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="45072-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="45072-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="45072-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="45072-129">datetime</span></span>  <br/> ||<span data-ttu-id="45072-130">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="45072-130">For internal use only.</span></span>  <br/> |
   

