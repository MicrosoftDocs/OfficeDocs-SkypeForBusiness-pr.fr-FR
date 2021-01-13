---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des emplacements, y compris les groupes de sécurité des services de domaine Active Directory, dans les conteneurs Active Directory, dans les domaines.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815864"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="75230-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="75230-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="75230-104">tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des emplacements, y compris les groupes de sécurité des services de domaine Active Directory, dans les conteneurs Active Directory, dans les domaines.</span><span class="sxs-lookup"><span data-stu-id="75230-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="75230-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="75230-105">**Columns**</span></span>

|<span data-ttu-id="75230-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="75230-106">**Column**</span></span>|<span data-ttu-id="75230-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="75230-107">**Type**</span></span>|<span data-ttu-id="75230-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="75230-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75230-109">principalID</span><span class="sxs-lookup"><span data-stu-id="75230-109">principalID</span></span>  <br/> |<span data-ttu-id="75230-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="75230-110">int, not null</span></span>  <br/> |<span data-ttu-id="75230-111">ID du principal affilié.</span><span class="sxs-lookup"><span data-stu-id="75230-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="75230-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="75230-112">affiliationID</span></span>  <br/> |<span data-ttu-id="75230-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="75230-113">int, not null</span></span>  <br/> |<span data-ttu-id="75230-p101">ID du principal représentant l’affiliation. Chaque principal (sauf system-user-types) possède également une auto-affiliation.</span><span class="sxs-lookup"><span data-stu-id="75230-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="75230-116">Index</span><span class="sxs-lookup"><span data-stu-id="75230-116">index</span></span>  <br/> |<span data-ttu-id="75230-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="75230-117">int, not null</span></span>  <br/> |<span data-ttu-id="75230-118">Index.</span><span class="sxs-lookup"><span data-stu-id="75230-118">Index.</span></span> <span data-ttu-id="75230-119">La valeur pour les auto-affiliations est -1, et pour les autres affiliations, elle augmente séquentiellement à partir de 1 dans chaque \<principalID, affiliationId\> compartiment.</span><span class="sxs-lookup"><span data-stu-id="75230-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="75230-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="75230-120">updatedBy</span></span>  <br/> |<span data-ttu-id="75230-121">int, non null</span><span class="sxs-lookup"><span data-stu-id="75230-121">int, not null</span></span>  <br/> |<span data-ttu-id="75230-p103">Principal qui a effectué la mise à jour la plus récente. Il s’agit généralement de 1, ce qui signifie Active Directory Sync.</span><span class="sxs-lookup"><span data-stu-id="75230-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="75230-124">**Keys**</span><span class="sxs-lookup"><span data-stu-id="75230-124">**Keys**</span></span>

|<span data-ttu-id="75230-125">**Columns**</span><span class="sxs-lookup"><span data-stu-id="75230-125">**Columns**</span></span>|<span data-ttu-id="75230-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="75230-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="75230-127">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="75230-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="75230-128">principalID</span><span class="sxs-lookup"><span data-stu-id="75230-128">principalID</span></span>  <br/> |<span data-ttu-id="75230-129">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="75230-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="75230-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="75230-130">affiliationID</span></span>  <br/> |<span data-ttu-id="75230-131">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="75230-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

