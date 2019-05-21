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
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294991"
---
# <a name="endpoint-table"></a><span data-ttu-id="2717a-104">Table Endpoint</span><span class="sxs-lookup"><span data-stu-id="2717a-104">Endpoint table</span></span>
 
<span data-ttu-id="2717a-105">La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2717a-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2717a-106">Chaque enregistrement de la table représente un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2717a-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="2717a-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2717a-107">**Column**</span></span>|<span data-ttu-id="2717a-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2717a-108">**Data Type**</span></span>|<span data-ttu-id="2717a-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="2717a-109">**Key/Index**</span></span>|<span data-ttu-id="2717a-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="2717a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2717a-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="2717a-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="2717a-112">int</span><span class="sxs-lookup"><span data-stu-id="2717a-112">int</span></span>  <br/> |<span data-ttu-id="2717a-113">Principal</span><span class="sxs-lookup"><span data-stu-id="2717a-113">Primary</span></span>  <br/> |<span data-ttu-id="2717a-114">Numéro unique identifiant ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2717a-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="2717a-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="2717a-115">**Name**</span></span> <br/> |<span data-ttu-id="2717a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2717a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2717a-117">Différent</span><span class="sxs-lookup"><span data-stu-id="2717a-117">Unique</span></span>  <br/> |<span data-ttu-id="2717a-118">Nom du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2717a-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="2717a-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="2717a-119">**OS**</span></span> <br/> |<span data-ttu-id="2717a-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="2717a-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="2717a-121">Système d’exploitation (se) du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2717a-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2717a-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="2717a-122">**CPUName**</span></span> <br/> |<span data-ttu-id="2717a-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="2717a-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="2717a-124">Nom de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2717a-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2717a-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="2717a-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="2717a-126">type</span><span class="sxs-lookup"><span data-stu-id="2717a-126">smallint</span></span>  <br/> ||<span data-ttu-id="2717a-127">Nombre de cœurs d’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2717a-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2717a-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="2717a-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="2717a-129">int</span><span class="sxs-lookup"><span data-stu-id="2717a-129">int</span></span>  <br/> ||<span data-ttu-id="2717a-130">Vitesse de processeur de l’UC du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2717a-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2717a-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="2717a-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="2717a-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="2717a-132">tinyint</span></span>  <br/> || <span data-ttu-id="2717a-133">Indicateur binaire indiquant si le système s’exécute dans un environnement virtualisé:</span><span class="sxs-lookup"><span data-stu-id="2717a-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="2717a-134">0x0000-aucun</span><span class="sxs-lookup"><span data-stu-id="2717a-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="2717a-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="2717a-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="2717a-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="2717a-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="2717a-137">0x0004-PC virtuel</span><span class="sxs-lookup"><span data-stu-id="2717a-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="2717a-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="2717a-138">0x0008 - Xen PC</span></span> <br/> |
   

