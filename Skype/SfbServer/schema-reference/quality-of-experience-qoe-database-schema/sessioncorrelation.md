---
title: Table SessionCorrelation
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est un tableau de prise en charge. Chaque enregistrement représente un ID de corrélation qui est utilisé pour corréler plusieurs sessions.
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="51632-104">Table SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="51632-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="51632-105">La table SessionCorrelation est un tableau de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="51632-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="51632-106">Chaque enregistrement représente un ID de corrélation qui est utilisé pour corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="51632-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="51632-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="51632-107">**Column**</span></span>|<span data-ttu-id="51632-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="51632-108">**Data Type**</span></span>|<span data-ttu-id="51632-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="51632-109">**Key/Index**</span></span>|<span data-ttu-id="51632-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="51632-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="51632-111">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="51632-111">**Checksum**</span></span> <br/> |<span data-ttu-id="51632-112">int</span><span class="sxs-lookup"><span data-stu-id="51632-112">int</span></span>  <br/> |||
|<span data-ttu-id="51632-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="51632-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="51632-114">int</span><span class="sxs-lookup"><span data-stu-id="51632-114">int</span></span>  <br/> |<span data-ttu-id="51632-115">Principal</span><span class="sxs-lookup"><span data-stu-id="51632-115">Primary</span></span>  <br/> |<span data-ttu-id="51632-116">Numéro unique identifiant cet A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="51632-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="51632-117">**ID de corrélation**</span><span class="sxs-lookup"><span data-stu-id="51632-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="51632-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51632-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="51632-119">Unique</span><span class="sxs-lookup"><span data-stu-id="51632-119">Unique</span></span>  <br/> |<span data-ttu-id="51632-120">Les sessions qui sont corrélées ont le même ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="51632-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="51632-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="51632-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="51632-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="51632-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="51632-123">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="51632-123">For internal use only.</span></span>  <br/> |
   

