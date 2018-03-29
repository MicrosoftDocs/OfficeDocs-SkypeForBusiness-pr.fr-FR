---
title: Table d’adresse IP
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe les adresses IP pour les identificateurs uniques d’adresse IP utilisées ailleurs dans la base de données de qualité. Cette table a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a><span data-ttu-id="27169-104">Table d’adresse IP</span><span class="sxs-lookup"><span data-stu-id="27169-104">IPAddress table</span></span>
 
<span data-ttu-id="27169-105">La table IPAddress mappe les adresses IP pour les identificateurs uniques d’adresse IP utilisées ailleurs dans la base de données de qualité.</span><span class="sxs-lookup"><span data-stu-id="27169-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="27169-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27169-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="27169-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="27169-107">**Column**</span></span>|<span data-ttu-id="27169-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="27169-108">**Data Type**</span></span>|<span data-ttu-id="27169-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="27169-109">**Key/Index**</span></span>|<span data-ttu-id="27169-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="27169-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27169-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="27169-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="27169-112">int</span><span class="sxs-lookup"><span data-stu-id="27169-112">int</span></span>  <br/> |<span data-ttu-id="27169-113">Principal</span><span class="sxs-lookup"><span data-stu-id="27169-113">Primary</span></span>  <br/> |<span data-ttu-id="27169-114">Identificateur unique de l’adresse IP spécifiée.</span><span class="sxs-lookup"><span data-stu-id="27169-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="27169-115">**Adresse IP**</span><span class="sxs-lookup"><span data-stu-id="27169-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="27169-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="27169-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="27169-117">Unique</span><span class="sxs-lookup"><span data-stu-id="27169-117">Unique</span></span>  <br/> |<span data-ttu-id="27169-118">Adresse IP unique (par exemple, 189.168.1.1) qui correspond à la IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="27169-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="27169-119">Cela peut être soit une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="27169-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

