---
title: Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de synthèse de conférence participer à temps. Le rapport de synthèse du temps de participer à une conférence résume le volume de temps requis pour les utilisateurs à prendre part à une conférence ; Ces valeurs sont signalés comme une moyenne et d’une des catégories suivantes :'
ms.openlocfilehash: 75df75e16d2a4ed34f667c94f2b2f0960f56e7ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901435"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cf26f-104">Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cf26f-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cf26f-105">La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de synthèse de conférence participer à temps.</span><span class="sxs-lookup"><span data-stu-id="cf26f-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="cf26f-106">Le rapport de synthèse du temps de participer à une conférence résume le volume de temps requis pour les utilisateurs à prendre part à une conférence ; Ces valeurs sont signalés comme une moyenne et d’une des catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="cf26f-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="cf26f-107">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="cf26f-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="cf26f-108">Entre 2 et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="cf26f-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="cf26f-109">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="cf26f-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="cf26f-110">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="cf26f-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="cf26f-111">La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="cf26f-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="cf26f-112">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf26f-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cf26f-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cf26f-113">**Column**</span></span>|<span data-ttu-id="cf26f-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="cf26f-114">**Data Type**</span></span>|<span data-ttu-id="cf26f-115">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="cf26f-115">**Key/Index**</span></span>|<span data-ttu-id="cf26f-116">**Détails**</span><span class="sxs-lookup"><span data-stu-id="cf26f-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf26f-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="cf26f-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="cf26f-118">int</span><span class="sxs-lookup"><span data-stu-id="cf26f-118">int</span></span>  <br/> |<span data-ttu-id="cf26f-119">Principal</span><span class="sxs-lookup"><span data-stu-id="cf26f-119">Primary</span></span>  <br/> |<span data-ttu-id="cf26f-120">Identificateur unique pour la classification.</span><span class="sxs-lookup"><span data-stu-id="cf26f-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="cf26f-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="cf26f-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="cf26f-122">int</span><span class="sxs-lookup"><span data-stu-id="cf26f-122">int</span></span>  <br/> || <span data-ttu-id="cf26f-123">Limite supérieure de la classification.</span><span class="sxs-lookup"><span data-stu-id="cf26f-123">Upper limit for the classification.</span></span> <span data-ttu-id="cf26f-124">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="cf26f-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="cf26f-125">2</span><span class="sxs-lookup"><span data-stu-id="cf26f-125">2</span></span> <br/>  <span data-ttu-id="cf26f-126">5</span><span class="sxs-lookup"><span data-stu-id="cf26f-126">5</span></span> <br/>  <span data-ttu-id="cf26f-127">10</span><span class="sxs-lookup"><span data-stu-id="cf26f-127">10</span></span> <br/> |
   

