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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente une corrélation qui est utilisée pour mettre en corrélation plusieurs sessions.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294655"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="0f64b-104">Table SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="0f64b-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="0f64b-105">La table SessionCorrelation est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0f64b-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="0f64b-106">Chaque enregistrement représente une corrélation qui est utilisée pour mettre en corrélation plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="0f64b-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="0f64b-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0f64b-107">**Column**</span></span>|<span data-ttu-id="0f64b-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0f64b-108">**Data Type**</span></span>|<span data-ttu-id="0f64b-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="0f64b-109">**Key/Index**</span></span>|<span data-ttu-id="0f64b-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0f64b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0f64b-111">**1018**</span><span class="sxs-lookup"><span data-stu-id="0f64b-111">**Checksum**</span></span> <br/> |<span data-ttu-id="0f64b-112">int</span><span class="sxs-lookup"><span data-stu-id="0f64b-112">int</span></span>  <br/> |||
|<span data-ttu-id="0f64b-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="0f64b-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="0f64b-114">int</span><span class="sxs-lookup"><span data-stu-id="0f64b-114">int</span></span>  <br/> |<span data-ttu-id="0f64b-115">Principal</span><span class="sxs-lookup"><span data-stu-id="0f64b-115">Primary</span></span>  <br/> |<span data-ttu-id="0f64b-116">Numéro unique identifiant ce serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="0f64b-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="0f64b-117">**Corrélation**</span><span class="sxs-lookup"><span data-stu-id="0f64b-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="0f64b-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0f64b-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f64b-119">Différent</span><span class="sxs-lookup"><span data-stu-id="0f64b-119">Unique</span></span>  <br/> |<span data-ttu-id="0f64b-120">Les sessions corrélées auront le même ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="0f64b-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="0f64b-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="0f64b-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0f64b-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0f64b-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="0f64b-123">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="0f64b-123">For internal use only.</span></span>  <br/> |
   

