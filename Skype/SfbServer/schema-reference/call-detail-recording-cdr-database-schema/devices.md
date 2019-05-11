---
title: Table Devices dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Le tableau des périphériques est une table de prise en charge. Chaque enregistrement stocke des informations sur un périphérique (téléphone de bureau).
ms.openlocfilehash: efd0894a36e02948a3a8cd9f3465dcdbd30f3e2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901093"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="46bf8-104">Table Devices dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="46bf8-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="46bf8-105">Le tableau des périphériques est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="46bf8-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="46bf8-106">Chaque enregistrement stocke des informations sur un périphérique (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="46bf8-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="46bf8-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="46bf8-107">**Column**</span></span>|<span data-ttu-id="46bf8-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="46bf8-108">**Data Type**</span></span>|<span data-ttu-id="46bf8-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="46bf8-109">**Key/Index**</span></span>|<span data-ttu-id="46bf8-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="46bf8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46bf8-111">**ID de périphérique**</span><span class="sxs-lookup"><span data-stu-id="46bf8-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="46bf8-112">int</span><span class="sxs-lookup"><span data-stu-id="46bf8-112">int</span></span>  <br/> |<span data-ttu-id="46bf8-113">Principal</span><span class="sxs-lookup"><span data-stu-id="46bf8-113">Primary</span></span>  <br/> |<span data-ttu-id="46bf8-114">Numéro unique identifiant cette version matérielle.</span><span class="sxs-lookup"><span data-stu-id="46bf8-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="46bf8-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="46bf8-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="46bf8-116">int</span><span class="sxs-lookup"><span data-stu-id="46bf8-116">int</span></span>  <br/> |<span data-ttu-id="46bf8-117">Étrangère</span><span class="sxs-lookup"><span data-stu-id="46bf8-117">Foreign</span></span>  <br/> |<span data-ttu-id="46bf8-118">Fabricant du périphérique.</span><span class="sxs-lookup"><span data-stu-id="46bf8-118">Manufacturer of this device.</span></span> <span data-ttu-id="46bf8-119">Voir la [table Manufacturers dans Skype pour Business Server 2015](manufacturers.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="46bf8-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="46bf8-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="46bf8-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="46bf8-121">int</span><span class="sxs-lookup"><span data-stu-id="46bf8-121">int</span></span>  <br/> |<span data-ttu-id="46bf8-122">Étrangère</span><span class="sxs-lookup"><span data-stu-id="46bf8-122">Foreign</span></span>  <br/> |<span data-ttu-id="46bf8-123">Version du matériel de ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="46bf8-123">Hardware version of this device.</span></span> <span data-ttu-id="46bf8-124">Consultez la [table HardwareVersions dans Skype pour Business Server 2015](hardwareversions.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="46bf8-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="46bf8-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="46bf8-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="46bf8-126">bigint</span><span class="sxs-lookup"><span data-stu-id="46bf8-126">bigint</span></span>  <br/> ||<span data-ttu-id="46bf8-127">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="46bf8-127">MAC Address</span></span>  <br/> |
   

