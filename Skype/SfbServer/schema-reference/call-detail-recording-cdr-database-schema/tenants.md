---
title: Table Tenants
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table Tenants est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831714"
---
# <a name="tenants-table"></a><span data-ttu-id="a25bc-104">Table Tenants</span><span class="sxs-lookup"><span data-stu-id="a25bc-104">Tenants table</span></span>
 
<span data-ttu-id="a25bc-p102">La table Tenants est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.</span><span class="sxs-lookup"><span data-stu-id="a25bc-p102">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a25bc-107">Dans les déploiement sur site, CDR utilise l’ID de client intégré pour indiquer différents types d’authentification, tels que la connectivité de messagerie instantanée publique, l’authentification fédérée et l’authentification anonyme.</span><span class="sxs-lookup"><span data-stu-id="a25bc-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="a25bc-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a25bc-108">**Column**</span></span>|<span data-ttu-id="a25bc-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a25bc-109">**Data Type**</span></span>|<span data-ttu-id="a25bc-110">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="a25bc-110">**Key/Index**</span></span>|<span data-ttu-id="a25bc-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="a25bc-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a25bc-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="a25bc-112">**TenantId**</span></span> <br/> |<span data-ttu-id="a25bc-113">int</span><span class="sxs-lookup"><span data-stu-id="a25bc-113">int</span></span>  <br/> |<span data-ttu-id="a25bc-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="a25bc-114">Primary</span></span>  <br/> |<span data-ttu-id="a25bc-115">Numéro unique identifiant cet ID de client.</span><span class="sxs-lookup"><span data-stu-id="a25bc-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="a25bc-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="a25bc-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="a25bc-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a25bc-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a25bc-118">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="a25bc-118">Allowed values:</span></span> <br/>  <span data-ttu-id="a25bc-119">00000000-0000-0000-0000-000000000000 - Entreprise</span><span class="sxs-lookup"><span data-stu-id="a25bc-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="a25bc-120">00000000-0000-0000-0000-000000000001 - Fédéré</span><span class="sxs-lookup"><span data-stu-id="a25bc-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="a25bc-121">00000000-0000-0000-0000-000000000002 - Anonyme</span><span class="sxs-lookup"><span data-stu-id="a25bc-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="a25bc-122">00000000-0000-0000-0000-000000000003 - Connectivité DE MESSAGERIE INSTANTANÉE publique</span><span class="sxs-lookup"><span data-stu-id="a25bc-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

