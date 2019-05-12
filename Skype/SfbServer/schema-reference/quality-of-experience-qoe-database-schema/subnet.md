---
title: Table Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Le tableau de sous-réseau est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration réseau.
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907065"
---
# <a name="subnet-table"></a><span data-ttu-id="24ca8-104">Table Subnet</span><span class="sxs-lookup"><span data-stu-id="24ca8-104">Subnet table</span></span>
 
<span data-ttu-id="24ca8-105">Le tableau de sous-réseau est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="24ca8-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="24ca8-106">Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="24ca8-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="24ca8-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="24ca8-107">**Column**</span></span>|<span data-ttu-id="24ca8-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="24ca8-108">**Data Type**</span></span>|<span data-ttu-id="24ca8-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="24ca8-109">**Key/Index**</span></span>|<span data-ttu-id="24ca8-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="24ca8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24ca8-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="24ca8-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="24ca8-112">int</span><span class="sxs-lookup"><span data-stu-id="24ca8-112">int</span></span>  <br/> |<span data-ttu-id="24ca8-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="24ca8-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="24ca8-114">Représentation entière pour l’adresse IP de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="24ca8-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="24ca8-115">**Masque de sous-réseau**</span><span class="sxs-lookup"><span data-stu-id="24ca8-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="24ca8-116">int</span><span class="sxs-lookup"><span data-stu-id="24ca8-116">int</span></span>  <br/> ||<span data-ttu-id="24ca8-117">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="24ca8-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="24ca8-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="24ca8-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="24ca8-119">int</span><span class="sxs-lookup"><span data-stu-id="24ca8-119">int</span></span>  <br/> |<span data-ttu-id="24ca8-120">Étrangère</span><span class="sxs-lookup"><span data-stu-id="24ca8-120">Foreign</span></span>  <br/> |<span data-ttu-id="24ca8-121">Référencé depuis la [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="24ca8-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="24ca8-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="24ca8-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="24ca8-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="24ca8-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="24ca8-124">La description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="24ca8-124">The description for the subnet.</span></span>  <br/> |
   

