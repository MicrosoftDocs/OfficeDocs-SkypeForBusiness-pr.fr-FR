---
title: Table Subnet
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831334"
---
# <a name="subnet-table"></a><span data-ttu-id="2edd1-104">Table Subnet</span><span class="sxs-lookup"><span data-stu-id="2edd1-104">Subnet table</span></span>
 
<span data-ttu-id="2edd1-p102">La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="2edd1-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="2edd1-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2edd1-107">**Column**</span></span>|<span data-ttu-id="2edd1-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2edd1-108">**Data Type**</span></span>|<span data-ttu-id="2edd1-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="2edd1-109">**Key/Index**</span></span>|<span data-ttu-id="2edd1-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="2edd1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2edd1-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="2edd1-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="2edd1-112">int</span><span class="sxs-lookup"><span data-stu-id="2edd1-112">int</span></span>  <br/> |<span data-ttu-id="2edd1-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2edd1-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2edd1-114">Représentation sous forme d’entier de l’adresse IP de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="2edd1-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="2edd1-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="2edd1-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="2edd1-116">int</span><span class="sxs-lookup"><span data-stu-id="2edd1-116">int</span></span>  <br/> ||<span data-ttu-id="2edd1-117">Masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="2edd1-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="2edd1-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="2edd1-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="2edd1-119">int</span><span class="sxs-lookup"><span data-stu-id="2edd1-119">int</span></span>  <br/> |<span data-ttu-id="2edd1-120">Étranger</span><span class="sxs-lookup"><span data-stu-id="2edd1-120">Foreign</span></span>  <br/> |<span data-ttu-id="2edd1-121">Référencé à partir de [la table UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="2edd1-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="2edd1-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="2edd1-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="2edd1-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="2edd1-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="2edd1-124">Description du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="2edd1-124">The description for the subnet.</span></span>  <br/> |
   

