---
title: Table Device
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Le tableau de périphérique est une table de prise en charge qui stocke des informations sur la capture différents ou les appareils de rendu. Chaque enregistrement de la table représente un périphérique.
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885511"
---
# <a name="device-table"></a><span data-ttu-id="6af31-104">Table Device</span><span class="sxs-lookup"><span data-stu-id="6af31-104">Device table</span></span>
 
<span data-ttu-id="6af31-105">Le tableau de périphérique est une table de prise en charge qui stocke des informations sur la capture différents ou les appareils de rendu.</span><span class="sxs-lookup"><span data-stu-id="6af31-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="6af31-106">Chaque enregistrement de la table représente un périphérique.</span><span class="sxs-lookup"><span data-stu-id="6af31-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="6af31-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6af31-107">**Column**</span></span>|<span data-ttu-id="6af31-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="6af31-108">**Data Type**</span></span>|<span data-ttu-id="6af31-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="6af31-109">**Key/Index**</span></span>|<span data-ttu-id="6af31-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="6af31-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6af31-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="6af31-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="6af31-112">int</span><span class="sxs-lookup"><span data-stu-id="6af31-112">int</span></span>  <br/> |<span data-ttu-id="6af31-113">Principal</span><span class="sxs-lookup"><span data-stu-id="6af31-113">Primary</span></span>  <br/> |<span data-ttu-id="6af31-114">Numéro unique qui identifie ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="6af31-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="6af31-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="6af31-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="6af31-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6af31-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6af31-117">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="6af31-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="6af31-118">Nom du périphérique.</span><span class="sxs-lookup"><span data-stu-id="6af31-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="6af31-119">**Type d’appareil**</span><span class="sxs-lookup"><span data-stu-id="6af31-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="6af31-120">bit</span><span class="sxs-lookup"><span data-stu-id="6af31-120">bit</span></span>  <br/> |<span data-ttu-id="6af31-121">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="6af31-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="6af31-122">Type d’appareil.</span><span class="sxs-lookup"><span data-stu-id="6af31-122">Device type.</span></span> <span data-ttu-id="6af31-123">1 est un périphérique de capture, 0 correspond à un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="6af31-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

