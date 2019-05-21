---
title: Table IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe les adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’utilisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294921"
---
# <a name="ipaddress-table"></a><span data-ttu-id="02337-104">Table IPAddress</span><span class="sxs-lookup"><span data-stu-id="02337-104">IPAddress table</span></span>
 
<span data-ttu-id="02337-105">La table IPAddress mappe les adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="02337-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="02337-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02337-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="02337-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="02337-107">**Column**</span></span>|<span data-ttu-id="02337-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="02337-108">**Data Type**</span></span>|<span data-ttu-id="02337-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="02337-109">**Key/Index**</span></span>|<span data-ttu-id="02337-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="02337-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="02337-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="02337-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="02337-112">int</span><span class="sxs-lookup"><span data-stu-id="02337-112">int</span></span>  <br/> |<span data-ttu-id="02337-113">Principal</span><span class="sxs-lookup"><span data-stu-id="02337-113">Primary</span></span>  <br/> |<span data-ttu-id="02337-114">Identificateur unique de l’adresse IP spécifiée.</span><span class="sxs-lookup"><span data-stu-id="02337-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="02337-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="02337-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="02337-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="02337-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="02337-117">Différent</span><span class="sxs-lookup"><span data-stu-id="02337-117">Unique</span></span>  <br/> |<span data-ttu-id="02337-118">Une adresse IP unique (par exemple, 189.168.1.1) qui correspond à IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="02337-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="02337-119">Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="02337-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

