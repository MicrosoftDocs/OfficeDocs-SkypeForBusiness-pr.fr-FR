---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisé à partir des services de domaine Active Directory.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831544"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="5b32c-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="5b32c-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="5b32c-104">tblPrincipalMeta contient les principaux qui doivent être actualisé à partir des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b32c-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="5b32c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="5b32c-105">**Columns**</span></span>

|<span data-ttu-id="5b32c-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5b32c-106">**Column**</span></span>|<span data-ttu-id="5b32c-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="5b32c-107">**Type**</span></span>|<span data-ttu-id="5b32c-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="5b32c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5b32c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5b32c-109">prinID</span></span>  <br/> |<span data-ttu-id="5b32c-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="5b32c-110">int, not null</span></span>  <br/> |<span data-ttu-id="5b32c-111">ID de principal.</span><span class="sxs-lookup"><span data-stu-id="5b32c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5b32c-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="5b32c-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="5b32c-113">bit, non null</span><span class="sxs-lookup"><span data-stu-id="5b32c-113">bit, not null</span></span>  <br/> |<span data-ttu-id="5b32c-114">True si les affiliations de principaux doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="5b32c-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="5b32c-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="5b32c-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="5b32c-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="5b32c-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5b32c-117">True si les attributs de principaux doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="5b32c-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="5b32c-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="5b32c-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="5b32c-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="5b32c-119">bit, not null</span></span>  <br/> |<span data-ttu-id="5b32c-120">True si le principal doit être supprimé.</span><span class="sxs-lookup"><span data-stu-id="5b32c-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="5b32c-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="5b32c-121">tryCount</span></span>  <br/> |<span data-ttu-id="5b32c-122">int</span><span class="sxs-lookup"><span data-stu-id="5b32c-122">int</span></span>  <br/> |<span data-ttu-id="5b32c-123">Nombre de tentatives d’actualisation à partir des services AD DS ayant eu lieu jusqu’à maintenant.</span><span class="sxs-lookup"><span data-stu-id="5b32c-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="5b32c-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="5b32c-124">lastTry</span></span>  <br/> |<span data-ttu-id="5b32c-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5b32c-125">datetime</span></span>  <br/> |<span data-ttu-id="5b32c-p101">Horodatage de la dernière tentative d’actualisation du principal. Peut être null si aucune actualisation n’a encore été tentée.</span><span class="sxs-lookup"><span data-stu-id="5b32c-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="5b32c-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="5b32c-128">nextTry</span></span>  <br/> |<span data-ttu-id="5b32c-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5b32c-129">datetime</span></span>  <br/> |<span data-ttu-id="5b32c-p102">Horodatage de la prochaine actualisation planifiée. Peut être null si aucune actualisation supplémentaire n’a été planifiée.</span><span class="sxs-lookup"><span data-stu-id="5b32c-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="5b32c-132">**Keys**</span><span class="sxs-lookup"><span data-stu-id="5b32c-132">**Keys**</span></span>

|<span data-ttu-id="5b32c-133">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5b32c-133">**Column**</span></span>|<span data-ttu-id="5b32c-134">**Description**</span><span class="sxs-lookup"><span data-stu-id="5b32c-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b32c-135">prinID</span><span class="sxs-lookup"><span data-stu-id="5b32c-135">prinID</span></span>  <br/> |<span data-ttu-id="5b32c-136">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5b32c-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5b32c-137">prinID</span><span class="sxs-lookup"><span data-stu-id="5b32c-137">prinID</span></span>  <br/> |<span data-ttu-id="5b32c-138">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="5b32c-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

