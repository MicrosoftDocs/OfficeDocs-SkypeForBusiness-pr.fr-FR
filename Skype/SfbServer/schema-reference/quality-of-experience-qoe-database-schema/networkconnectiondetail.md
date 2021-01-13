---
title: Table NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données Qualité de l’expérience (QoE). Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806304"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="e849b-104">Table NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="e849b-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="e849b-105">La table NetworkConnectionDetail mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données Qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="e849b-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="e849b-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e849b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e849b-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e849b-107">**Column**</span></span>|<span data-ttu-id="e849b-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e849b-108">**Data Type**</span></span>|<span data-ttu-id="e849b-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e849b-109">**Key/Index**</span></span>|<span data-ttu-id="e849b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e849b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e849b-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="e849b-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="e849b-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="e849b-112">tinyint</span></span>  <br/> |<span data-ttu-id="e849b-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="e849b-113">Primary</span></span>  <br/> |<span data-ttu-id="e849b-114">Identificateur unique du type de connexion réseau.</span><span class="sxs-lookup"><span data-stu-id="e849b-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="e849b-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="e849b-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="e849b-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="e849b-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="e849b-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="e849b-117">Unique</span></span>  <br/> |<span data-ttu-id="e849b-p103">Type de connexion réseau correspondant à la valeur NetworkConnectionDetailKey. Les valeurs autorisées sont les suivantes :
</span><span class="sxs-lookup"><span data-stu-id="e849b-p103">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span>  <br/> <span data-ttu-id="e849b-120">0 -- Câblé</span><span class="sxs-lookup"><span data-stu-id="e849b-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="e849b-121">1 -- WiFi</span><span class="sxs-lookup"><span data-stu-id="e849b-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="e849b-122">2 -- Ethernet</span><span class="sxs-lookup"><span data-stu-id="e849b-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="e849b-123">3 -- MobileBB</span><span class="sxs-lookup"><span data-stu-id="e849b-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="e849b-124">4 -- Autre</span><span class="sxs-lookup"><span data-stu-id="e849b-124">4 -- Other</span></span>  <br/> <span data-ttu-id="e849b-125">5 -- Tunnel</span><span class="sxs-lookup"><span data-stu-id="e849b-125">5 -- Tunnel</span></span>  <br/> |
   

