---
title: Table AppliedBandwidthSource
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La table AppliedBandwidthSource est un tableau de prise en charge. Chaque enregistrement représente une source.
ms.openlocfilehash: e15df92423a3408e3cb8ae40a0788e1f165961df
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="88233-104">Table AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="88233-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="88233-105">La table AppliedBandwidthSource est un tableau de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="88233-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="88233-106">Chaque enregistrement représente une source.</span><span class="sxs-lookup"><span data-stu-id="88233-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="88233-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="88233-107">**Column**</span></span>|<span data-ttu-id="88233-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="88233-108">**Data Type**</span></span>|<span data-ttu-id="88233-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="88233-109">**Key/Index**</span></span>|<span data-ttu-id="88233-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="88233-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="88233-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="88233-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="88233-112">int</span><span class="sxs-lookup"><span data-stu-id="88233-112">int</span></span>  <br/> |<span data-ttu-id="88233-113">Principal</span><span class="sxs-lookup"><span data-stu-id="88233-113">Primary</span></span>  <br/> |<span data-ttu-id="88233-114">Numéro unique identifiant la source.</span><span class="sxs-lookup"><span data-stu-id="88233-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="88233-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="88233-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="88233-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="88233-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="88233-117">Unique</span><span class="sxs-lookup"><span data-stu-id="88233-117">Unique</span></span>  <br/> |<span data-ttu-id="88233-118">Il s’agit de la source de l’embout de la bande passante est imposée.</span><span class="sxs-lookup"><span data-stu-id="88233-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="88233-119">Il décrit la limite de bande passante provenance (par exemple, « Policy Server », « Arrêter le serveur » ou « Modalité »).</span><span class="sxs-lookup"><span data-stu-id="88233-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

