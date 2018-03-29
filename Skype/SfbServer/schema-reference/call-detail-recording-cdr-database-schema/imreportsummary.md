---
title: Table IMReportSummary dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Le IMReportSummaryTable fournit un rapport global sur les sessions dans une organisation de messagerie instantanée. Cette table a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: f716a7406f4cf3562e2fa9244e8a766ef8537f53
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8d043-104">Table IMReportSummary dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d043-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d043-105">Le IMReportSummaryTable fournit un rapport global sur les sessions dans une organisation de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="8d043-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="8d043-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d043-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8d043-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8d043-107">**Column**</span></span>|<span data-ttu-id="8d043-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="8d043-108">**Data Type**</span></span>|<span data-ttu-id="8d043-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="8d043-109">**Key/Index**</span></span>|<span data-ttu-id="8d043-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="8d043-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d043-111">**Heure de début**</span><span class="sxs-lookup"><span data-stu-id="8d043-111">**StartTime**</span></span> <br/> |<span data-ttu-id="8d043-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8d043-112">datetime</span></span>  <br/> |<span data-ttu-id="8d043-113">Principal</span><span class="sxs-lookup"><span data-stu-id="8d043-113">Primary</span></span>  <br/> |<span data-ttu-id="8d043-114">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="8d043-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="8d043-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="8d043-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="8d043-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="8d043-116">char(1)</span></span>  <br/> |<span data-ttu-id="8d043-117">Principal</span><span class="sxs-lookup"><span data-stu-id="8d043-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="8d043-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="8d043-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="8d043-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="8d043-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="8d043-120">Principal</span><span class="sxs-lookup"><span data-stu-id="8d043-120">Primary</span></span>  <br/> |<span data-ttu-id="8d043-121">Nom de domaine complet du pool qui héberge la session.</span><span class="sxs-lookup"><span data-stu-id="8d043-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="8d043-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="8d043-122">**AuthType**</span></span> <br/> |<span data-ttu-id="8d043-123">int</span><span class="sxs-lookup"><span data-stu-id="8d043-123">int</span></span>  <br/> |<span data-ttu-id="8d043-124">Principal</span><span class="sxs-lookup"><span data-stu-id="8d043-124">Primary</span></span>  <br/> |<span data-ttu-id="8d043-125">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="8d043-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="8d043-126">Les informations de priorité sont stockées dans la [table CallPriorities dans Skype pour Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="8d043-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="8d043-127">**CompteSession**</span><span class="sxs-lookup"><span data-stu-id="8d043-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="8d043-128">bigint</span><span class="sxs-lookup"><span data-stu-id="8d043-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="8d043-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="8d043-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="8d043-130">bigint</span><span class="sxs-lookup"><span data-stu-id="8d043-130">bigint</span></span>  <br/> ||<span data-ttu-id="8d043-131">Nombre total de messages instantanés échangés au cours de la session.</span><span class="sxs-lookup"><span data-stu-id="8d043-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

