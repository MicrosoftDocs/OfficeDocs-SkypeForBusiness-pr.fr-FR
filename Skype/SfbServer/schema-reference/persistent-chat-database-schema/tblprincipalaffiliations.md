---
title: tblPrincipalAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des endroits, y compris les groupes de sécurité de Services de domaine Active Directory, dans des conteneurs Active Directory, dans des domaines.
ms.openlocfilehash: 4e5529590a6a636c28c801392953c7fd69e9f649
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="07411-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="07411-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="07411-104">tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des endroits, y compris les groupes de sécurité de Services de domaine Active Directory, dans des conteneurs Active Directory, dans des domaines.</span><span class="sxs-lookup"><span data-stu-id="07411-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="07411-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="07411-105">**Columns**</span></span>

|<span data-ttu-id="07411-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="07411-106">**Column**</span></span>|<span data-ttu-id="07411-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="07411-107">**Type**</span></span>|<span data-ttu-id="07411-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="07411-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07411-109">principalID</span><span class="sxs-lookup"><span data-stu-id="07411-109">principalID</span></span>  <br/> |<span data-ttu-id="07411-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="07411-110">int, not null</span></span>  <br/> |<span data-ttu-id="07411-111">ID de l’entité de sécurité liée.</span><span class="sxs-lookup"><span data-stu-id="07411-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="07411-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="07411-112">affiliationID</span></span>  <br/> |<span data-ttu-id="07411-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="07411-113">int, not null</span></span>  <br/> |<span data-ttu-id="07411-114">ID de l’entité de sécurité représentant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="07411-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="07411-115">Chaque entité de sécurité (à l’exception du système-utilisateur-types) possède une affiliation de Self ainsi.</span><span class="sxs-lookup"><span data-stu-id="07411-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="07411-116">index</span><span class="sxs-lookup"><span data-stu-id="07411-116">index</span></span>  <br/> |<span data-ttu-id="07411-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="07411-117">int, not null</span></span>  <br/> |<span data-ttu-id="07411-118">Index.</span><span class="sxs-lookup"><span data-stu-id="07411-118">Index.</span></span> <span data-ttu-id="07411-119">La valeur d’affiliations Self est -1, et pour les autres affiliations augmente séquentiellement à partir de 1 dans chaque \<principalID, affiliationId\> pot.</span><span class="sxs-lookup"><span data-stu-id="07411-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="07411-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="07411-120">updatedBy</span></span>  <br/> |<span data-ttu-id="07411-121">int, non null</span><span class="sxs-lookup"><span data-stu-id="07411-121">int, not null</span></span>  <br/> |<span data-ttu-id="07411-122">Entité de sécurité qui ont fait de la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="07411-122">Principal that did the latest update.</span></span> <span data-ttu-id="07411-123">Il s’agit généralement de 1, ce qui signifie que la synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="07411-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="07411-124">**Clés**</span><span class="sxs-lookup"><span data-stu-id="07411-124">**Keys**</span></span>

|<span data-ttu-id="07411-125">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="07411-125">**Columns**</span></span>|<span data-ttu-id="07411-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="07411-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07411-127">\<principalID, index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="07411-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="07411-128">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="07411-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="07411-129">principalID</span><span class="sxs-lookup"><span data-stu-id="07411-129">principalID</span></span>  <br/> |<span data-ttu-id="07411-130">Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="07411-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="07411-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="07411-131">affiliationID</span></span>  <br/> |<span data-ttu-id="07411-132">Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="07411-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

