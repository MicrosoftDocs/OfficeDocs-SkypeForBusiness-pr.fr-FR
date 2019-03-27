---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des Services de domaine Active Directory.
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889606"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="a0b25-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="a0b25-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="a0b25-104">tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a0b25-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="a0b25-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="a0b25-105">**Columns**</span></span>

|<span data-ttu-id="a0b25-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a0b25-106">**Column**</span></span>|<span data-ttu-id="a0b25-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="a0b25-107">**Type**</span></span>|<span data-ttu-id="a0b25-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a0b25-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0b25-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a0b25-109">prinID</span></span>  <br/> |<span data-ttu-id="a0b25-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="a0b25-110">int, not null</span></span>  <br/> |<span data-ttu-id="a0b25-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="a0b25-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a0b25-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="a0b25-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="a0b25-113">bit, non null</span><span class="sxs-lookup"><span data-stu-id="a0b25-113">bit, not null</span></span>  <br/> |<span data-ttu-id="a0b25-114">True si le principal affiliations doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="a0b25-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="a0b25-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="a0b25-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="a0b25-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="a0b25-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a0b25-117">True si les principaux attributs doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="a0b25-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="a0b25-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="a0b25-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="a0b25-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="a0b25-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a0b25-120">True si le principal a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="a0b25-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="a0b25-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="a0b25-121">tryCount</span></span>  <br/> |<span data-ttu-id="a0b25-122">int</span><span class="sxs-lookup"><span data-stu-id="a0b25-122">int</span></span>  <br/> |<span data-ttu-id="a0b25-123">Nombre de tentatives d’actualisation de l’entité de sécurité de domaine Active Directory ayant eu lieu jusqu'à présent.</span><span class="sxs-lookup"><span data-stu-id="a0b25-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="a0b25-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="a0b25-124">lastTry</span></span>  <br/> |<span data-ttu-id="a0b25-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a0b25-125">datetime</span></span>  <br/> |<span data-ttu-id="a0b25-126">Horodatage de la dernière tentative d’actualisation.</span><span class="sxs-lookup"><span data-stu-id="a0b25-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="a0b25-127">Peut être null si aucune actualisation n’a été tentée encore.</span><span class="sxs-lookup"><span data-stu-id="a0b25-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="a0b25-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="a0b25-128">nextTry</span></span>  <br/> |<span data-ttu-id="a0b25-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a0b25-129">datetime</span></span>  <br/> |<span data-ttu-id="a0b25-130">Horodatage de l’actualisation planifiée suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b25-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="a0b25-131">Peut être une valeur null si aucune actualisation a été planifiée.</span><span class="sxs-lookup"><span data-stu-id="a0b25-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="a0b25-132">**Clés**</span><span class="sxs-lookup"><span data-stu-id="a0b25-132">**Keys**</span></span>

|<span data-ttu-id="a0b25-133">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a0b25-133">**Column**</span></span>|<span data-ttu-id="a0b25-134">**Description**</span><span class="sxs-lookup"><span data-stu-id="a0b25-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a0b25-135">prinID</span><span class="sxs-lookup"><span data-stu-id="a0b25-135">prinID</span></span>  <br/> |<span data-ttu-id="a0b25-136">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a0b25-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a0b25-137">prinID</span><span class="sxs-lookup"><span data-stu-id="a0b25-137">prinID</span></span>  <br/> |<span data-ttu-id="a0b25-138">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="a0b25-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

