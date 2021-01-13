---
title: Table Device
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814744"
---
# <a name="device-table"></a><span data-ttu-id="b22c2-104">Table Device</span><span class="sxs-lookup"><span data-stu-id="b22c2-104">Device table</span></span>
 
<span data-ttu-id="b22c2-p102">La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.</span><span class="sxs-lookup"><span data-stu-id="b22c2-p102">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="b22c2-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b22c2-107">**Column**</span></span>|<span data-ttu-id="b22c2-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b22c2-108">**Data Type**</span></span>|<span data-ttu-id="b22c2-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b22c2-109">**Key/Index**</span></span>|<span data-ttu-id="b22c2-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="b22c2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b22c2-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="b22c2-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="b22c2-112">int</span><span class="sxs-lookup"><span data-stu-id="b22c2-112">int</span></span>  <br/> |<span data-ttu-id="b22c2-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="b22c2-113">Primary</span></span>  <br/> |<span data-ttu-id="b22c2-114">Numéro unique qui identifie ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="b22c2-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="b22c2-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="b22c2-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="b22c2-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b22c2-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b22c2-117">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="b22c2-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="b22c2-118">Nom du périphérique.</span><span class="sxs-lookup"><span data-stu-id="b22c2-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="b22c2-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="b22c2-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="b22c2-120">bit</span><span class="sxs-lookup"><span data-stu-id="b22c2-120">bit</span></span>  <br/> |<span data-ttu-id="b22c2-121">DeviceName + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="b22c2-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="b22c2-p103">Type de périphérique. 1 correspond à un périphérique de capture, 0 à un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="b22c2-p103">Device type. 1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

