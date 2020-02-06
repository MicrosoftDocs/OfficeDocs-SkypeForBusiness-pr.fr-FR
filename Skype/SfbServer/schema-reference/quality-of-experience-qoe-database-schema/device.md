---
title: Table Device
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un appareil.
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810152"
---
# <a name="device-table"></a><span data-ttu-id="ecd5f-104">Table Device</span><span class="sxs-lookup"><span data-stu-id="ecd5f-104">Device table</span></span>
 
<span data-ttu-id="ecd5f-105">La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="ecd5f-106">Chaque enregistrement de la table représente un appareil.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="ecd5f-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ecd5f-107">**Column**</span></span>|<span data-ttu-id="ecd5f-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="ecd5f-108">**Data Type**</span></span>|<span data-ttu-id="ecd5f-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="ecd5f-109">**Key/Index**</span></span>|<span data-ttu-id="ecd5f-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="ecd5f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ecd5f-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="ecd5f-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="ecd5f-112">int</span><span class="sxs-lookup"><span data-stu-id="ecd5f-112">int</span></span>  <br/> |<span data-ttu-id="ecd5f-113">Principal</span><span class="sxs-lookup"><span data-stu-id="ecd5f-113">Primary</span></span>  <br/> |<span data-ttu-id="ecd5f-114">Numéro unique identifiant cet appareil.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="ecd5f-115">**Périphérique**</span><span class="sxs-lookup"><span data-stu-id="ecd5f-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="ecd5f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ecd5f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ecd5f-117">Nom_unité + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="ecd5f-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="ecd5f-118">Nom de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="ecd5f-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="ecd5f-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="ecd5f-120">bit</span><span class="sxs-lookup"><span data-stu-id="ecd5f-120">bit</span></span>  <br/> |<span data-ttu-id="ecd5f-121">Nom_unité + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="ecd5f-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="ecd5f-122">Type d’appareil.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-122">Device type.</span></span> <span data-ttu-id="ecd5f-123">1 est un appareil de capture ; 0 est un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

