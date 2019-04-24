---
title: Table IPAddress
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe des adresses IP pour les identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212206"
---
# <a name="ipaddress-table"></a><span data-ttu-id="c4040-104">Table IPAddress</span><span class="sxs-lookup"><span data-stu-id="c4040-104">IPAddress table</span></span>
 
<span data-ttu-id="c4040-105">La table IPAddress mappe des adresses IP pour les identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="c4040-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="c4040-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4040-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c4040-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c4040-107">**Column**</span></span>|<span data-ttu-id="c4040-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c4040-108">**Data Type**</span></span>|<span data-ttu-id="c4040-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c4040-109">**Key/Index**</span></span>|<span data-ttu-id="c4040-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c4040-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4040-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="c4040-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="c4040-112">int</span><span class="sxs-lookup"><span data-stu-id="c4040-112">int</span></span>  <br/> |<span data-ttu-id="c4040-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c4040-113">Primary</span></span>  <br/> |<span data-ttu-id="c4040-114">Identificateur unique de l’adresse IP spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c4040-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="c4040-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="c4040-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="c4040-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="c4040-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="c4040-117">Unique</span><span class="sxs-lookup"><span data-stu-id="c4040-117">Unique</span></span>  <br/> |<span data-ttu-id="c4040-118">Adresse IP unique (par exemple, 189.168.1.1) qui correspond à la IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="c4040-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="c4040-119">Cela peut être soit une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="c4040-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

