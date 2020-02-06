---
title: Table Endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809552"
---
# <a name="endpoint-table"></a><span data-ttu-id="e5cee-104">Table Endpoint</span><span class="sxs-lookup"><span data-stu-id="e5cee-104">Endpoint table</span></span>
 
<span data-ttu-id="e5cee-105">La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e5cee-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e5cee-106">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e5cee-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="e5cee-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e5cee-107">**Column**</span></span>|<span data-ttu-id="e5cee-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e5cee-108">**Data Type**</span></span>|<span data-ttu-id="e5cee-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e5cee-109">**Key/Index**</span></span>|<span data-ttu-id="e5cee-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e5cee-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5cee-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="e5cee-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="e5cee-112">int</span><span class="sxs-lookup"><span data-stu-id="e5cee-112">int</span></span>  <br/> |<span data-ttu-id="e5cee-113">Principal</span><span class="sxs-lookup"><span data-stu-id="e5cee-113">Primary</span></span>  <br/> |<span data-ttu-id="e5cee-114">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e5cee-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="e5cee-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="e5cee-115">**Name**</span></span> <br/> |<span data-ttu-id="e5cee-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5cee-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e5cee-117">Différent</span><span class="sxs-lookup"><span data-stu-id="e5cee-117">Unique</span></span>  <br/> |<span data-ttu-id="e5cee-118">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e5cee-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="e5cee-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="e5cee-119">**OS**</span></span> <br/> |<span data-ttu-id="e5cee-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5cee-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="e5cee-121">Système d’exploitation (se) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e5cee-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="e5cee-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="e5cee-122">**CPUName**</span></span> <br/> |<span data-ttu-id="e5cee-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5cee-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="e5cee-124">Nom de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e5cee-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="e5cee-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="e5cee-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="e5cee-126">type</span><span class="sxs-lookup"><span data-stu-id="e5cee-126">smallint</span></span>  <br/> ||<span data-ttu-id="e5cee-127">Nombre de cœurs d’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e5cee-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="e5cee-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="e5cee-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="e5cee-129">int</span><span class="sxs-lookup"><span data-stu-id="e5cee-129">int</span></span>  <br/> ||<span data-ttu-id="e5cee-130">Vitesse de processeur de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e5cee-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="e5cee-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="e5cee-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="e5cee-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5cee-132">tinyint</span></span>  <br/> || <span data-ttu-id="e5cee-133">Indicateur binaire indiquant si le système s’exécute dans un environnement virtualisé :</span><span class="sxs-lookup"><span data-stu-id="e5cee-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="e5cee-134">0x0000-aucun</span><span class="sxs-lookup"><span data-stu-id="e5cee-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="e5cee-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="e5cee-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="e5cee-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="e5cee-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="e5cee-137">0x0004-PC virtuel</span><span class="sxs-lookup"><span data-stu-id="e5cee-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="e5cee-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="e5cee-138">0x0008 - Xen PC</span></span> <br/> |
   

