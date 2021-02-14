---
title: Table DeviceDriver
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: La table DeviceDriver est une table de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou par un périphérique de rendu.
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823074"
---
# <a name="devicedriver-table"></a><span data-ttu-id="e0911-104">Table DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="e0911-104">DeviceDriver table</span></span>
 
<span data-ttu-id="e0911-p102">La table DeviceDriver est une table de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou par un périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="e0911-p102">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="e0911-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e0911-107">**Column**</span></span>|<span data-ttu-id="e0911-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e0911-108">**Data Type**</span></span>|<span data-ttu-id="e0911-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e0911-109">**Key/Index**</span></span>|<span data-ttu-id="e0911-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e0911-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0911-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="e0911-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="e0911-112">int</span><span class="sxs-lookup"><span data-stu-id="e0911-112">int</span></span>  <br/> |<span data-ttu-id="e0911-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="e0911-113">Primary</span></span>  <br/> |<span data-ttu-id="e0911-114">Numéro unique d’identification de cet enregistrement de pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="e0911-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="e0911-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="e0911-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="e0911-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="e0911-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="e0911-117">unique</span><span class="sxs-lookup"><span data-stu-id="e0911-117">unique</span></span>  <br/> |<span data-ttu-id="e0911-118">Nom du pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="e0911-118">Device driver name.</span></span>  <br/> |
   

