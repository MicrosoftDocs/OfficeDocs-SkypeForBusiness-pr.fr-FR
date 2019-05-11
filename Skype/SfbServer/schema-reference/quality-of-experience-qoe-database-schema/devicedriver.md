---
title: Table DeviceDriver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: La DeviceDriver table est une table de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou périphérique de rendu.
ms.openlocfilehash: 9a011c7e555bad71f453510dca7c310e2467a505
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920172"
---
# <a name="devicedriver-table"></a><span data-ttu-id="91f99-104">Table DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="91f99-104">DeviceDriver table</span></span>
 
<span data-ttu-id="91f99-105">La DeviceDriver table est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="91f99-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="91f99-106">Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="91f99-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="91f99-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="91f99-107">**Column**</span></span>|<span data-ttu-id="91f99-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="91f99-108">**Data Type**</span></span>|<span data-ttu-id="91f99-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="91f99-109">**Key/Index**</span></span>|<span data-ttu-id="91f99-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="91f99-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91f99-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="91f99-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="91f99-112">int</span><span class="sxs-lookup"><span data-stu-id="91f99-112">int</span></span>  <br/> |<span data-ttu-id="91f99-113">Principal</span><span class="sxs-lookup"><span data-stu-id="91f99-113">Primary</span></span>  <br/> |<span data-ttu-id="91f99-114">Numéro unique identifiant cet enregistrement de pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="91f99-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="91f99-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="91f99-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="91f99-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="91f99-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="91f99-117">unique</span><span class="sxs-lookup"><span data-stu-id="91f99-117">unique</span></span>  <br/> |<span data-ttu-id="91f99-118">Nom du pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="91f99-118">Device driver name.</span></span>  <br/> |
   

