---
title: Table Pool
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Le tableau de Pool est une table de prise en charge qui stocke des informations sur les différents pools frontaux. Chaque enregistrement de la table représente un pool.
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212171"
---
# <a name="pool-table"></a><span data-ttu-id="37352-104">Table Pool</span><span class="sxs-lookup"><span data-stu-id="37352-104">Pool table</span></span>
 
<span data-ttu-id="37352-105">Le tableau de Pool est une table de prise en charge qui stocke des informations sur les différents pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="37352-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="37352-106">Chaque enregistrement de la table représente un pool.</span><span class="sxs-lookup"><span data-stu-id="37352-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="37352-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="37352-107">**Column**</span></span>|<span data-ttu-id="37352-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="37352-108">**Data Type**</span></span>|<span data-ttu-id="37352-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="37352-109">**Key/Index**</span></span>|<span data-ttu-id="37352-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="37352-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="37352-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="37352-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="37352-112">int</span><span class="sxs-lookup"><span data-stu-id="37352-112">int</span></span>  <br/> |<span data-ttu-id="37352-113">Principal</span><span class="sxs-lookup"><span data-stu-id="37352-113">Primary</span></span>  <br/> |<span data-ttu-id="37352-114">Numéro unique identifiant ce pool.</span><span class="sxs-lookup"><span data-stu-id="37352-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="37352-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="37352-115">**PoolName**</span></span> <br/> |<span data-ttu-id="37352-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="37352-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="37352-117">Unique</span><span class="sxs-lookup"><span data-stu-id="37352-117">Unique</span></span>  <br/> |<span data-ttu-id="37352-118">Nom de domaine complet de pool.</span><span class="sxs-lookup"><span data-stu-id="37352-118">Pool FQDN.</span></span>  <br/> |
   

