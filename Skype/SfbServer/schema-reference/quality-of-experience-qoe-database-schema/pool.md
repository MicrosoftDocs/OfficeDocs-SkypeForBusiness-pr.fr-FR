---
title: Table Pool
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Le tableau de réserve est une table de prise en charge qui stocke des informations sur les divers pools de front-end. Chaque enregistrement de la table représente un pool.
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807402"
---
# <a name="pool-table"></a><span data-ttu-id="b6559-104">Table Pool</span><span class="sxs-lookup"><span data-stu-id="b6559-104">Pool table</span></span>
 
<span data-ttu-id="b6559-105">Le tableau de réserve est une table de prise en charge qui stocke des informations sur les divers pools de front-end.</span><span class="sxs-lookup"><span data-stu-id="b6559-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="b6559-106">Chaque enregistrement de la table représente un pool.</span><span class="sxs-lookup"><span data-stu-id="b6559-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="b6559-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b6559-107">**Column**</span></span>|<span data-ttu-id="b6559-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b6559-108">**Data Type**</span></span>|<span data-ttu-id="b6559-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b6559-109">**Key/Index**</span></span>|<span data-ttu-id="b6559-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b6559-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b6559-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="b6559-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="b6559-112">int</span><span class="sxs-lookup"><span data-stu-id="b6559-112">int</span></span>  <br/> |<span data-ttu-id="b6559-113">Principal</span><span class="sxs-lookup"><span data-stu-id="b6559-113">Primary</span></span>  <br/> |<span data-ttu-id="b6559-114">Numéro unique identifiant ce pool.</span><span class="sxs-lookup"><span data-stu-id="b6559-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="b6559-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="b6559-115">**PoolName**</span></span> <br/> |<span data-ttu-id="b6559-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b6559-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b6559-117">Différent</span><span class="sxs-lookup"><span data-stu-id="b6559-117">Unique</span></span>  <br/> |<span data-ttu-id="b6559-118">Nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="b6559-118">Pool FQDN.</span></span>  <br/> |
   

