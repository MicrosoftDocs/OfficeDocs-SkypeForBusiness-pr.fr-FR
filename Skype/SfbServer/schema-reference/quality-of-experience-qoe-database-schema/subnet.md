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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La table de sous-réseau est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration du réseau.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805202"
---
# <a name="subnet-table"></a><span data-ttu-id="a95af-104">Table Subnet</span><span class="sxs-lookup"><span data-stu-id="a95af-104">Subnet table</span></span>
 
<span data-ttu-id="a95af-105">La table de sous-réseau est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a95af-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="a95af-106">Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="a95af-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="a95af-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a95af-107">**Column**</span></span>|<span data-ttu-id="a95af-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a95af-108">**Data Type**</span></span>|<span data-ttu-id="a95af-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="a95af-109">**Key/Index**</span></span>|<span data-ttu-id="a95af-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a95af-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a95af-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="a95af-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="a95af-112">int</span><span class="sxs-lookup"><span data-stu-id="a95af-112">int</span></span>  <br/> |<span data-ttu-id="a95af-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="a95af-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a95af-114">Représentation entière de l’adresse IP du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="a95af-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="a95af-115">**Masque_sous_réseau**</span><span class="sxs-lookup"><span data-stu-id="a95af-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="a95af-116">int</span><span class="sxs-lookup"><span data-stu-id="a95af-116">int</span></span>  <br/> ||<span data-ttu-id="a95af-117">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="a95af-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="a95af-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="a95af-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="a95af-119">int</span><span class="sxs-lookup"><span data-stu-id="a95af-119">int</span></span>  <br/> |<span data-ttu-id="a95af-120">Externes</span><span class="sxs-lookup"><span data-stu-id="a95af-120">Foreign</span></span>  <br/> |<span data-ttu-id="a95af-121">Fait référence à partir de la [table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="a95af-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="a95af-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="a95af-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="a95af-123">nvarchar</span><span class="sxs-lookup"><span data-stu-id="a95af-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="a95af-124">Description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="a95af-124">The description for the subnet.</span></span>  <br/> |
   

