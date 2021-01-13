---
title: Table IPAddress
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802774"
---
# <a name="ipaddress-table"></a><span data-ttu-id="3576c-104">Table IPAddress</span><span class="sxs-lookup"><span data-stu-id="3576c-104">IPAddress table</span></span>
 
<span data-ttu-id="3576c-105">La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="3576c-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3576c-106">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3576c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3576c-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3576c-107">**Column**</span></span>|<span data-ttu-id="3576c-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="3576c-108">**Data Type**</span></span>|<span data-ttu-id="3576c-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="3576c-109">**Key/Index**</span></span>|<span data-ttu-id="3576c-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="3576c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3576c-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="3576c-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="3576c-112">int</span><span class="sxs-lookup"><span data-stu-id="3576c-112">int</span></span>  <br/> |<span data-ttu-id="3576c-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="3576c-113">Primary</span></span>  <br/> |<span data-ttu-id="3576c-114">Identificateur unique pour l’adresse IP spécifiée.</span><span class="sxs-lookup"><span data-stu-id="3576c-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="3576c-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="3576c-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="3576c-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="3576c-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="3576c-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="3576c-117">Unique</span></span>  <br/> |<span data-ttu-id="3576c-p103">Adresse IP unique (par exemple, 189.168.1.1) qui est mappée à IpAddressKey. Il peut d’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="3576c-p103">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

