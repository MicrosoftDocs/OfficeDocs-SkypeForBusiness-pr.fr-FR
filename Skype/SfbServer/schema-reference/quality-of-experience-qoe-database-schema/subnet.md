---
title: Table Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La table de sous-réseau est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration du réseau.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294634"
---
# <a name="subnet-table"></a><span data-ttu-id="782bc-104">Table Subnet</span><span class="sxs-lookup"><span data-stu-id="782bc-104">Subnet table</span></span>
 
<span data-ttu-id="782bc-105">La table de sous-réseau est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="782bc-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="782bc-106">Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="782bc-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="782bc-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="782bc-107">**Column**</span></span>|<span data-ttu-id="782bc-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="782bc-108">**Data Type**</span></span>|<span data-ttu-id="782bc-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="782bc-109">**Key/Index**</span></span>|<span data-ttu-id="782bc-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="782bc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="782bc-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="782bc-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="782bc-112">int</span><span class="sxs-lookup"><span data-stu-id="782bc-112">int</span></span>  <br/> |<span data-ttu-id="782bc-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="782bc-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="782bc-114">Représentation entière de l’adresse IP du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="782bc-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="782bc-115">**Masque_sous_réseau**</span><span class="sxs-lookup"><span data-stu-id="782bc-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="782bc-116">int</span><span class="sxs-lookup"><span data-stu-id="782bc-116">int</span></span>  <br/> ||<span data-ttu-id="782bc-117">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="782bc-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="782bc-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="782bc-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="782bc-119">int</span><span class="sxs-lookup"><span data-stu-id="782bc-119">int</span></span>  <br/> |<span data-ttu-id="782bc-120">Externes</span><span class="sxs-lookup"><span data-stu-id="782bc-120">Foreign</span></span>  <br/> |<span data-ttu-id="782bc-121">Fait référence à partir de la [table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="782bc-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="782bc-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="782bc-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="782bc-123">nvarchar</span><span class="sxs-lookup"><span data-stu-id="782bc-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="782bc-124">Description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="782bc-124">The description for the subnet.</span></span>  <br/> |
   

