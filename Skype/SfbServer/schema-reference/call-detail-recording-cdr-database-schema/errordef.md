---
title: Table ErrorDef dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur qui peut-être se produire. Chaque fiche correspond à un type d’erreur.
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d3ea9-104">Table ErrorDef dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3ea9-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d3ea9-105">La table ErrorDef stocke des informations sur chaque type d’erreur qui peut-être se produire.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="d3ea9-106">Chaque fiche correspond à un type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="d3ea9-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-107">**Column**</span></span>|<span data-ttu-id="d3ea9-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-108">**Data Type**</span></span>|<span data-ttu-id="d3ea9-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-109">**Key/Index**</span></span>|<span data-ttu-id="d3ea9-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d3ea9-111">**Code d’erreur**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="d3ea9-112">int</span><span class="sxs-lookup"><span data-stu-id="d3ea9-112">int</span></span>  <br/> |<span data-ttu-id="d3ea9-113">Principal</span><span class="sxs-lookup"><span data-stu-id="d3ea9-113">Primary</span></span>  <br/> |<span data-ttu-id="d3ea9-114">Numéro d’identification unique qui identifie ce type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="d3ea9-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="d3ea9-116">int</span><span class="sxs-lookup"><span data-stu-id="d3ea9-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="d3ea9-117">Code de réponse SIP standard associé à cette erreur.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="d3ea9-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="d3ea9-119">int</span><span class="sxs-lookup"><span data-stu-id="d3ea9-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="d3ea9-120">ID de Diagnostic de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="d3ea9-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="d3ea9-122">Int</span><span class="sxs-lookup"><span data-stu-id="d3ea9-122">Int</span></span>  <br/> |<span data-ttu-id="d3ea9-123">Étrangère</span><span class="sxs-lookup"><span data-stu-id="d3ea9-123">Foreign</span></span>  <br/> |<span data-ttu-id="d3ea9-124">Type de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-124">Type of the call.</span></span> <span data-ttu-id="d3ea9-125">Consultez le [tableau CallType dans Skype pour Business Server 2015](calltype.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d3ea9-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-126">**RequestType**</span></span> <br/> |<span data-ttu-id="d3ea9-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="d3ea9-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="d3ea9-128">Type de demande qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="d3ea9-129">Ces données peuvent être converties au format de texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="d3ea9-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="d3ea9-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="d3ea9-130">**ContentType**</span></span> <br/> |<span data-ttu-id="d3ea9-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="d3ea9-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="d3ea9-132">Type de contenu de la demande qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="d3ea9-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="d3ea9-133">Ces données peuvent être converties au format de texte à l’aide de cette syntaxt :</span><span class="sxs-lookup"><span data-stu-id="d3ea9-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

