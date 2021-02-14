---
title: Table SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un CorrelationID qui est utilisé pour corréler plusieurs sessions.
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802654"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="d1cc0-104">Table SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="d1cc0-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="d1cc0-105">La table SessionCorrelation est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d1cc0-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="d1cc0-106">Chaque enregistrement représente un CorrelationID qui est utilisé pour corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="d1cc0-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="d1cc0-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d1cc0-107">**Column**</span></span>|<span data-ttu-id="d1cc0-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d1cc0-108">**Data Type**</span></span>|<span data-ttu-id="d1cc0-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="d1cc0-109">**Key/Index**</span></span>|<span data-ttu-id="d1cc0-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="d1cc0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1cc0-111">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="d1cc0-111">**Checksum**</span></span> <br/> |<span data-ttu-id="d1cc0-112">int</span><span class="sxs-lookup"><span data-stu-id="d1cc0-112">int</span></span>  <br/> |||
|<span data-ttu-id="d1cc0-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="d1cc0-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="d1cc0-114">int</span><span class="sxs-lookup"><span data-stu-id="d1cc0-114">int</span></span>  <br/> |<span data-ttu-id="d1cc0-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="d1cc0-115">Primary</span></span>  <br/> |<span data-ttu-id="d1cc0-116">Numéro unique identifiant ce serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="d1cc0-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="d1cc0-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="d1cc0-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="d1cc0-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1cc0-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d1cc0-119">Uniques</span><span class="sxs-lookup"><span data-stu-id="d1cc0-119">Unique</span></span>  <br/> |<span data-ttu-id="d1cc0-120">Les sessions corrélées auront le même ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="d1cc0-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="d1cc0-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d1cc0-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d1cc0-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d1cc0-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="d1cc0-123">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="d1cc0-123">For internal use only.</span></span>  <br/> |
   

