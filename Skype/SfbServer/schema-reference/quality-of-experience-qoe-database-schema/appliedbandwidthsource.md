---
title: Table AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831404"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="d13cc-104">Table AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="d13cc-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="d13cc-p102">La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.</span><span class="sxs-lookup"><span data-stu-id="d13cc-p102">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>
  
|<span data-ttu-id="d13cc-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d13cc-107">**Column**</span></span>|<span data-ttu-id="d13cc-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d13cc-108">**Data Type**</span></span>|<span data-ttu-id="d13cc-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="d13cc-109">**Key/Index**</span></span>|<span data-ttu-id="d13cc-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="d13cc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d13cc-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="d13cc-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="d13cc-112">int</span><span class="sxs-lookup"><span data-stu-id="d13cc-112">int</span></span>  <br/> |<span data-ttu-id="d13cc-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="d13cc-113">Primary</span></span>  <br/> |<span data-ttu-id="d13cc-114">Numéro unique d’identification de cette source.</span><span class="sxs-lookup"><span data-stu-id="d13cc-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="d13cc-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="d13cc-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="d13cc-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="d13cc-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="d13cc-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="d13cc-117">Unique</span></span>  <br/> |<span data-ttu-id="d13cc-118">Il s’agit de la source de la capacité de bande passante imposée.</span><span class="sxs-lookup"><span data-stu-id="d13cc-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="d13cc-119">Il décrit l’emplacement d’où vient la limite de bande passante (par exemple, « Serveur de stratégie », « SERVEUR TURN » ou « Modalité »).</span><span class="sxs-lookup"><span data-stu-id="d13cc-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

