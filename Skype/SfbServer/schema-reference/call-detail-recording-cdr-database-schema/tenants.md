---
title: Table Tenants
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table de locataires est une table de support qui stocke une liste des locataires différents. Chaque enregistrement de la table représente un locataire.
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a><span data-ttu-id="99c27-104">Table Tenants</span><span class="sxs-lookup"><span data-stu-id="99c27-104">Tenants table</span></span>
 
<span data-ttu-id="99c27-105">La table de locataires est une table de support qui stocke une liste des locataires différents.</span><span class="sxs-lookup"><span data-stu-id="99c27-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="99c27-106">Chaque enregistrement de la table représente un locataire.</span><span class="sxs-lookup"><span data-stu-id="99c27-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99c27-107">Dans un déploiement sur site, CDR utilise le nom de build locataire pour indiquer le type d’authentification, telles que la connectivité PIC, fédéré et anonyme.</span><span class="sxs-lookup"><span data-stu-id="99c27-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="99c27-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="99c27-108">**Column**</span></span>|<span data-ttu-id="99c27-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="99c27-109">**Data Type**</span></span>|<span data-ttu-id="99c27-110">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="99c27-110">**Key/Index**</span></span>|<span data-ttu-id="99c27-111">**Détails**</span><span class="sxs-lookup"><span data-stu-id="99c27-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="99c27-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="99c27-112">**TenantId**</span></span> <br/> |<span data-ttu-id="99c27-113">int</span><span class="sxs-lookup"><span data-stu-id="99c27-113">int</span></span>  <br/> |<span data-ttu-id="99c27-114">Principal</span><span class="sxs-lookup"><span data-stu-id="99c27-114">Primary</span></span>  <br/> |<span data-ttu-id="99c27-115">Numéro unique qui identifie ce code de client.</span><span class="sxs-lookup"><span data-stu-id="99c27-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="99c27-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="99c27-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="99c27-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="99c27-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="99c27-118">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="99c27-118">Allowed values:</span></span> <br/>  <span data-ttu-id="99c27-119">00000000-0000-0000-0000-000000000000-entreprise</span><span class="sxs-lookup"><span data-stu-id="99c27-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="99c27-120">00000000-0000-0000-0000-000000000001-fédéré</span><span class="sxs-lookup"><span data-stu-id="99c27-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="99c27-121">Valeur 00000000-0000-0000-0000-000000000002 - anonyme</span><span class="sxs-lookup"><span data-stu-id="99c27-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="99c27-122">00000000-0000-0000-0000-000000000003-la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="99c27-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

