---
title: Table Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table clients est une table de prise en charge qui stocke une liste de ces locataires différents. Chaque enregistrement de la table représente un client.
ms.openlocfilehash: 68050ce76cc41d3fd66931fbdc0b0d3168786bc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930205"
---
# <a name="tenants-table"></a><span data-ttu-id="2d5a5-104">Table Tenants</span><span class="sxs-lookup"><span data-stu-id="2d5a5-104">Tenants table</span></span>
 
<span data-ttu-id="2d5a5-105">La table clients est une table de prise en charge qui stocke une liste de ces locataires différents.</span><span class="sxs-lookup"><span data-stu-id="2d5a5-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="2d5a5-106">Chaque enregistrement de la table représente un client.</span><span class="sxs-lookup"><span data-stu-id="2d5a5-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d5a5-107">Dans un déploiement sur site, CDR utilise l’ID de client intégré pour indiquer différents types d’authentification, telles que la connectivité PIC, fédérés et anonymes.</span><span class="sxs-lookup"><span data-stu-id="2d5a5-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="2d5a5-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2d5a5-108">**Column**</span></span>|<span data-ttu-id="2d5a5-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2d5a5-109">**Data Type**</span></span>|<span data-ttu-id="2d5a5-110">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="2d5a5-110">**Key/Index**</span></span>|<span data-ttu-id="2d5a5-111">**Détails**</span><span class="sxs-lookup"><span data-stu-id="2d5a5-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d5a5-112">**ID client sur**</span><span class="sxs-lookup"><span data-stu-id="2d5a5-112">**TenantId**</span></span> <br/> |<span data-ttu-id="2d5a5-113">int</span><span class="sxs-lookup"><span data-stu-id="2d5a5-113">int</span></span>  <br/> |<span data-ttu-id="2d5a5-114">Principal</span><span class="sxs-lookup"><span data-stu-id="2d5a5-114">Primary</span></span>  <br/> |<span data-ttu-id="2d5a5-115">Numéro unique identifiant cet ID de client.</span><span class="sxs-lookup"><span data-stu-id="2d5a5-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="2d5a5-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="2d5a5-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="2d5a5-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2d5a5-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2d5a5-118">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="2d5a5-118">Allowed values:</span></span> <br/>  <span data-ttu-id="2d5a5-119">00000000-0000-0000-0000-000000000000-entreprise</span><span class="sxs-lookup"><span data-stu-id="2d5a5-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="2d5a5-120">00000000-0000-0000-0000-000000000001-fédéré</span><span class="sxs-lookup"><span data-stu-id="2d5a5-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="2d5a5-121">Valeur 00000000-0000-0000-0000-000000000002 - anonyme</span><span class="sxs-lookup"><span data-stu-id="2d5a5-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="2d5a5-122">00000000-0000-0000-0000-000000000003-la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="2d5a5-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

