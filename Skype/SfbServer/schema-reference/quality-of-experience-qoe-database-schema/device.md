---
title: Table Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Le tableau de périphérique est une table de prise en charge qui stocke des informations sur la capture différents ou les appareils de rendu. Chaque enregistrement de la table représente un périphérique.
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920025"
---
# <a name="device-table"></a><span data-ttu-id="1612d-104">Table Device</span><span class="sxs-lookup"><span data-stu-id="1612d-104">Device table</span></span>
 
<span data-ttu-id="1612d-105">Le tableau de périphérique est une table de prise en charge qui stocke des informations sur la capture différents ou les appareils de rendu.</span><span class="sxs-lookup"><span data-stu-id="1612d-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="1612d-106">Chaque enregistrement de la table représente un périphérique.</span><span class="sxs-lookup"><span data-stu-id="1612d-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="1612d-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1612d-107">**Column**</span></span>|<span data-ttu-id="1612d-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1612d-108">**Data Type**</span></span>|<span data-ttu-id="1612d-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="1612d-109">**Key/Index**</span></span>|<span data-ttu-id="1612d-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1612d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1612d-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="1612d-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="1612d-112">int</span><span class="sxs-lookup"><span data-stu-id="1612d-112">int</span></span>  <br/> |<span data-ttu-id="1612d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="1612d-113">Primary</span></span>  <br/> |<span data-ttu-id="1612d-114">Numéro unique qui identifie ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="1612d-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="1612d-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="1612d-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="1612d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1612d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1612d-117">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="1612d-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="1612d-118">Nom du périphérique.</span><span class="sxs-lookup"><span data-stu-id="1612d-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="1612d-119">**Type d’appareil**</span><span class="sxs-lookup"><span data-stu-id="1612d-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="1612d-120">bit</span><span class="sxs-lookup"><span data-stu-id="1612d-120">bit</span></span>  <br/> |<span data-ttu-id="1612d-121">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="1612d-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="1612d-122">Type d’appareil.</span><span class="sxs-lookup"><span data-stu-id="1612d-122">Device type.</span></span> <span data-ttu-id="1612d-123">1 est un périphérique de capture, 0 correspond à un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="1612d-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

