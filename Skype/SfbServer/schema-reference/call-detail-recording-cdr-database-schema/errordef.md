---
title: Table ErrorDef dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur qui peut se produire. Chaque enregistrement est un type d’erreur.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821724"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="71415-104">Table ErrorDef dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="71415-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="71415-105">La table ErrorDef stocke des informations sur chaque type d’erreur qui peut se produire.</span><span class="sxs-lookup"><span data-stu-id="71415-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="71415-106">Chaque enregistrement est un type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="71415-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="71415-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="71415-107">**Column**</span></span>|<span data-ttu-id="71415-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="71415-108">**Data Type**</span></span>|<span data-ttu-id="71415-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="71415-109">**Key/Index**</span></span>|<span data-ttu-id="71415-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="71415-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71415-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="71415-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="71415-112">int</span><span class="sxs-lookup"><span data-stu-id="71415-112">int</span></span>  <br/> |<span data-ttu-id="71415-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="71415-113">Primary</span></span>  <br/> |<span data-ttu-id="71415-114">Numéro d’identification unique identifiant ce type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="71415-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="71415-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="71415-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="71415-116">int</span><span class="sxs-lookup"><span data-stu-id="71415-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="71415-117">Code de réponse SIP standard associé à cette erreur.</span><span class="sxs-lookup"><span data-stu-id="71415-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="71415-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="71415-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="71415-119">int</span><span class="sxs-lookup"><span data-stu-id="71415-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="71415-120">ID de diagnostic Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71415-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="71415-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="71415-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="71415-122">Int</span><span class="sxs-lookup"><span data-stu-id="71415-122">Int</span></span>  <br/> |<span data-ttu-id="71415-123">Étranger</span><span class="sxs-lookup"><span data-stu-id="71415-123">Foreign</span></span>  <br/> |<span data-ttu-id="71415-124">Type de l’appel.</span><span class="sxs-lookup"><span data-stu-id="71415-124">Type of the call.</span></span> <span data-ttu-id="71415-125">Pour plus d’informations, voir la table CallType dans Skype Entreprise [Server 2015.](calltype.md)</span><span class="sxs-lookup"><span data-stu-id="71415-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="71415-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="71415-126">**RequestType**</span></span> <br/> |<span data-ttu-id="71415-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="71415-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="71415-128">Type de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="71415-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="71415-129">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="71415-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="71415-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="71415-130">**ContentType**</span></span> <br/> |<span data-ttu-id="71415-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="71415-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="71415-132">Type de contenu de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="71415-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="71415-133">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="71415-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

