---
title: Table ConferenceJoinTimeThresholds dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse du temps de connexion à la conférence. Ce rapport récapitule le temps nécessaire aux utilisateurs pour se joindre à une conférence. Ces valeurs de temps représentent à la fois une moyenne et l’une des catégories suivantes :'
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813304"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a9ca3-104">Table ConferenceJoinTimeThresholds dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="a9ca3-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a9ca3-p102">La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse du temps de connexion à la conférence. Ce rapport récapitule le temps nécessaire aux utilisateurs pour se joindre à une conférence. Ces valeurs de temps représentent à la fois une moyenne et l’une des catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9ca3-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="a9ca3-107">Moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="a9ca3-108">Entre 2 et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="a9ca3-109">Entre 5 et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="a9ca3-110">Plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="a9ca3-111">La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="a9ca3-112">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a9ca3-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a9ca3-113">**Column**</span></span>|<span data-ttu-id="a9ca3-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a9ca3-114">**Data Type**</span></span>|<span data-ttu-id="a9ca3-115">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="a9ca3-115">**Key/Index**</span></span>|<span data-ttu-id="a9ca3-116">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a9ca3-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9ca3-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="a9ca3-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="a9ca3-118">int</span><span class="sxs-lookup"><span data-stu-id="a9ca3-118">int</span></span>  <br/> |<span data-ttu-id="a9ca3-119">Primaire</span><span class="sxs-lookup"><span data-stu-id="a9ca3-119">Primary</span></span>  <br/> |<span data-ttu-id="a9ca3-120">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="a9ca3-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="a9ca3-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="a9ca3-122">int</span><span class="sxs-lookup"><span data-stu-id="a9ca3-122">int</span></span>  <br/> || <span data-ttu-id="a9ca3-p103">Limite supérieure de la classification. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9ca3-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="a9ca3-125">2 </span><span class="sxs-lookup"><span data-stu-id="a9ca3-125">2</span></span> <br/>  <span data-ttu-id="a9ca3-126">5 </span><span class="sxs-lookup"><span data-stu-id="a9ca3-126">5</span></span> <br/>  <span data-ttu-id="a9ca3-127">10 </span><span class="sxs-lookup"><span data-stu-id="a9ca3-127">10</span></span> <br/> |
   

