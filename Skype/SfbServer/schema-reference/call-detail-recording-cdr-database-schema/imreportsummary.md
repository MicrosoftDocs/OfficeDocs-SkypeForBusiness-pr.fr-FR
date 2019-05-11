---
title: Table IMReportSummary dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Le IMReportSummaryTable fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901044"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="64611-104">Table IMReportSummary dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="64611-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="64611-105">Le IMReportSummaryTable fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="64611-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="64611-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64611-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="64611-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="64611-107">**Column**</span></span>|<span data-ttu-id="64611-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="64611-108">**Data Type**</span></span>|<span data-ttu-id="64611-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="64611-109">**Key/Index**</span></span>|<span data-ttu-id="64611-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="64611-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="64611-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="64611-111">**StartTime**</span></span> <br/> |<span data-ttu-id="64611-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="64611-112">datetime</span></span>  <br/> |<span data-ttu-id="64611-113">Principal</span><span class="sxs-lookup"><span data-stu-id="64611-113">Primary</span></span>  <br/> |<span data-ttu-id="64611-114">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="64611-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="64611-115">**Période**</span><span class="sxs-lookup"><span data-stu-id="64611-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="64611-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="64611-116">char(1)</span></span>  <br/> |<span data-ttu-id="64611-117">Principal</span><span class="sxs-lookup"><span data-stu-id="64611-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="64611-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="64611-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="64611-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="64611-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="64611-120">Principal</span><span class="sxs-lookup"><span data-stu-id="64611-120">Primary</span></span>  <br/> |<span data-ttu-id="64611-121">Nom de domaine complet du pool hébergeant la session.</span><span class="sxs-lookup"><span data-stu-id="64611-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="64611-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="64611-122">**AuthType**</span></span> <br/> |<span data-ttu-id="64611-123">int</span><span class="sxs-lookup"><span data-stu-id="64611-123">int</span></span>  <br/> |<span data-ttu-id="64611-124">Principal</span><span class="sxs-lookup"><span data-stu-id="64611-124">Primary</span></span>  <br/> |<span data-ttu-id="64611-125">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="64611-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="64611-126">Informations de priorité sont stockées dans la [table CallPriorities dans Skype pour Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="64611-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="64611-127">**CompteSession**</span><span class="sxs-lookup"><span data-stu-id="64611-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="64611-128">bigint</span><span class="sxs-lookup"><span data-stu-id="64611-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="64611-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="64611-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="64611-130">bigint</span><span class="sxs-lookup"><span data-stu-id="64611-130">bigint</span></span>  <br/> ||<span data-ttu-id="64611-131">Nombre total de messages instantanés échangés au cours de la session.</span><span class="sxs-lookup"><span data-stu-id="64611-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

