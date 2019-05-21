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
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un appareil.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295005"
---
# <a name="device-table"></a><span data-ttu-id="aa8cd-104">Table Device</span><span class="sxs-lookup"><span data-stu-id="aa8cd-104">Device table</span></span>
 
<span data-ttu-id="aa8cd-105">La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu.</span><span class="sxs-lookup"><span data-stu-id="aa8cd-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="aa8cd-106">Chaque enregistrement de la table représente un appareil.</span><span class="sxs-lookup"><span data-stu-id="aa8cd-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="aa8cd-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="aa8cd-107">**Column**</span></span>|<span data-ttu-id="aa8cd-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="aa8cd-108">**Data Type**</span></span>|<span data-ttu-id="aa8cd-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="aa8cd-109">**Key/Index**</span></span>|<span data-ttu-id="aa8cd-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="aa8cd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa8cd-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="aa8cd-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="aa8cd-112">int</span><span class="sxs-lookup"><span data-stu-id="aa8cd-112">int</span></span>  <br/> |<span data-ttu-id="aa8cd-113">Principal</span><span class="sxs-lookup"><span data-stu-id="aa8cd-113">Primary</span></span>  <br/> |<span data-ttu-id="aa8cd-114">Numéro unique identifiant cet appareil.</span><span class="sxs-lookup"><span data-stu-id="aa8cd-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="aa8cd-115">**Périphérique**</span><span class="sxs-lookup"><span data-stu-id="aa8cd-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="aa8cd-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa8cd-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aa8cd-117">Nom_unité + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="aa8cd-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="aa8cd-118">Nom de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="aa8cd-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="aa8cd-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="aa8cd-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="aa8cd-120">bit</span><span class="sxs-lookup"><span data-stu-id="aa8cd-120">bit</span></span>  <br/> |<span data-ttu-id="aa8cd-121">Nom_unité + DeviceType est unique</span><span class="sxs-lookup"><span data-stu-id="aa8cd-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="aa8cd-122">Type d’appareil.</span><span class="sxs-lookup"><span data-stu-id="aa8cd-122">Device type.</span></span> <span data-ttu-id="aa8cd-123">1 est un appareil de capture; 0 est un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="aa8cd-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

