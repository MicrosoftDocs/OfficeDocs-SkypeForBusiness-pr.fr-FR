---
title: Table Pool
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La table primaire est une table qui stocke des informations sur les différents pools de Front-End de support. Chaque enregistrement de la table représente un pool.
ms.openlocfilehash: 8ce54d4b0a20fa405f34bb14b3eecb9ad395884e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="pool-table"></a><span data-ttu-id="23284-104">Table Pool</span><span class="sxs-lookup"><span data-stu-id="23284-104">Pool table</span></span>
 
<span data-ttu-id="23284-105">La table primaire est une table qui stocke des informations sur les différents pools de Front-End de support.</span><span class="sxs-lookup"><span data-stu-id="23284-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="23284-106">Chaque enregistrement de la table représente un pool.</span><span class="sxs-lookup"><span data-stu-id="23284-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="23284-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="23284-107">**Column**</span></span>|<span data-ttu-id="23284-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="23284-108">**Data Type**</span></span>|<span data-ttu-id="23284-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="23284-109">**Key/Index**</span></span>|<span data-ttu-id="23284-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="23284-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23284-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="23284-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="23284-112">int</span><span class="sxs-lookup"><span data-stu-id="23284-112">int</span></span>  <br/> |<span data-ttu-id="23284-113">Principal</span><span class="sxs-lookup"><span data-stu-id="23284-113">Primary</span></span>  <br/> |<span data-ttu-id="23284-114">Numéro unique identifiant ce pool.</span><span class="sxs-lookup"><span data-stu-id="23284-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="23284-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="23284-115">**PoolName**</span></span> <br/> |<span data-ttu-id="23284-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="23284-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="23284-117">Unique</span><span class="sxs-lookup"><span data-stu-id="23284-117">Unique</span></span>  <br/> |<span data-ttu-id="23284-118">Nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="23284-118">Pool FQDN.</span></span>  <br/> |
   

