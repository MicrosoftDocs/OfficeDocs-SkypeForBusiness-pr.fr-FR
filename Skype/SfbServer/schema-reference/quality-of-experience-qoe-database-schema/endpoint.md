---
title: Table Endpoint
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Le tableau du point de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212241"
---
# <a name="endpoint-table"></a><span data-ttu-id="b4503-104">Table Endpoint</span><span class="sxs-lookup"><span data-stu-id="b4503-104">Endpoint table</span></span>
 
<span data-ttu-id="b4503-105">Le tableau du point de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b4503-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="b4503-106">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="b4503-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="b4503-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b4503-107">**Column**</span></span>|<span data-ttu-id="b4503-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b4503-108">**Data Type**</span></span>|<span data-ttu-id="b4503-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b4503-109">**Key/Index**</span></span>|<span data-ttu-id="b4503-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b4503-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4503-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="b4503-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="b4503-112">int</span><span class="sxs-lookup"><span data-stu-id="b4503-112">int</span></span>  <br/> |<span data-ttu-id="b4503-113">Principal</span><span class="sxs-lookup"><span data-stu-id="b4503-113">Primary</span></span>  <br/> |<span data-ttu-id="b4503-114">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="b4503-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="b4503-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b4503-115">**Name**</span></span> <br/> |<span data-ttu-id="b4503-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b4503-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b4503-117">Unique</span><span class="sxs-lookup"><span data-stu-id="b4503-117">Unique</span></span>  <br/> |<span data-ttu-id="b4503-118">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="b4503-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="b4503-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="b4503-119">**OS**</span></span> <br/> |<span data-ttu-id="b4503-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b4503-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="b4503-121">Système d’exploitation (OS) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="b4503-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="b4503-122">**NOMUC**</span><span class="sxs-lookup"><span data-stu-id="b4503-122">**CPUName**</span></span> <br/> |<span data-ttu-id="b4503-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b4503-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="b4503-124">Nom de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="b4503-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="b4503-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="b4503-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="b4503-126">smallint</span><span class="sxs-lookup"><span data-stu-id="b4503-126">smallint</span></span>  <br/> ||<span data-ttu-id="b4503-127">Nombre de cœurs d’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="b4503-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="b4503-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="b4503-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="b4503-129">int</span><span class="sxs-lookup"><span data-stu-id="b4503-129">int</span></span>  <br/> ||<span data-ttu-id="b4503-130">Vitesse du processeur du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="b4503-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="b4503-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="b4503-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="b4503-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="b4503-132">tinyint</span></span>  <br/> || <span data-ttu-id="b4503-133">Indicateur binaire indiquant si le système est exécuté dans un environnement virtualisé :</span><span class="sxs-lookup"><span data-stu-id="b4503-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="b4503-134">0 x 0000 - aucun</span><span class="sxs-lookup"><span data-stu-id="b4503-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="b4503-135">0 x 0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="b4503-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="b4503-136">0 x 0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="b4503-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="b4503-137">0 x 0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="b4503-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="b4503-138">0 x 0008 - PC Xen</span><span class="sxs-lookup"><span data-stu-id="b4503-138">0x0008 - Xen PC</span></span> <br/> |
   

