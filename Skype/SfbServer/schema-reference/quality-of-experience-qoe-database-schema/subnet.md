---
title: Table Subnet
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Le tableau de sous-réseau est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration réseau.
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880475"
---
# <a name="subnet-table"></a><span data-ttu-id="21901-104">Table Subnet</span><span class="sxs-lookup"><span data-stu-id="21901-104">Subnet table</span></span>
 
<span data-ttu-id="21901-105">Le tableau de sous-réseau est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="21901-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="21901-106">Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="21901-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="21901-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="21901-107">**Column**</span></span>|<span data-ttu-id="21901-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="21901-108">**Data Type**</span></span>|<span data-ttu-id="21901-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="21901-109">**Key/Index**</span></span>|<span data-ttu-id="21901-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="21901-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21901-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="21901-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="21901-112">int</span><span class="sxs-lookup"><span data-stu-id="21901-112">int</span></span>  <br/> |<span data-ttu-id="21901-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="21901-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="21901-114">Représentation entière pour l’adresse IP de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="21901-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="21901-115">**Masque de sous-réseau**</span><span class="sxs-lookup"><span data-stu-id="21901-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="21901-116">int</span><span class="sxs-lookup"><span data-stu-id="21901-116">int</span></span>  <br/> ||<span data-ttu-id="21901-117">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="21901-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="21901-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="21901-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="21901-119">int</span><span class="sxs-lookup"><span data-stu-id="21901-119">int</span></span>  <br/> |<span data-ttu-id="21901-120">Étrangère</span><span class="sxs-lookup"><span data-stu-id="21901-120">Foreign</span></span>  <br/> |<span data-ttu-id="21901-121">Référencé depuis la [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="21901-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="21901-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="21901-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="21901-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="21901-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="21901-124">La description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="21901-124">The description for the subnet.</span></span>  <br/> |
   

