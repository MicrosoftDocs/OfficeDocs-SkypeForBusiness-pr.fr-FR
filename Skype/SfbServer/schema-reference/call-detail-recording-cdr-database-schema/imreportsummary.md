---
title: Table IMReportSummary dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Le IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815142"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="269c8-104">Table IMReportSummary dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="269c8-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="269c8-105">Le IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="269c8-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="269c8-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="269c8-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="269c8-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="269c8-107">**Column**</span></span>|<span data-ttu-id="269c8-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="269c8-108">**Data Type**</span></span>|<span data-ttu-id="269c8-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="269c8-109">**Key/Index**</span></span>|<span data-ttu-id="269c8-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="269c8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="269c8-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="269c8-111">**StartTime**</span></span> <br/> |<span data-ttu-id="269c8-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="269c8-112">datetime</span></span>  <br/> |<span data-ttu-id="269c8-113">Principal</span><span class="sxs-lookup"><span data-stu-id="269c8-113">Primary</span></span>  <br/> |<span data-ttu-id="269c8-114">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="269c8-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="269c8-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="269c8-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="269c8-116">Char(1</span><span class="sxs-lookup"><span data-stu-id="269c8-116">char(1)</span></span>  <br/> |<span data-ttu-id="269c8-117">Principal</span><span class="sxs-lookup"><span data-stu-id="269c8-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="269c8-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="269c8-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="269c8-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="269c8-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="269c8-120">Principal</span><span class="sxs-lookup"><span data-stu-id="269c8-120">Primary</span></span>  <br/> |<span data-ttu-id="269c8-121">Nom de domaine complet du pool hébergeant la session.</span><span class="sxs-lookup"><span data-stu-id="269c8-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="269c8-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="269c8-122">**AuthType**</span></span> <br/> |<span data-ttu-id="269c8-123">int</span><span class="sxs-lookup"><span data-stu-id="269c8-123">int</span></span>  <br/> |<span data-ttu-id="269c8-124">Principal</span><span class="sxs-lookup"><span data-stu-id="269c8-124">Primary</span></span>  <br/> |<span data-ttu-id="269c8-125">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="269c8-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="269c8-126">Les informations de priorité sont stockées dans la [table CallPriorities dans Skype entreprise Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="269c8-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="269c8-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="269c8-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="269c8-128">bigint</span><span class="sxs-lookup"><span data-stu-id="269c8-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="269c8-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="269c8-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="269c8-130">bigint</span><span class="sxs-lookup"><span data-stu-id="269c8-130">bigint</span></span>  <br/> ||<span data-ttu-id="269c8-131">Nombre total de messages instantanés échangés lors de la session.</span><span class="sxs-lookup"><span data-stu-id="269c8-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

