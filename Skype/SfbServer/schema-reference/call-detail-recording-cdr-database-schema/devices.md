---
title: Table Devices dans Skype Entreprise Server 2015
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
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La table Devices est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831814"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3b2e7-104">Table Devices dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="3b2e7-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3b2e7-105">La table Devices est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="3b2e7-106">Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).</span><span class="sxs-lookup"><span data-stu-id="3b2e7-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="3b2e7-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3b2e7-107">**Column**</span></span>|<span data-ttu-id="3b2e7-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="3b2e7-108">**Data Type**</span></span>|<span data-ttu-id="3b2e7-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="3b2e7-109">**Key/Index**</span></span>|<span data-ttu-id="3b2e7-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="3b2e7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b2e7-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="3b2e7-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="3b2e7-112">int</span><span class="sxs-lookup"><span data-stu-id="3b2e7-112">int</span></span>  <br/> |<span data-ttu-id="3b2e7-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="3b2e7-113">Primary</span></span>  <br/> |<span data-ttu-id="3b2e7-114">Numéro unique identifiant cette version du matériel.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="3b2e7-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="3b2e7-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="3b2e7-116">int</span><span class="sxs-lookup"><span data-stu-id="3b2e7-116">int</span></span>  <br/> |<span data-ttu-id="3b2e7-117">Étranger</span><span class="sxs-lookup"><span data-stu-id="3b2e7-117">Foreign</span></span>  <br/> |<span data-ttu-id="3b2e7-118">Fabricant de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-118">Manufacturer of this device.</span></span> <span data-ttu-id="3b2e7-119">Pour plus d’informations, voir le tableau Manufacturers dans [Skype Entreprise Server 2015.](manufacturers.md)</span><span class="sxs-lookup"><span data-stu-id="3b2e7-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3b2e7-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="3b2e7-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="3b2e7-121">int</span><span class="sxs-lookup"><span data-stu-id="3b2e7-121">int</span></span>  <br/> |<span data-ttu-id="3b2e7-122">Étranger</span><span class="sxs-lookup"><span data-stu-id="3b2e7-122">Foreign</span></span>  <br/> |<span data-ttu-id="3b2e7-123">Version du matériel de cet appareil.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-123">Hardware version of this device.</span></span> <span data-ttu-id="3b2e7-124">Pour plus d’informations, voir le tableau HardwareVersions dans Skype Entreprise [Server 2015.](hardwareversions.md)</span><span class="sxs-lookup"><span data-stu-id="3b2e7-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3b2e7-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="3b2e7-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="3b2e7-126">bigint</span><span class="sxs-lookup"><span data-stu-id="3b2e7-126">bigint</span></span>  <br/> ||<span data-ttu-id="3b2e7-127">Adresse MAC</span><span class="sxs-lookup"><span data-stu-id="3b2e7-127">MAC Address</span></span>  <br/> |
   

