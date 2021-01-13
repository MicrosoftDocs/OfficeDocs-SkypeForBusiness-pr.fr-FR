---
title: Table ErrorCategory dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Le tableau ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype Entreprise Server 2015. Par défaut, Skype Entreprise Server 2015 utilise les classifications suivantes :'
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813144"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cad8f-104">Table ErrorCategory dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="cad8f-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cad8f-105">Le tableau ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cad8f-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="cad8f-106">Par défaut, Skype Entreprise Server 2015 utilise les classifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="cad8f-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="cad8f-107">0 : réussite</span><span class="sxs-lookup"><span data-stu-id="cad8f-107">0 -- Success</span></span>
    
- <span data-ttu-id="cad8f-108">1 - Échec attendu</span><span class="sxs-lookup"><span data-stu-id="cad8f-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="cad8f-109">2 - Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="cad8f-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="cad8f-110">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cad8f-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cad8f-111">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cad8f-111">**Column**</span></span>|<span data-ttu-id="cad8f-112">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="cad8f-112">**Data Type**</span></span>|<span data-ttu-id="cad8f-113">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="cad8f-113">**Key/Index**</span></span>|<span data-ttu-id="cad8f-114">**Details**</span><span class="sxs-lookup"><span data-stu-id="cad8f-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cad8f-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="cad8f-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="cad8f-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="cad8f-116">tinyint</span></span>  <br/> |<span data-ttu-id="cad8f-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="cad8f-117">Primary</span></span>  <br/> |<span data-ttu-id="cad8f-118">Identificateur unique pour la classification.</span><span class="sxs-lookup"><span data-stu-id="cad8f-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="cad8f-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="cad8f-119">**Name**</span></span> <br/> |<span data-ttu-id="cad8f-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cad8f-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="cad8f-p103">Valeur et nom convivial attribués à la classification. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="cad8f-p103">Value and friendly name assigned to the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="cad8f-123">0 : réussite</span><span class="sxs-lookup"><span data-stu-id="cad8f-123">0 -- Success</span></span> <br/>  <span data-ttu-id="cad8f-124">1 - Échec attendu</span><span class="sxs-lookup"><span data-stu-id="cad8f-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="cad8f-125">2 - Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="cad8f-125">2 - Unexpected failure</span></span> <br/> |
   

