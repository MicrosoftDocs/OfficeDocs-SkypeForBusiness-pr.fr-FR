---
title: Table SessionCorrelation
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un ID de corrélation qui sert à corréler plusieurs sessions.
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884662"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="02010-104">Table SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="02010-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="02010-105">La table SessionCorrelation est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="02010-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="02010-106">Chaque enregistrement représente un ID de corrélation qui sert à corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="02010-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="02010-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="02010-107">**Column**</span></span>|<span data-ttu-id="02010-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="02010-108">**Data Type**</span></span>|<span data-ttu-id="02010-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="02010-109">**Key/Index**</span></span>|<span data-ttu-id="02010-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="02010-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="02010-111">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="02010-111">**Checksum**</span></span> <br/> |<span data-ttu-id="02010-112">int</span><span class="sxs-lookup"><span data-stu-id="02010-112">int</span></span>  <br/> |||
|<span data-ttu-id="02010-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="02010-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="02010-114">int</span><span class="sxs-lookup"><span data-stu-id="02010-114">int</span></span>  <br/> |<span data-ttu-id="02010-115">Principal</span><span class="sxs-lookup"><span data-stu-id="02010-115">Primary</span></span>  <br/> |<span data-ttu-id="02010-116">Numéro unique identifiant cet A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="02010-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="02010-117">**ID de corrélation**</span><span class="sxs-lookup"><span data-stu-id="02010-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="02010-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="02010-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="02010-119">Unique</span><span class="sxs-lookup"><span data-stu-id="02010-119">Unique</span></span>  <br/> |<span data-ttu-id="02010-120">Sessions qui sont corrélées auront le même ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="02010-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="02010-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="02010-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="02010-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="02010-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="02010-123">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="02010-123">For internal use only.</span></span>  <br/> |
   

