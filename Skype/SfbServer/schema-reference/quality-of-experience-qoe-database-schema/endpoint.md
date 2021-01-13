---
title: Table Endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La table Endpoint est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823064"
---
# <a name="endpoint-table"></a><span data-ttu-id="342d5-104">Table Endpoint</span><span class="sxs-lookup"><span data-stu-id="342d5-104">Endpoint table</span></span>
 
<span data-ttu-id="342d5-105">La table Endpoint est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="342d5-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="342d5-106">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="342d5-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="342d5-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="342d5-107">**Column**</span></span>|<span data-ttu-id="342d5-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="342d5-108">**Data Type**</span></span>|<span data-ttu-id="342d5-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="342d5-109">**Key/Index**</span></span>|<span data-ttu-id="342d5-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="342d5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="342d5-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="342d5-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="342d5-112">int</span><span class="sxs-lookup"><span data-stu-id="342d5-112">int</span></span>  <br/> |<span data-ttu-id="342d5-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="342d5-113">Primary</span></span>  <br/> |<span data-ttu-id="342d5-114">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="342d5-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="342d5-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="342d5-115">**Name**</span></span> <br/> |<span data-ttu-id="342d5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="342d5-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="342d5-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="342d5-117">Unique</span></span>  <br/> |<span data-ttu-id="342d5-118">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="342d5-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="342d5-119">**SYSTÈME D’EXPLOITATION**</span><span class="sxs-lookup"><span data-stu-id="342d5-119">**OS**</span></span> <br/> |<span data-ttu-id="342d5-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="342d5-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="342d5-121">Système d’exploitation du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="342d5-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="342d5-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="342d5-122">**CPUName**</span></span> <br/> |<span data-ttu-id="342d5-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="342d5-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="342d5-124">Nom du processeur du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="342d5-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="342d5-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="342d5-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="342d5-126">smallint</span><span class="sxs-lookup"><span data-stu-id="342d5-126">smallint</span></span>  <br/> ||<span data-ttu-id="342d5-127">Nombre de cœurs d’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="342d5-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="342d5-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="342d5-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="342d5-129">int</span><span class="sxs-lookup"><span data-stu-id="342d5-129">int</span></span>  <br/> ||<span data-ttu-id="342d5-130">Vitesse du processeur processeur du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="342d5-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="342d5-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="342d5-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="342d5-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="342d5-132">tinyint</span></span>  <br/> || <span data-ttu-id="342d5-133">Indicateur de bits qui indique si le système s’exécute dans un environnement virtualisé :</span><span class="sxs-lookup"><span data-stu-id="342d5-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="342d5-134">0x0000 - Aucun</span><span class="sxs-lookup"><span data-stu-id="342d5-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="342d5-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="342d5-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="342d5-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="342d5-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="342d5-137">0x0004 - Virtual PC</span><span class="sxs-lookup"><span data-stu-id="342d5-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="342d5-138">0x0008 - PC Xen</span><span class="sxs-lookup"><span data-stu-id="342d5-138">0x0008 - Xen PC</span></span> <br/> |
   

