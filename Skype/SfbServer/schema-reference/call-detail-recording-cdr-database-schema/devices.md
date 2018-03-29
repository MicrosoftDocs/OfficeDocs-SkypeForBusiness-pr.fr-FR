---
title: Table de périphériques dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La table des périphériques est une table de prise en charge. Chaque enregistrement contient des informations sur un périphérique (téléphone de bureau).
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d42b4-104">Table de périphériques dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d42b4-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d42b4-105">La table des périphériques est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d42b4-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="d42b4-106">Chaque enregistrement contient des informations sur un périphérique (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="d42b4-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="d42b4-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d42b4-107">**Column**</span></span>|<span data-ttu-id="d42b4-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d42b4-108">**Data Type**</span></span>|<span data-ttu-id="d42b4-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="d42b4-109">**Key/Index**</span></span>|<span data-ttu-id="d42b4-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="d42b4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d42b4-111">**ID de périphérique**</span><span class="sxs-lookup"><span data-stu-id="d42b4-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="d42b4-112">int</span><span class="sxs-lookup"><span data-stu-id="d42b4-112">int</span></span>  <br/> |<span data-ttu-id="d42b4-113">Principal</span><span class="sxs-lookup"><span data-stu-id="d42b4-113">Primary</span></span>  <br/> |<span data-ttu-id="d42b4-114">Numéro unique identifiant la version de ce matériel.</span><span class="sxs-lookup"><span data-stu-id="d42b4-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="d42b4-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="d42b4-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="d42b4-116">int</span><span class="sxs-lookup"><span data-stu-id="d42b4-116">int</span></span>  <br/> |<span data-ttu-id="d42b4-117">Étrangère</span><span class="sxs-lookup"><span data-stu-id="d42b4-117">Foreign</span></span>  <br/> |<span data-ttu-id="d42b4-118">Fabricant de ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="d42b4-118">Manufacturer of this device.</span></span> <span data-ttu-id="d42b4-119">Consultez le [tableau des fabricants dans Skype pour Business Server 2015](manufacturers.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="d42b4-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d42b4-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="d42b4-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="d42b4-121">int</span><span class="sxs-lookup"><span data-stu-id="d42b4-121">int</span></span>  <br/> |<span data-ttu-id="d42b4-122">Étrangère</span><span class="sxs-lookup"><span data-stu-id="d42b4-122">Foreign</span></span>  <br/> |<span data-ttu-id="d42b4-123">Version du matériel de ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="d42b4-123">Hardware version of this device.</span></span> <span data-ttu-id="d42b4-124">Consultez la [table HardwareVersions dans Skype pour Business Server 2015](hardwareversions.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="d42b4-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d42b4-125">**Adresse MAC**</span><span class="sxs-lookup"><span data-stu-id="d42b4-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="d42b4-126">bigint</span><span class="sxs-lookup"><span data-stu-id="d42b4-126">bigint</span></span>  <br/> ||<span data-ttu-id="d42b4-127">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="d42b4-127">MAC Address</span></span>  <br/> |
   

