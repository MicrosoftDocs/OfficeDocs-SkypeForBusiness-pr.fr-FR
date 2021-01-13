---
title: Table Pool
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La table Pool est une table de prise en charge qui contient des informations sur les différents pools frontaux. Chaque enregistrement dans la table représente un pool.
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815814"
---
# <a name="pool-table"></a><span data-ttu-id="fac5c-104">Table Pool</span><span class="sxs-lookup"><span data-stu-id="fac5c-104">Pool table</span></span>
 
<span data-ttu-id="fac5c-p102">La table Pool est une table de prise en charge qui contient des informations sur les différents pools frontaux. Chaque enregistrement dans la table représente un pool.</span><span class="sxs-lookup"><span data-stu-id="fac5c-p102">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="fac5c-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fac5c-107">**Column**</span></span>|<span data-ttu-id="fac5c-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="fac5c-108">**Data Type**</span></span>|<span data-ttu-id="fac5c-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="fac5c-109">**Key/Index**</span></span>|<span data-ttu-id="fac5c-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="fac5c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fac5c-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="fac5c-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="fac5c-112">int</span><span class="sxs-lookup"><span data-stu-id="fac5c-112">int</span></span>  <br/> |<span data-ttu-id="fac5c-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="fac5c-113">Primary</span></span>  <br/> |<span data-ttu-id="fac5c-114">Numéro unique identifiant ce pool.</span><span class="sxs-lookup"><span data-stu-id="fac5c-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="fac5c-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="fac5c-115">**PoolName**</span></span> <br/> |<span data-ttu-id="fac5c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fac5c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fac5c-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="fac5c-117">Unique</span></span>  <br/> |<span data-ttu-id="fac5c-118">Nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="fac5c-118">Pool FQDN.</span></span>  <br/> |
   

