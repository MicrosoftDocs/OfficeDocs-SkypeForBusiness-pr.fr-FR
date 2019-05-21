---
title: Table ErrorDef dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur pouvant se produire. Chaque enregistrement correspond à un type d’erreur.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296279"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="01e4d-104">Table ErrorDef dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="01e4d-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="01e4d-105">La table ErrorDef stocke des informations sur chaque type d’erreur pouvant se produire.</span><span class="sxs-lookup"><span data-stu-id="01e4d-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="01e4d-106">Chaque enregistrement correspond à un type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="01e4d-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="01e4d-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="01e4d-107">**Column**</span></span>|<span data-ttu-id="01e4d-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="01e4d-108">**Data Type**</span></span>|<span data-ttu-id="01e4d-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="01e4d-109">**Key/Index**</span></span>|<span data-ttu-id="01e4d-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="01e4d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="01e4d-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="01e4d-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="01e4d-112">int</span><span class="sxs-lookup"><span data-stu-id="01e4d-112">int</span></span>  <br/> |<span data-ttu-id="01e4d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="01e4d-113">Primary</span></span>  <br/> |<span data-ttu-id="01e4d-114">Numéro d’identification unique identifiant ce type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="01e4d-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="01e4d-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="01e4d-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="01e4d-116">int</span><span class="sxs-lookup"><span data-stu-id="01e4d-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="01e4d-117">Code de réponse SIP standard associé à cette erreur.</span><span class="sxs-lookup"><span data-stu-id="01e4d-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="01e4d-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="01e4d-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="01e4d-119">int</span><span class="sxs-lookup"><span data-stu-id="01e4d-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="01e4d-120">ID de diagnostic Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01e4d-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="01e4d-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="01e4d-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="01e4d-122">Ent</span><span class="sxs-lookup"><span data-stu-id="01e4d-122">Int</span></span>  <br/> |<span data-ttu-id="01e4d-123">Externes</span><span class="sxs-lookup"><span data-stu-id="01e4d-123">Foreign</span></span>  <br/> |<span data-ttu-id="01e4d-124">Type de l’appel.</span><span class="sxs-lookup"><span data-stu-id="01e4d-124">Type of the call.</span></span> <span data-ttu-id="01e4d-125">Pour plus d’informations, reportez-vous [à la table CallType dans Skype entreprise Server 2015](calltype.md) .</span><span class="sxs-lookup"><span data-stu-id="01e4d-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="01e4d-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="01e4d-126">**RequestType**</span></span> <br/> |<span data-ttu-id="01e4d-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="01e4d-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="01e4d-128">Type de requête ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="01e4d-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="01e4d-129">Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:</span><span class="sxs-lookup"><span data-stu-id="01e4d-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="01e4d-130">**Indiquez**</span><span class="sxs-lookup"><span data-stu-id="01e4d-130">**ContentType**</span></span> <br/> |<span data-ttu-id="01e4d-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="01e4d-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="01e4d-132">Type de contenu de la requête qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="01e4d-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="01e4d-133">Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:</span><span class="sxs-lookup"><span data-stu-id="01e4d-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

