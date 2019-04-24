---
title: Table Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table des serveurs est une table de prise en charge. Chaque enregistrement représente un seul serveur.
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212108"
---
# <a name="server-table"></a><span data-ttu-id="7f26d-104">Table Server</span><span class="sxs-lookup"><span data-stu-id="7f26d-104">Server table</span></span>
 
<span data-ttu-id="7f26d-105">La table des serveurs est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7f26d-105">The Server table is a supporting table.</span></span> <span data-ttu-id="7f26d-106">Chaque enregistrement représente un seul serveur.</span><span class="sxs-lookup"><span data-stu-id="7f26d-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="7f26d-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="7f26d-107">**Column**</span></span>|<span data-ttu-id="7f26d-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="7f26d-108">**Data Type**</span></span>|<span data-ttu-id="7f26d-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="7f26d-109">**Key/Index**</span></span>|<span data-ttu-id="7f26d-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="7f26d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7f26d-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="7f26d-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="7f26d-112">int</span><span class="sxs-lookup"><span data-stu-id="7f26d-112">int</span></span>  <br/> |<span data-ttu-id="7f26d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="7f26d-113">Primary</span></span>  <br/> |<span data-ttu-id="7f26d-114">Numéro unique identifiant le serveur.</span><span class="sxs-lookup"><span data-stu-id="7f26d-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="7f26d-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="7f26d-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="7f26d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7f26d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7f26d-117">index</span><span class="sxs-lookup"><span data-stu-id="7f26d-117">index</span></span>  <br/> |<span data-ttu-id="7f26d-118">Chaîne d’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="7f26d-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="7f26d-119">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="7f26d-119">**ServerType**</span></span> <br/> |<span data-ttu-id="7f26d-120">int</span><span class="sxs-lookup"><span data-stu-id="7f26d-120">int</span></span>  <br/> |<span data-ttu-id="7f26d-121">Étrangère</span><span class="sxs-lookup"><span data-stu-id="7f26d-121">Foreign</span></span>  <br/> |<span data-ttu-id="7f26d-122">1 : serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7f26d-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="7f26d-123">2 : A / V Conferencing Server16394 : A Edge a / V v32769 : passerelle</span><span class="sxs-lookup"><span data-stu-id="7f26d-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="7f26d-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="7f26d-124">**PoolName**</span></span> <br/> |<span data-ttu-id="7f26d-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="7f26d-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="7f26d-126">Pool que le serveur appartient.</span><span class="sxs-lookup"><span data-stu-id="7f26d-126">Pool the server belongs to.</span></span> <span data-ttu-id="7f26d-127">Applicable uniquement aux A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="7f26d-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="7f26d-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7f26d-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7f26d-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7f26d-129">datetime</span></span>  <br/> ||<span data-ttu-id="7f26d-130">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="7f26d-130">For internal use only.</span></span>  <br/> |
   

