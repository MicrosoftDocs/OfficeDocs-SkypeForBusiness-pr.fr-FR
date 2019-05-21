---
title: Table ConferenceJoinTimeThresholds dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence. Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296496"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7633e-104">Table ConferenceJoinTimeThresholds dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7633e-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7633e-105">La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="7633e-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="7633e-106">Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes:</span><span class="sxs-lookup"><span data-stu-id="7633e-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="7633e-107">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="7633e-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="7633e-108">Entre 2 secondes et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="7633e-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="7633e-109">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="7633e-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="7633e-110">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="7633e-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="7633e-111">La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="7633e-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="7633e-112">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7633e-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7633e-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="7633e-113">**Column**</span></span>|<span data-ttu-id="7633e-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="7633e-114">**Data Type**</span></span>|<span data-ttu-id="7633e-115">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="7633e-115">**Key/Index**</span></span>|<span data-ttu-id="7633e-116">**Détails**</span><span class="sxs-lookup"><span data-stu-id="7633e-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7633e-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="7633e-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="7633e-118">int</span><span class="sxs-lookup"><span data-stu-id="7633e-118">int</span></span>  <br/> |<span data-ttu-id="7633e-119">Principal</span><span class="sxs-lookup"><span data-stu-id="7633e-119">Primary</span></span>  <br/> |<span data-ttu-id="7633e-120">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="7633e-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="7633e-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="7633e-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="7633e-122">int</span><span class="sxs-lookup"><span data-stu-id="7633e-122">int</span></span>  <br/> || <span data-ttu-id="7633e-123">Limite supérieure de la classification.</span><span class="sxs-lookup"><span data-stu-id="7633e-123">Upper limit for the classification.</span></span> <span data-ttu-id="7633e-124">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7633e-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="7633e-125">2</span><span class="sxs-lookup"><span data-stu-id="7633e-125">2</span></span> <br/>  <span data-ttu-id="7633e-126">5</span><span class="sxs-lookup"><span data-stu-id="7633e-126">5</span></span> <br/>  <span data-ttu-id="7633e-127">0,10</span><span class="sxs-lookup"><span data-stu-id="7633e-127">10</span></span> <br/> |
   

