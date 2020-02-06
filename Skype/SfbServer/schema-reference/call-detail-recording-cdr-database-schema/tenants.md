---
title: Table Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table clients est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814852"
---
# <a name="tenants-table"></a><span data-ttu-id="eefcb-104">Table Tenants</span><span class="sxs-lookup"><span data-stu-id="eefcb-104">Tenants table</span></span>
 
<span data-ttu-id="eefcb-105">La table clients est une table de prise en charge qui stocke une liste des différents clients.</span><span class="sxs-lookup"><span data-stu-id="eefcb-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="eefcb-106">Chaque enregistrement de la table représente un client.</span><span class="sxs-lookup"><span data-stu-id="eefcb-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eefcb-107">Dans le cadre d’un déploiement local, le CDR utilise l’ID de locataire intégré pour indiquer un type d’authentification différent, tel que la connectivité de messagerie instantanée publique, fédéré et anonyme.</span><span class="sxs-lookup"><span data-stu-id="eefcb-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="eefcb-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="eefcb-108">**Column**</span></span>|<span data-ttu-id="eefcb-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="eefcb-109">**Data Type**</span></span>|<span data-ttu-id="eefcb-110">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="eefcb-110">**Key/Index**</span></span>|<span data-ttu-id="eefcb-111">**Détails**</span><span class="sxs-lookup"><span data-stu-id="eefcb-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eefcb-112">**IDClient**</span><span class="sxs-lookup"><span data-stu-id="eefcb-112">**TenantId**</span></span> <br/> |<span data-ttu-id="eefcb-113">int</span><span class="sxs-lookup"><span data-stu-id="eefcb-113">int</span></span>  <br/> |<span data-ttu-id="eefcb-114">Principal</span><span class="sxs-lookup"><span data-stu-id="eefcb-114">Primary</span></span>  <br/> |<span data-ttu-id="eefcb-115">Numéro unique identifiant cet ID de client.</span><span class="sxs-lookup"><span data-stu-id="eefcb-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="eefcb-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="eefcb-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="eefcb-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eefcb-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="eefcb-118">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="eefcb-118">Allowed values:</span></span> <br/>  <span data-ttu-id="eefcb-119">00000000-0000-0000-0000-000000000000-entreprise</span><span class="sxs-lookup"><span data-stu-id="eefcb-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="eefcb-120">00000000-0000-0000-0000-000000000001-Federated</span><span class="sxs-lookup"><span data-stu-id="eefcb-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="eefcb-121">00000000-0000-0000-0000-000000000002-anonyme</span><span class="sxs-lookup"><span data-stu-id="eefcb-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="eefcb-122">00000000-0000-0000-0000-000000000003-connectivité PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="eefcb-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

