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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213031"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="42e17-104">Table IMReportSummary dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="42e17-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="42e17-105">Le IMReportSummaryTable fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="42e17-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="42e17-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42e17-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="42e17-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="42e17-107">**Column**</span></span>|<span data-ttu-id="42e17-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="42e17-108">**Data Type**</span></span>|<span data-ttu-id="42e17-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="42e17-109">**Key/Index**</span></span>|<span data-ttu-id="42e17-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="42e17-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="42e17-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="42e17-111">**StartTime**</span></span> <br/> |<span data-ttu-id="42e17-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="42e17-112">datetime</span></span>  <br/> |<span data-ttu-id="42e17-113">Principal</span><span class="sxs-lookup"><span data-stu-id="42e17-113">Primary</span></span>  <br/> |<span data-ttu-id="42e17-114">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="42e17-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="42e17-115">**Période**</span><span class="sxs-lookup"><span data-stu-id="42e17-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="42e17-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="42e17-116">char(1)</span></span>  <br/> |<span data-ttu-id="42e17-117">Principal</span><span class="sxs-lookup"><span data-stu-id="42e17-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="42e17-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="42e17-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="42e17-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="42e17-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="42e17-120">Principal</span><span class="sxs-lookup"><span data-stu-id="42e17-120">Primary</span></span>  <br/> |<span data-ttu-id="42e17-121">Nom de domaine complet du pool hébergeant la session.</span><span class="sxs-lookup"><span data-stu-id="42e17-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="42e17-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="42e17-122">**AuthType**</span></span> <br/> |<span data-ttu-id="42e17-123">int</span><span class="sxs-lookup"><span data-stu-id="42e17-123">int</span></span>  <br/> |<span data-ttu-id="42e17-124">Principal</span><span class="sxs-lookup"><span data-stu-id="42e17-124">Primary</span></span>  <br/> |<span data-ttu-id="42e17-125">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="42e17-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="42e17-126">Informations de priorité sont stockées dans la [table CallPriorities dans Skype pour Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="42e17-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="42e17-127">**CompteSession**</span><span class="sxs-lookup"><span data-stu-id="42e17-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="42e17-128">bigint</span><span class="sxs-lookup"><span data-stu-id="42e17-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="42e17-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="42e17-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="42e17-130">bigint</span><span class="sxs-lookup"><span data-stu-id="42e17-130">bigint</span></span>  <br/> ||<span data-ttu-id="42e17-131">Nombre total de messages instantanés échangés au cours de la session.</span><span class="sxs-lookup"><span data-stu-id="42e17-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

