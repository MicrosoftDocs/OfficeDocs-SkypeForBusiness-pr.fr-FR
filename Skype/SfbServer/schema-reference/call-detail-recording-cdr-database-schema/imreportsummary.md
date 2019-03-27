---
title: Table IMReportSummary dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Le IMReportSummaryTable fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: fd907165f7db131e94d09d2b9a531eeb20812734
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881021"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9b994-104">Table IMReportSummary dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9b994-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9b994-105">Le IMReportSummaryTable fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="9b994-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="9b994-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b994-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9b994-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9b994-107">**Column**</span></span>|<span data-ttu-id="9b994-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="9b994-108">**Data Type**</span></span>|<span data-ttu-id="9b994-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="9b994-109">**Key/Index**</span></span>|<span data-ttu-id="9b994-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="9b994-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9b994-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="9b994-111">**StartTime**</span></span> <br/> |<span data-ttu-id="9b994-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9b994-112">datetime</span></span>  <br/> |<span data-ttu-id="9b994-113">Principal</span><span class="sxs-lookup"><span data-stu-id="9b994-113">Primary</span></span>  <br/> |<span data-ttu-id="9b994-114">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="9b994-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="9b994-115">**Période**</span><span class="sxs-lookup"><span data-stu-id="9b994-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="9b994-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="9b994-116">char(1)</span></span>  <br/> |<span data-ttu-id="9b994-117">Principal</span><span class="sxs-lookup"><span data-stu-id="9b994-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="9b994-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="9b994-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="9b994-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="9b994-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="9b994-120">Principal</span><span class="sxs-lookup"><span data-stu-id="9b994-120">Primary</span></span>  <br/> |<span data-ttu-id="9b994-121">Nom de domaine complet du pool hébergeant la session.</span><span class="sxs-lookup"><span data-stu-id="9b994-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="9b994-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="9b994-122">**AuthType**</span></span> <br/> |<span data-ttu-id="9b994-123">int</span><span class="sxs-lookup"><span data-stu-id="9b994-123">int</span></span>  <br/> |<span data-ttu-id="9b994-124">Principal</span><span class="sxs-lookup"><span data-stu-id="9b994-124">Primary</span></span>  <br/> |<span data-ttu-id="9b994-125">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="9b994-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="9b994-126">Informations de priorité sont stockées dans la [table CallPriorities dans Skype pour Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="9b994-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="9b994-127">**CompteSession**</span><span class="sxs-lookup"><span data-stu-id="9b994-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="9b994-128">bigint</span><span class="sxs-lookup"><span data-stu-id="9b994-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="9b994-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="9b994-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="9b994-130">bigint</span><span class="sxs-lookup"><span data-stu-id="9b994-130">bigint</span></span>  <br/> ||<span data-ttu-id="9b994-131">Nombre total de messages instantanés échangés au cours de la session.</span><span class="sxs-lookup"><span data-stu-id="9b994-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

