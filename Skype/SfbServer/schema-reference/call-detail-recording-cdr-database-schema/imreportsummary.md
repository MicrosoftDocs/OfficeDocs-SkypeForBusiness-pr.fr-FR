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
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Le IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296125"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cfb91-104">Table IMReportSummary dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="cfb91-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cfb91-105">Le IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="cfb91-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="cfb91-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfb91-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cfb91-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cfb91-107">**Column**</span></span>|<span data-ttu-id="cfb91-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="cfb91-108">**Data Type**</span></span>|<span data-ttu-id="cfb91-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="cfb91-109">**Key/Index**</span></span>|<span data-ttu-id="cfb91-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="cfb91-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfb91-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="cfb91-111">**StartTime**</span></span> <br/> |<span data-ttu-id="cfb91-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="cfb91-112">datetime</span></span>  <br/> |<span data-ttu-id="cfb91-113">Principal</span><span class="sxs-lookup"><span data-stu-id="cfb91-113">Primary</span></span>  <br/> |<span data-ttu-id="cfb91-114">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="cfb91-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="cfb91-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="cfb91-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="cfb91-116">Char(1</span><span class="sxs-lookup"><span data-stu-id="cfb91-116">char(1)</span></span>  <br/> |<span data-ttu-id="cfb91-117">Principal</span><span class="sxs-lookup"><span data-stu-id="cfb91-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="cfb91-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="cfb91-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="cfb91-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="cfb91-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="cfb91-120">Principal</span><span class="sxs-lookup"><span data-stu-id="cfb91-120">Primary</span></span>  <br/> |<span data-ttu-id="cfb91-121">Nom de domaine complet du pool hébergeant la session.</span><span class="sxs-lookup"><span data-stu-id="cfb91-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="cfb91-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="cfb91-122">**AuthType**</span></span> <br/> |<span data-ttu-id="cfb91-123">int</span><span class="sxs-lookup"><span data-stu-id="cfb91-123">int</span></span>  <br/> |<span data-ttu-id="cfb91-124">Principal</span><span class="sxs-lookup"><span data-stu-id="cfb91-124">Primary</span></span>  <br/> |<span data-ttu-id="cfb91-125">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="cfb91-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="cfb91-126">Les informations de priorité sont stockées dans la [table CallPriorities dans Skype entreprise Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="cfb91-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="cfb91-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="cfb91-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="cfb91-128">bigint</span><span class="sxs-lookup"><span data-stu-id="cfb91-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="cfb91-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="cfb91-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="cfb91-130">bigint</span><span class="sxs-lookup"><span data-stu-id="cfb91-130">bigint</span></span>  <br/> ||<span data-ttu-id="cfb91-131">Nombre total de messages instantanés échangés lors de la session.</span><span class="sxs-lookup"><span data-stu-id="cfb91-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

