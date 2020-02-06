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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Le tableau appareils est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815282"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6e6a1-104">Tableau des appareils dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="6e6a1-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6e6a1-105">Le tableau appareils est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="6e6a1-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="6e6a1-106">Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="6e6a1-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="6e6a1-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6e6a1-107">**Column**</span></span>|<span data-ttu-id="6e6a1-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="6e6a1-108">**Data Type**</span></span>|<span data-ttu-id="6e6a1-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="6e6a1-109">**Key/Index**</span></span>|<span data-ttu-id="6e6a1-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="6e6a1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e6a1-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="6e6a1-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="6e6a1-112">int</span><span class="sxs-lookup"><span data-stu-id="6e6a1-112">int</span></span>  <br/> |<span data-ttu-id="6e6a1-113">Principal</span><span class="sxs-lookup"><span data-stu-id="6e6a1-113">Primary</span></span>  <br/> |<span data-ttu-id="6e6a1-114">Numéro unique identifiant cette version matérielle.</span><span class="sxs-lookup"><span data-stu-id="6e6a1-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="6e6a1-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="6e6a1-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="6e6a1-116">int</span><span class="sxs-lookup"><span data-stu-id="6e6a1-116">int</span></span>  <br/> |<span data-ttu-id="6e6a1-117">Externes</span><span class="sxs-lookup"><span data-stu-id="6e6a1-117">Foreign</span></span>  <br/> |<span data-ttu-id="6e6a1-118">Fabricant de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="6e6a1-118">Manufacturer of this device.</span></span> <span data-ttu-id="6e6a1-119">Pour plus d’informations, reportez-vous [à la table constructeurs dans Skype entreprise Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="6e6a1-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6e6a1-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="6e6a1-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="6e6a1-121">int</span><span class="sxs-lookup"><span data-stu-id="6e6a1-121">int</span></span>  <br/> |<span data-ttu-id="6e6a1-122">Externes</span><span class="sxs-lookup"><span data-stu-id="6e6a1-122">Foreign</span></span>  <br/> |<span data-ttu-id="6e6a1-123">Version matérielle de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="6e6a1-123">Hardware version of this device.</span></span> <span data-ttu-id="6e6a1-124">Pour plus d’informations, reportez-vous [à la table HardwareVersions dans Skype entreprise Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="6e6a1-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6e6a1-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="6e6a1-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="6e6a1-126">bigint</span><span class="sxs-lookup"><span data-stu-id="6e6a1-126">bigint</span></span>  <br/> ||<span data-ttu-id="6e6a1-127">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="6e6a1-127">MAC Address</span></span>  <br/> |
   

