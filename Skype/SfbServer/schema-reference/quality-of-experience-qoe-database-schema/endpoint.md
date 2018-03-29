---
title: Table Endpoint
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Le tableau du point de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a><span data-ttu-id="ba77e-104">Table Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba77e-104">Endpoint table</span></span>
 
<span data-ttu-id="ba77e-105">Le tableau du point de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé aux sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba77e-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ba77e-106">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ba77e-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="ba77e-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ba77e-107">**Column**</span></span>|<span data-ttu-id="ba77e-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="ba77e-108">**Data Type**</span></span>|<span data-ttu-id="ba77e-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="ba77e-109">**Key/Index**</span></span>|<span data-ttu-id="ba77e-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="ba77e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ba77e-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="ba77e-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="ba77e-112">int</span><span class="sxs-lookup"><span data-stu-id="ba77e-112">int</span></span>  <br/> |<span data-ttu-id="ba77e-113">Principal</span><span class="sxs-lookup"><span data-stu-id="ba77e-113">Primary</span></span>  <br/> |<span data-ttu-id="ba77e-114">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ba77e-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="ba77e-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ba77e-115">**Name**</span></span> <br/> |<span data-ttu-id="ba77e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba77e-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ba77e-117">Unique</span><span class="sxs-lookup"><span data-stu-id="ba77e-117">Unique</span></span>  <br/> |<span data-ttu-id="ba77e-118">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ba77e-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="ba77e-119">**SYSTÈME D’EXPLOITATION**</span><span class="sxs-lookup"><span data-stu-id="ba77e-119">**OS**</span></span> <br/> |<span data-ttu-id="ba77e-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="ba77e-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="ba77e-121">Système d’exploitation (OS) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ba77e-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ba77e-122">**NOMUC**</span><span class="sxs-lookup"><span data-stu-id="ba77e-122">**CPUName**</span></span> <br/> |<span data-ttu-id="ba77e-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="ba77e-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="ba77e-124">Nom du processeur du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ba77e-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ba77e-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="ba77e-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="ba77e-126">smallint</span><span class="sxs-lookup"><span data-stu-id="ba77e-126">smallint</span></span>  <br/> ||<span data-ttu-id="ba77e-127">Nombre de coeurs de processeur du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ba77e-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ba77e-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="ba77e-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="ba77e-129">int</span><span class="sxs-lookup"><span data-stu-id="ba77e-129">int</span></span>  <br/> ||<span data-ttu-id="ba77e-130">Vitesse de processeur du processeur du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ba77e-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ba77e-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="ba77e-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="ba77e-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba77e-132">tinyint</span></span>  <br/> || <span data-ttu-id="ba77e-133">Indicateur binaire qui indique si le système est en cours d’exécution dans un environnement virtualisé :</span><span class="sxs-lookup"><span data-stu-id="ba77e-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="ba77e-134">0 x 0000 - aucun</span><span class="sxs-lookup"><span data-stu-id="ba77e-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="ba77e-135">0 x 0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="ba77e-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="ba77e-136">0 x 0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="ba77e-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="ba77e-137">0 x 0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="ba77e-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="ba77e-138">0 x 0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="ba77e-138">0x0008 - Xen PC</span></span> <br/> |
   

