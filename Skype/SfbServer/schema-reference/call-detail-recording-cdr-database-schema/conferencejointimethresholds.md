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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence. Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence ; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes :'
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815392"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1bf66-104">Table ConferenceJoinTimeThresholds dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="1bf66-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1bf66-105">La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="1bf66-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="1bf66-106">Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence ; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="1bf66-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="1bf66-107">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="1bf66-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="1bf66-108">Entre 2 secondes et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="1bf66-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="1bf66-109">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="1bf66-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="1bf66-110">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="1bf66-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="1bf66-111">La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="1bf66-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="1bf66-112">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1bf66-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="1bf66-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1bf66-113">**Column**</span></span>|<span data-ttu-id="1bf66-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1bf66-114">**Data Type**</span></span>|<span data-ttu-id="1bf66-115">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="1bf66-115">**Key/Index**</span></span>|<span data-ttu-id="1bf66-116">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1bf66-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1bf66-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="1bf66-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="1bf66-118">int</span><span class="sxs-lookup"><span data-stu-id="1bf66-118">int</span></span>  <br/> |<span data-ttu-id="1bf66-119">Principal</span><span class="sxs-lookup"><span data-stu-id="1bf66-119">Primary</span></span>  <br/> |<span data-ttu-id="1bf66-120">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="1bf66-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="1bf66-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="1bf66-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="1bf66-122">int</span><span class="sxs-lookup"><span data-stu-id="1bf66-122">int</span></span>  <br/> || <span data-ttu-id="1bf66-123">Limite supérieure de la classification.</span><span class="sxs-lookup"><span data-stu-id="1bf66-123">Upper limit for the classification.</span></span> <span data-ttu-id="1bf66-124">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="1bf66-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="1bf66-125">deuxième</span><span class="sxs-lookup"><span data-stu-id="1bf66-125">2</span></span> <br/>  <span data-ttu-id="1bf66-126">5</span><span class="sxs-lookup"><span data-stu-id="1bf66-126">5</span></span> <br/>  <span data-ttu-id="1bf66-127">0,10</span><span class="sxs-lookup"><span data-stu-id="1bf66-127">10</span></span> <br/> |
   

