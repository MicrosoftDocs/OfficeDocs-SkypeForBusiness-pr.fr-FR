---
title: Table Subnet
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La table de sous-réseau est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans le paramètre de configuration réseau.
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a><span data-ttu-id="6d210-104">Table Subnet</span><span class="sxs-lookup"><span data-stu-id="6d210-104">Subnet table</span></span>
 
<span data-ttu-id="6d210-105">La table de sous-réseau est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="6d210-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="6d210-106">Chaque enregistrement représente un sous-réseau défini dans le paramètre de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="6d210-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="6d210-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6d210-107">**Column**</span></span>|<span data-ttu-id="6d210-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="6d210-108">**Data Type**</span></span>|<span data-ttu-id="6d210-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="6d210-109">**Key/Index**</span></span>|<span data-ttu-id="6d210-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="6d210-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6d210-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="6d210-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="6d210-112">int</span><span class="sxs-lookup"><span data-stu-id="6d210-112">int</span></span>  <br/> |<span data-ttu-id="6d210-113">Primaires et étrangères</span><span class="sxs-lookup"><span data-stu-id="6d210-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6d210-114">Représentation sous forme de nombre entier pour l’adresse IP du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="6d210-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="6d210-115">**Masque de sous-réseau**</span><span class="sxs-lookup"><span data-stu-id="6d210-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="6d210-116">int</span><span class="sxs-lookup"><span data-stu-id="6d210-116">int</span></span>  <br/> ||<span data-ttu-id="6d210-117">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="6d210-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="6d210-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="6d210-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="6d210-119">int</span><span class="sxs-lookup"><span data-stu-id="6d210-119">int</span></span>  <br/> |<span data-ttu-id="6d210-120">Étrangère</span><span class="sxs-lookup"><span data-stu-id="6d210-120">Foreign</span></span>  <br/> |<span data-ttu-id="6d210-121">Référencé à partir de la [table de UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="6d210-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="6d210-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="6d210-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="6d210-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="6d210-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="6d210-124">La description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="6d210-124">The description for the subnet.</span></span>  <br/> |
   

