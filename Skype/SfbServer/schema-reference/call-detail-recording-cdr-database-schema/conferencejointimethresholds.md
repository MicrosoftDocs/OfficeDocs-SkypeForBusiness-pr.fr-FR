---
title: Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de résumé de conférence joindre le temps. Le rapport Résumé de conférence jointure temps résume le délai requis pour les utilisateurs avec succès à participer à une conférence ; Ces valeurs d’heure sont signalés à la fois sous la forme d’une moyenne et dans une des catégories suivantes :'
ms.openlocfilehash: 3646337c9e9f20ac0b1dabfdd5504ce83dfa5c40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="64215-104">Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="64215-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="64215-105">La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de résumé de conférence joindre le temps.</span><span class="sxs-lookup"><span data-stu-id="64215-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="64215-106">Le rapport Résumé de conférence jointure temps résume le délai requis pour les utilisateurs avec succès à participer à une conférence ; Ces valeurs d’heure sont signalés à la fois sous la forme d’une moyenne et dans une des catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="64215-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="64215-107">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="64215-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="64215-108">Entre 2 secondes et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="64215-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="64215-109">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="64215-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="64215-110">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="64215-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="64215-111">La table ConferenceJoinTimeThresholds contient les valeurs de classement à 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="64215-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="64215-112">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64215-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="64215-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="64215-113">**Column**</span></span>|<span data-ttu-id="64215-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="64215-114">**Data Type**</span></span>|<span data-ttu-id="64215-115">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="64215-115">**Key/Index**</span></span>|<span data-ttu-id="64215-116">**Détails**</span><span class="sxs-lookup"><span data-stu-id="64215-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="64215-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="64215-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="64215-118">int</span><span class="sxs-lookup"><span data-stu-id="64215-118">int</span></span>  <br/> |<span data-ttu-id="64215-119">Principal</span><span class="sxs-lookup"><span data-stu-id="64215-119">Primary</span></span>  <br/> |<span data-ttu-id="64215-120">Identificateur unique pour la classification.</span><span class="sxs-lookup"><span data-stu-id="64215-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="64215-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="64215-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="64215-122">int</span><span class="sxs-lookup"><span data-stu-id="64215-122">int</span></span>  <br/> || <span data-ttu-id="64215-123">Limite supérieure pour la classification.</span><span class="sxs-lookup"><span data-stu-id="64215-123">Upper limit for the classification.</span></span> <span data-ttu-id="64215-124">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="64215-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="64215-125">2</span><span class="sxs-lookup"><span data-stu-id="64215-125">2</span></span> <br/>  <span data-ttu-id="64215-126">5</span><span class="sxs-lookup"><span data-stu-id="64215-126">5</span></span> <br/>  <span data-ttu-id="64215-127">10</span><span class="sxs-lookup"><span data-stu-id="64215-127">10</span></span> <br/> |
   

