---
title: Table NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: a7095000cc996f2a6430ffcaf8411a2891872938
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919990"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="3deeb-104">Table NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="3deeb-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="3deeb-105">La table NetworkConnectionDetail mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="3deeb-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3deeb-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3deeb-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3deeb-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3deeb-107">**Column**</span></span>|<span data-ttu-id="3deeb-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="3deeb-108">**Data Type**</span></span>|<span data-ttu-id="3deeb-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="3deeb-109">**Key/Index**</span></span>|<span data-ttu-id="3deeb-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="3deeb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3deeb-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="3deeb-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="3deeb-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="3deeb-112">tinyint</span></span>  <br/> |<span data-ttu-id="3deeb-113">Principal</span><span class="sxs-lookup"><span data-stu-id="3deeb-113">Primary</span></span>  <br/> |<span data-ttu-id="3deeb-114">Identificateur unique pour le type de connexion réseau.</span><span class="sxs-lookup"><span data-stu-id="3deeb-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="3deeb-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="3deeb-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="3deeb-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="3deeb-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="3deeb-117">Unique</span><span class="sxs-lookup"><span data-stu-id="3deeb-117">Unique</span></span>  <br/> |<span data-ttu-id="3deeb-118">Type de connexion réseau qui correspond à la NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="3deeb-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="3deeb-119">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3deeb-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="3deeb-120">0--filaire</span><span class="sxs-lookup"><span data-stu-id="3deeb-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="3deeb-121">1--Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3deeb-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="3deeb-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="3deeb-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="3deeb-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="3deeb-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="3deeb-124">4--autres</span><span class="sxs-lookup"><span data-stu-id="3deeb-124">4 -- Other</span></span>  <br/> <span data-ttu-id="3deeb-125">5--tunnel</span><span class="sxs-lookup"><span data-stu-id="3deeb-125">5 -- Tunnel</span></span>  <br/> |
   

