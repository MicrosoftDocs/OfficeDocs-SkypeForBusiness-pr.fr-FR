---
title: Table Device
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table des périphériques est une table de prise en charge qui stocke des informations sur la capture différents ou restitue des périphériques. Chaque enregistrement de la table représente un périphérique.
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a><span data-ttu-id="14bac-104">Table Device</span><span class="sxs-lookup"><span data-stu-id="14bac-104">Device table</span></span>
 
<span data-ttu-id="14bac-105">La table des périphériques est une table de prise en charge qui stocke des informations sur la capture différents ou restitue des périphériques.</span><span class="sxs-lookup"><span data-stu-id="14bac-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="14bac-106">Chaque enregistrement de la table représente un périphérique.</span><span class="sxs-lookup"><span data-stu-id="14bac-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="14bac-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="14bac-107">**Column**</span></span>|<span data-ttu-id="14bac-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="14bac-108">**Data Type**</span></span>|<span data-ttu-id="14bac-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="14bac-109">**Key/Index**</span></span>|<span data-ttu-id="14bac-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="14bac-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14bac-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="14bac-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="14bac-112">int</span><span class="sxs-lookup"><span data-stu-id="14bac-112">int</span></span>  <br/> |<span data-ttu-id="14bac-113">Principal</span><span class="sxs-lookup"><span data-stu-id="14bac-113">Primary</span></span>  <br/> |<span data-ttu-id="14bac-114">Numéro unique identifiant ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="14bac-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="14bac-115">**Nom de périphérique**</span><span class="sxs-lookup"><span data-stu-id="14bac-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="14bac-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="14bac-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="14bac-117">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="14bac-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="14bac-118">Nom du périphérique.</span><span class="sxs-lookup"><span data-stu-id="14bac-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="14bac-119">**Type d’appareil**</span><span class="sxs-lookup"><span data-stu-id="14bac-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="14bac-120">bit</span><span class="sxs-lookup"><span data-stu-id="14bac-120">bit</span></span>  <br/> |<span data-ttu-id="14bac-121">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="14bac-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="14bac-122">Type de périphérique.</span><span class="sxs-lookup"><span data-stu-id="14bac-122">Device type.</span></span> <span data-ttu-id="14bac-123">1 est un périphérique de capture, 0 est un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="14bac-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

