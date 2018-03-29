---
title: Table DeviceDriver
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: La table DeviceDriver est un tableau de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou périphérique de rendu.
ms.openlocfilehash: d5882ba853bd4909863fc5da415c993d4b59ea4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="devicedriver-table"></a><span data-ttu-id="165c0-104">Table DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="165c0-104">DeviceDriver table</span></span>
 
<span data-ttu-id="165c0-105">La table DeviceDriver est un tableau de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="165c0-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="165c0-106">Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="165c0-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="165c0-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="165c0-107">**Column**</span></span>|<span data-ttu-id="165c0-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="165c0-108">**Data Type**</span></span>|<span data-ttu-id="165c0-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="165c0-109">**Key/Index**</span></span>|<span data-ttu-id="165c0-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="165c0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="165c0-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="165c0-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="165c0-112">int</span><span class="sxs-lookup"><span data-stu-id="165c0-112">int</span></span>  <br/> |<span data-ttu-id="165c0-113">Principal</span><span class="sxs-lookup"><span data-stu-id="165c0-113">Primary</span></span>  <br/> |<span data-ttu-id="165c0-114">Numéro unique identifiant cet enregistrement de pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="165c0-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="165c0-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="165c0-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="165c0-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="165c0-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="165c0-117">unique</span><span class="sxs-lookup"><span data-stu-id="165c0-117">unique</span></span>  <br/> |<span data-ttu-id="165c0-118">Nom du pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="165c0-118">Device driver name.</span></span>  <br/> |
   

