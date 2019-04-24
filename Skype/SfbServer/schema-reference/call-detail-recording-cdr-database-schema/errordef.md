---
title: Table ErrorDef dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur qui peut se produire. Chaque enregistrement est un type d’erreur.
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213108"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="495ab-104">Table ErrorDef dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="495ab-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="495ab-105">La table ErrorDef stocke des informations sur chaque type d’erreur qui peut se produire.</span><span class="sxs-lookup"><span data-stu-id="495ab-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="495ab-106">Chaque enregistrement est un type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="495ab-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="495ab-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="495ab-107">**Column**</span></span>|<span data-ttu-id="495ab-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="495ab-108">**Data Type**</span></span>|<span data-ttu-id="495ab-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="495ab-109">**Key/Index**</span></span>|<span data-ttu-id="495ab-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="495ab-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="495ab-111">**Code d’erreur**</span><span class="sxs-lookup"><span data-stu-id="495ab-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="495ab-112">int</span><span class="sxs-lookup"><span data-stu-id="495ab-112">int</span></span>  <br/> |<span data-ttu-id="495ab-113">Principal</span><span class="sxs-lookup"><span data-stu-id="495ab-113">Primary</span></span>  <br/> |<span data-ttu-id="495ab-114">Numéro unique identifiant ce type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="495ab-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="495ab-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="495ab-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="495ab-116">int</span><span class="sxs-lookup"><span data-stu-id="495ab-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="495ab-117">Code de réponse SIP standard associé à cette erreur.</span><span class="sxs-lookup"><span data-stu-id="495ab-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="495ab-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="495ab-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="495ab-119">int</span><span class="sxs-lookup"><span data-stu-id="495ab-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="495ab-120">ID de Diagnostic de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="495ab-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="495ab-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="495ab-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="495ab-122">Int</span><span class="sxs-lookup"><span data-stu-id="495ab-122">Int</span></span>  <br/> |<span data-ttu-id="495ab-123">Étrangère</span><span class="sxs-lookup"><span data-stu-id="495ab-123">Foreign</span></span>  <br/> |<span data-ttu-id="495ab-124">Type de l’appel.</span><span class="sxs-lookup"><span data-stu-id="495ab-124">Type of the call.</span></span> <span data-ttu-id="495ab-125">Voir la [table CallType dans Skype pour Business Server 2015](calltype.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="495ab-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="495ab-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="495ab-126">**RequestType**</span></span> <br/> |<span data-ttu-id="495ab-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="495ab-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="495ab-128">Type de demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="495ab-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="495ab-129">Ces données peuvent être converties au format texte à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="495ab-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="495ab-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="495ab-130">**ContentType**</span></span> <br/> |<span data-ttu-id="495ab-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="495ab-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="495ab-132">Type de contenu de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="495ab-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="495ab-133">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="495ab-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

