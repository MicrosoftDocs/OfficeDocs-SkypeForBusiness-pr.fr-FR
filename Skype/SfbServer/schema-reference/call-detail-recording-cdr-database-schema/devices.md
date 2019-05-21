---
title: Tableau des appareils dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Le tableau appareils est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296377"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="49baa-104">Tableau des appareils dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="49baa-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="49baa-105">Le tableau appareils est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="49baa-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="49baa-106">Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="49baa-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="49baa-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="49baa-107">**Column**</span></span>|<span data-ttu-id="49baa-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="49baa-108">**Data Type**</span></span>|<span data-ttu-id="49baa-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="49baa-109">**Key/Index**</span></span>|<span data-ttu-id="49baa-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="49baa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="49baa-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="49baa-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="49baa-112">int</span><span class="sxs-lookup"><span data-stu-id="49baa-112">int</span></span>  <br/> |<span data-ttu-id="49baa-113">Principal</span><span class="sxs-lookup"><span data-stu-id="49baa-113">Primary</span></span>  <br/> |<span data-ttu-id="49baa-114">Numéro unique identifiant cette version matérielle.</span><span class="sxs-lookup"><span data-stu-id="49baa-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="49baa-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="49baa-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="49baa-116">int</span><span class="sxs-lookup"><span data-stu-id="49baa-116">int</span></span>  <br/> |<span data-ttu-id="49baa-117">Externes</span><span class="sxs-lookup"><span data-stu-id="49baa-117">Foreign</span></span>  <br/> |<span data-ttu-id="49baa-118">Fabricant de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="49baa-118">Manufacturer of this device.</span></span> <span data-ttu-id="49baa-119">Pour plus d’informations, reportez-vous [à la table constructeurs dans Skype entreprise Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="49baa-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="49baa-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="49baa-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="49baa-121">int</span><span class="sxs-lookup"><span data-stu-id="49baa-121">int</span></span>  <br/> |<span data-ttu-id="49baa-122">Externes</span><span class="sxs-lookup"><span data-stu-id="49baa-122">Foreign</span></span>  <br/> |<span data-ttu-id="49baa-123">Version matérielle de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="49baa-123">Hardware version of this device.</span></span> <span data-ttu-id="49baa-124">Pour plus d’informations, reportez-vous [à la table HardwareVersions dans Skype entreprise Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="49baa-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="49baa-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="49baa-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="49baa-126">bigint</span><span class="sxs-lookup"><span data-stu-id="49baa-126">bigint</span></span>  <br/> ||<span data-ttu-id="49baa-127">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="49baa-127">MAC Address</span></span>  <br/> |
   

