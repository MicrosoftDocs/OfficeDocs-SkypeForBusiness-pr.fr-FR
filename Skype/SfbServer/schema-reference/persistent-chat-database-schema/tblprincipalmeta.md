---
title: tblPrincipalMeta
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les identités qui doivent être actualisées à partir des Services de domaine Active Directory.
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="9a96e-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="9a96e-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="9a96e-104">tblPrincipalMeta contient les identités qui doivent être actualisées à partir des Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a96e-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="9a96e-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="9a96e-105">**Columns**</span></span>

|<span data-ttu-id="9a96e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9a96e-106">**Column**</span></span>|<span data-ttu-id="9a96e-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="9a96e-107">**Type**</span></span>|<span data-ttu-id="9a96e-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="9a96e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a96e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9a96e-109">prinID</span></span>  <br/> |<span data-ttu-id="9a96e-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="9a96e-110">int, not null</span></span>  <br/> |<span data-ttu-id="9a96e-111">ID d’entité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="9a96e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9a96e-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="9a96e-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="9a96e-113">bits, non null</span><span class="sxs-lookup"><span data-stu-id="9a96e-113">bit, not null</span></span>  <br/> |<span data-ttu-id="9a96e-114">True si l’entité de sécurité affiliations doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="9a96e-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="9a96e-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="9a96e-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="9a96e-116">bits, non null</span><span class="sxs-lookup"><span data-stu-id="9a96e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="9a96e-117">True si l’entité de sécurité attributs doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="9a96e-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="9a96e-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="9a96e-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="9a96e-119">bits, non null</span><span class="sxs-lookup"><span data-stu-id="9a96e-119">bit, not null</span></span>  <br/> |<span data-ttu-id="9a96e-120">True si l’entité de sécurité a été supprimée.</span><span class="sxs-lookup"><span data-stu-id="9a96e-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="9a96e-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="9a96e-121">tryCount</span></span>  <br/> |<span data-ttu-id="9a96e-122">int</span><span class="sxs-lookup"><span data-stu-id="9a96e-122">int</span></span>  <br/> |<span data-ttu-id="9a96e-123">Nombre de tentatives d’actualisation de l’entité de sécurité AD DS qui ont eu lieu jusqu'à présent.</span><span class="sxs-lookup"><span data-stu-id="9a96e-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="9a96e-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="9a96e-124">lastTry</span></span>  <br/> |<span data-ttu-id="9a96e-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9a96e-125">datetime</span></span>  <br/> |<span data-ttu-id="9a96e-126">Horodatage de la dernière tentative d’actualisation de l’entité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="9a96e-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="9a96e-127">Peut être null si aucune actualisation n’a été tentée encore.</span><span class="sxs-lookup"><span data-stu-id="9a96e-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="9a96e-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="9a96e-128">nextTry</span></span>  <br/> |<span data-ttu-id="9a96e-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9a96e-129">datetime</span></span>  <br/> |<span data-ttu-id="9a96e-130">Horodatage de la prochaine actualisation planifiée.</span><span class="sxs-lookup"><span data-stu-id="9a96e-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="9a96e-131">Peut être null si aucune actualisation a été planifiée.</span><span class="sxs-lookup"><span data-stu-id="9a96e-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="9a96e-132">**Clés**</span><span class="sxs-lookup"><span data-stu-id="9a96e-132">**Keys**</span></span>

|<span data-ttu-id="9a96e-133">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9a96e-133">**Column**</span></span>|<span data-ttu-id="9a96e-134">**Description**</span><span class="sxs-lookup"><span data-stu-id="9a96e-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a96e-135">prinID</span><span class="sxs-lookup"><span data-stu-id="9a96e-135">prinID</span></span>  <br/> |<span data-ttu-id="9a96e-136">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="9a96e-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9a96e-137">prinID</span><span class="sxs-lookup"><span data-stu-id="9a96e-137">prinID</span></span>  <br/> |<span data-ttu-id="9a96e-138">Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="9a96e-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

