---
title: Table AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811442"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="556fe-104">Table AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="556fe-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="556fe-105">La table AppliedBandwidthSource est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="556fe-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="556fe-106">Chaque enregistrement représente une source.</span><span class="sxs-lookup"><span data-stu-id="556fe-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="556fe-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="556fe-107">**Column**</span></span>|<span data-ttu-id="556fe-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="556fe-108">**Data Type**</span></span>|<span data-ttu-id="556fe-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="556fe-109">**Key/Index**</span></span>|<span data-ttu-id="556fe-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="556fe-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="556fe-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="556fe-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="556fe-112">int</span><span class="sxs-lookup"><span data-stu-id="556fe-112">int</span></span>  <br/> |<span data-ttu-id="556fe-113">Principal</span><span class="sxs-lookup"><span data-stu-id="556fe-113">Primary</span></span>  <br/> |<span data-ttu-id="556fe-114">Numéro unique identifiant la source.</span><span class="sxs-lookup"><span data-stu-id="556fe-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="556fe-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="556fe-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="556fe-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="556fe-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="556fe-117">Différent</span><span class="sxs-lookup"><span data-stu-id="556fe-117">Unique</span></span>  <br/> |<span data-ttu-id="556fe-118">Il s’agit de la source de la bande passante qui est imposée.</span><span class="sxs-lookup"><span data-stu-id="556fe-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="556fe-119">Il décrit l’emplacement vers lequel la limite de bande passante provient (par exemple, « serveur de stratégie », « activer le serveur » ou « modalité »).</span><span class="sxs-lookup"><span data-stu-id="556fe-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

