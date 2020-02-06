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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail associe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’utilisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807502"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="a22e5-104">Table NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="a22e5-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="a22e5-105">La table NetworkConnectionDetail associe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="a22e5-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a22e5-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22e5-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a22e5-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a22e5-107">**Column**</span></span>|<span data-ttu-id="a22e5-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a22e5-108">**Data Type**</span></span>|<span data-ttu-id="a22e5-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="a22e5-109">**Key/Index**</span></span>|<span data-ttu-id="a22e5-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a22e5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a22e5-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="a22e5-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="a22e5-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="a22e5-112">tinyint</span></span>  <br/> |<span data-ttu-id="a22e5-113">Principal</span><span class="sxs-lookup"><span data-stu-id="a22e5-113">Primary</span></span>  <br/> |<span data-ttu-id="a22e5-114">Identificateur unique du type de connexion réseau.</span><span class="sxs-lookup"><span data-stu-id="a22e5-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="a22e5-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="a22e5-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="a22e5-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="a22e5-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="a22e5-117">Différent</span><span class="sxs-lookup"><span data-stu-id="a22e5-117">Unique</span></span>  <br/> |<span data-ttu-id="a22e5-118">Type de connexion réseau correspondant au NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="a22e5-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="a22e5-119">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a22e5-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="a22e5-120">0--filaire</span><span class="sxs-lookup"><span data-stu-id="a22e5-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="a22e5-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="a22e5-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="a22e5-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="a22e5-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="a22e5-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="a22e5-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="a22e5-124">4--autre</span><span class="sxs-lookup"><span data-stu-id="a22e5-124">4 -- Other</span></span>  <br/> <span data-ttu-id="a22e5-125">5--tunnel</span><span class="sxs-lookup"><span data-stu-id="a22e5-125">5 -- Tunnel</span></span>  <br/> |
   

