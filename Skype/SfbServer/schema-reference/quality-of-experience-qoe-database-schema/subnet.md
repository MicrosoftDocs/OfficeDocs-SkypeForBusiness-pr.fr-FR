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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212087"
---
# <a name="subnet-table"></a><span data-ttu-id="18f26-104">Table Subnet</span><span class="sxs-lookup"><span data-stu-id="18f26-104">Subnet table</span></span>
 
<span data-ttu-id="18f26-105">Le tableau de sous-réseau est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="18f26-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="18f26-106">Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="18f26-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="18f26-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="18f26-107">**Column**</span></span>|<span data-ttu-id="18f26-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="18f26-108">**Data Type**</span></span>|<span data-ttu-id="18f26-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="18f26-109">**Key/Index**</span></span>|<span data-ttu-id="18f26-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="18f26-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18f26-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="18f26-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="18f26-112">int</span><span class="sxs-lookup"><span data-stu-id="18f26-112">int</span></span>  <br/> |<span data-ttu-id="18f26-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="18f26-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="18f26-114">Représentation entière pour l’adresse IP de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="18f26-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="18f26-115">**Masque de sous-réseau**</span><span class="sxs-lookup"><span data-stu-id="18f26-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="18f26-116">int</span><span class="sxs-lookup"><span data-stu-id="18f26-116">int</span></span>  <br/> ||<span data-ttu-id="18f26-117">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="18f26-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="18f26-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="18f26-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="18f26-119">int</span><span class="sxs-lookup"><span data-stu-id="18f26-119">int</span></span>  <br/> |<span data-ttu-id="18f26-120">Étrangère</span><span class="sxs-lookup"><span data-stu-id="18f26-120">Foreign</span></span>  <br/> |<span data-ttu-id="18f26-121">Référencé depuis la [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="18f26-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="18f26-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="18f26-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="18f26-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="18f26-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="18f26-124">La description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="18f26-124">The description for the subnet.</span></span>  <br/> |
   

