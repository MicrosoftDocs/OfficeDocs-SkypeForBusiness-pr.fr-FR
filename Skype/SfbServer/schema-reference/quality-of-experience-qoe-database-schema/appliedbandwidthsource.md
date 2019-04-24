---
title: Table AppliedBandwidthSource
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212354"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="81d2d-104">Table AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="81d2d-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="81d2d-105">La table AppliedBandwidthSource est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="81d2d-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="81d2d-106">Chaque enregistrement représente une source.</span><span class="sxs-lookup"><span data-stu-id="81d2d-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="81d2d-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="81d2d-107">**Column**</span></span>|<span data-ttu-id="81d2d-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="81d2d-108">**Data Type**</span></span>|<span data-ttu-id="81d2d-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="81d2d-109">**Key/Index**</span></span>|<span data-ttu-id="81d2d-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="81d2d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81d2d-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="81d2d-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="81d2d-112">int</span><span class="sxs-lookup"><span data-stu-id="81d2d-112">int</span></span>  <br/> |<span data-ttu-id="81d2d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="81d2d-113">Primary</span></span>  <br/> |<span data-ttu-id="81d2d-114">Numéro unique identifiant la source.</span><span class="sxs-lookup"><span data-stu-id="81d2d-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="81d2d-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="81d2d-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="81d2d-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="81d2d-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="81d2d-117">Unique</span><span class="sxs-lookup"><span data-stu-id="81d2d-117">Unique</span></span>  <br/> |<span data-ttu-id="81d2d-118">Il s’agit de la source de l’extrémité de la bande passante imposée en cours.</span><span class="sxs-lookup"><span data-stu-id="81d2d-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="81d2d-119">Il décrit la limite de bande passante provenance (par exemple, « Stratégie de serveur », « Activer le serveur » ou « Modalité »).</span><span class="sxs-lookup"><span data-stu-id="81d2d-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

