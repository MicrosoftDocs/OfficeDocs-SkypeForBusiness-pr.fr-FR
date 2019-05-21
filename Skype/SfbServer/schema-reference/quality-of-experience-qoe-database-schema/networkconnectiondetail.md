---
title: Table NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail associe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’utilisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294816"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="7a18a-104">Table NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="7a18a-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="7a18a-105">La table NetworkConnectionDetail associe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="7a18a-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="7a18a-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a18a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7a18a-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="7a18a-107">**Column**</span></span>|<span data-ttu-id="7a18a-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="7a18a-108">**Data Type**</span></span>|<span data-ttu-id="7a18a-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="7a18a-109">**Key/Index**</span></span>|<span data-ttu-id="7a18a-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="7a18a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a18a-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="7a18a-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="7a18a-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="7a18a-112">tinyint</span></span>  <br/> |<span data-ttu-id="7a18a-113">Principal</span><span class="sxs-lookup"><span data-stu-id="7a18a-113">Primary</span></span>  <br/> |<span data-ttu-id="7a18a-114">Identificateur unique du type de connexion réseau.</span><span class="sxs-lookup"><span data-stu-id="7a18a-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="7a18a-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="7a18a-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="7a18a-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7a18a-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="7a18a-117">Différent</span><span class="sxs-lookup"><span data-stu-id="7a18a-117">Unique</span></span>  <br/> |<span data-ttu-id="7a18a-118">Type de connexion réseau correspondant au NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="7a18a-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="7a18a-119">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7a18a-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="7a18a-120">0--filaire</span><span class="sxs-lookup"><span data-stu-id="7a18a-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="7a18a-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="7a18a-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="7a18a-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="7a18a-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="7a18a-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="7a18a-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="7a18a-124">4--autre</span><span class="sxs-lookup"><span data-stu-id="7a18a-124">4 -- Other</span></span>  <br/> <span data-ttu-id="7a18a-125">5--tunnel</span><span class="sxs-lookup"><span data-stu-id="7a18a-125">5 -- Tunnel</span></span>  <br/> |
   

