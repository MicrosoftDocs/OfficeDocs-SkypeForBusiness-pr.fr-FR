---
title: Table IMReportSummary dans Skype Entreprise Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues dans une organisation. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821524"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="607d4-104">Table IMReportSummary dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="607d4-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="607d4-105">IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="607d4-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="607d4-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="607d4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="607d4-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="607d4-107">**Column**</span></span>|<span data-ttu-id="607d4-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="607d4-108">**Data Type**</span></span>|<span data-ttu-id="607d4-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="607d4-109">**Key/Index**</span></span>|<span data-ttu-id="607d4-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="607d4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="607d4-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="607d4-111">**StartTime**</span></span> <br/> |<span data-ttu-id="607d4-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="607d4-112">datetime</span></span>  <br/> |<span data-ttu-id="607d4-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="607d4-113">Primary</span></span>  <br/> |<span data-ttu-id="607d4-114">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="607d4-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="607d4-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="607d4-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="607d4-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="607d4-116">char(1)</span></span>  <br/> |<span data-ttu-id="607d4-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="607d4-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="607d4-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="607d4-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="607d4-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="607d4-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="607d4-120">Primaire</span><span class="sxs-lookup"><span data-stu-id="607d4-120">Primary</span></span>  <br/> |<span data-ttu-id="607d4-121">Nom de domaine complet du pool hébergeant la session.</span><span class="sxs-lookup"><span data-stu-id="607d4-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="607d4-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="607d4-122">**AuthType**</span></span> <br/> |<span data-ttu-id="607d4-123">int</span><span class="sxs-lookup"><span data-stu-id="607d4-123">int</span></span>  <br/> |<span data-ttu-id="607d4-124">Primaire</span><span class="sxs-lookup"><span data-stu-id="607d4-124">Primary</span></span>  <br/> |<span data-ttu-id="607d4-125">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="607d4-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="607d4-126">Les informations de priorité sont stockées dans la [table CallPriorities dans Skype Entreprise Server 2015.](callpriorities.md)</span><span class="sxs-lookup"><span data-stu-id="607d4-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="607d4-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="607d4-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="607d4-128">bigint</span><span class="sxs-lookup"><span data-stu-id="607d4-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="607d4-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="607d4-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="607d4-130">bigint</span><span class="sxs-lookup"><span data-stu-id="607d4-130">bigint</span></span>  <br/> ||<span data-ttu-id="607d4-131">Nombre total de messages instantanés échangés au cours de la session.</span><span class="sxs-lookup"><span data-stu-id="607d4-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

