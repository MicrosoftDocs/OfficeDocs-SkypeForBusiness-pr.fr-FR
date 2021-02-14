---
title: Table EndpointSubnet
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
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: La table EndpointSubnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau capturé depuis des systèmes d’extrémité.
ms.openlocfilehash: 9671c7dc269b7f13f0679c6da12b46ea7d7c8b5f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815824"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="decad-104">Table EndpointSubnet</span><span class="sxs-lookup"><span data-stu-id="decad-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="decad-p102">La table EndpointSubnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau capturé depuis des systèmes d’extrémité.</span><span class="sxs-lookup"><span data-stu-id="decad-p102">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="decad-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="decad-107">**Column**</span></span>|<span data-ttu-id="decad-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="decad-108">**Data Type**</span></span>|<span data-ttu-id="decad-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="decad-109">**Key/Index**</span></span>|<span data-ttu-id="decad-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="decad-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="decad-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="decad-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="decad-112">int</span><span class="sxs-lookup"><span data-stu-id="decad-112">int</span></span>  <br/> |<span data-ttu-id="decad-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="decad-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="decad-114">Représentation entière du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="decad-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="decad-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="decad-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="decad-116">DateHeure</span><span class="sxs-lookup"><span data-stu-id="decad-116">datetime</span></span>  <br/> ||<span data-ttu-id="decad-117">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="decad-117">For internal use only.</span></span>  <br/> |
   

