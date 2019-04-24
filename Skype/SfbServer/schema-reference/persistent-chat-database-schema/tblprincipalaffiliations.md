---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent des appartenances dans les emplacements incluant les groupes de sécurité Active Directory Domain Services, dans les conteneurs Active Directory dans les domaines.
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212501"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="e852a-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="e852a-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="e852a-104">tblPrincipalAffiliations contient les affiliations principales qui décrivent des appartenances dans les emplacements incluant les groupes de sécurité Active Directory Domain Services, dans les conteneurs Active Directory dans les domaines.</span><span class="sxs-lookup"><span data-stu-id="e852a-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="e852a-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="e852a-105">**Columns**</span></span>

|<span data-ttu-id="e852a-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e852a-106">**Column**</span></span>|<span data-ttu-id="e852a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="e852a-107">**Type**</span></span>|<span data-ttu-id="e852a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e852a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e852a-109">principalID</span><span class="sxs-lookup"><span data-stu-id="e852a-109">principalID</span></span>  <br/> |<span data-ttu-id="e852a-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="e852a-110">int, not null</span></span>  <br/> |<span data-ttu-id="e852a-111">ID du principal affilié.</span><span class="sxs-lookup"><span data-stu-id="e852a-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="e852a-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e852a-112">affiliationID</span></span>  <br/> |<span data-ttu-id="e852a-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="e852a-113">int, not null</span></span>  <br/> |<span data-ttu-id="e852a-114">ID du principal qui représente l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="e852a-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="e852a-115">Chaque entité (à l’exception du système-utilisateur-types) possède une affiliation Self également.</span><span class="sxs-lookup"><span data-stu-id="e852a-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="e852a-116">index</span><span class="sxs-lookup"><span data-stu-id="e852a-116">index</span></span>  <br/> |<span data-ttu-id="e852a-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="e852a-117">int, not null</span></span>  <br/> |<span data-ttu-id="e852a-118">Index.</span><span class="sxs-lookup"><span data-stu-id="e852a-118">Index.</span></span> <span data-ttu-id="e852a-119">La valeur d’affiliations Self est -1, et pour les autres affiliations augmente en séquence de 1 au sein de chaque \<principalID, affiliationId\> compartiment.</span><span class="sxs-lookup"><span data-stu-id="e852a-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="e852a-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e852a-120">updatedBy</span></span>  <br/> |<span data-ttu-id="e852a-121">int, non null</span><span class="sxs-lookup"><span data-stu-id="e852a-121">int, not null</span></span>  <br/> |<span data-ttu-id="e852a-122">Principal ayant effectué la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="e852a-122">Principal that did the latest update.</span></span> <span data-ttu-id="e852a-123">Il s’agit généralement de 1, ce qui signifie que la synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e852a-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="e852a-124">**Clés**</span><span class="sxs-lookup"><span data-stu-id="e852a-124">**Keys**</span></span>

|<span data-ttu-id="e852a-125">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="e852a-125">**Columns**</span></span>|<span data-ttu-id="e852a-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="e852a-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e852a-127">\<principalID, index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="e852a-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="e852a-128">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e852a-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e852a-129">principalID</span><span class="sxs-lookup"><span data-stu-id="e852a-129">principalID</span></span>  <br/> |<span data-ttu-id="e852a-130">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e852a-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e852a-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e852a-131">affiliationID</span></span>  <br/> |<span data-ttu-id="e852a-132">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e852a-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

