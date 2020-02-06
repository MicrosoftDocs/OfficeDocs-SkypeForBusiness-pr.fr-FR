---
title: Table SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente une corrélation qui est utilisée pour mettre en corrélation plusieurs sessions.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805742"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="35cc1-104">Table SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="35cc1-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="35cc1-105">La table SessionCorrelation est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="35cc1-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="35cc1-106">Chaque enregistrement représente une corrélation qui est utilisée pour mettre en corrélation plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="35cc1-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="35cc1-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="35cc1-107">**Column**</span></span>|<span data-ttu-id="35cc1-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="35cc1-108">**Data Type**</span></span>|<span data-ttu-id="35cc1-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="35cc1-109">**Key/Index**</span></span>|<span data-ttu-id="35cc1-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="35cc1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35cc1-111">**1018**</span><span class="sxs-lookup"><span data-stu-id="35cc1-111">**Checksum**</span></span> <br/> |<span data-ttu-id="35cc1-112">int</span><span class="sxs-lookup"><span data-stu-id="35cc1-112">int</span></span>  <br/> |||
|<span data-ttu-id="35cc1-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="35cc1-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="35cc1-114">int</span><span class="sxs-lookup"><span data-stu-id="35cc1-114">int</span></span>  <br/> |<span data-ttu-id="35cc1-115">Principal</span><span class="sxs-lookup"><span data-stu-id="35cc1-115">Primary</span></span>  <br/> |<span data-ttu-id="35cc1-116">Numéro unique identifiant ce serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="35cc1-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="35cc1-117">**Corrélation**</span><span class="sxs-lookup"><span data-stu-id="35cc1-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="35cc1-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="35cc1-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="35cc1-119">Différent</span><span class="sxs-lookup"><span data-stu-id="35cc1-119">Unique</span></span>  <br/> |<span data-ttu-id="35cc1-120">Les sessions corrélées auront le même ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="35cc1-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="35cc1-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="35cc1-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="35cc1-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="35cc1-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="35cc1-123">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="35cc1-123">For internal use only.</span></span>  <br/> |
   

