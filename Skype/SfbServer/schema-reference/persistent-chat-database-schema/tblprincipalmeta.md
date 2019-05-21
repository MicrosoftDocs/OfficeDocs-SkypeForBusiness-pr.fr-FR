---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory (AD FS).
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295257"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="00187-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="00187-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="00187-104">tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="00187-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="00187-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="00187-105">**Columns**</span></span>

|<span data-ttu-id="00187-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="00187-106">**Column**</span></span>|<span data-ttu-id="00187-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="00187-107">**Type**</span></span>|<span data-ttu-id="00187-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="00187-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="00187-109">prinID</span><span class="sxs-lookup"><span data-stu-id="00187-109">prinID</span></span>  <br/> |<span data-ttu-id="00187-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="00187-110">int, not null</span></span>  <br/> |<span data-ttu-id="00187-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="00187-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="00187-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="00187-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="00187-113">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="00187-113">bit, not null</span></span>  <br/> |<span data-ttu-id="00187-114">True si les affiliations principales doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="00187-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="00187-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="00187-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="00187-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="00187-116">bit, not null</span></span>  <br/> |<span data-ttu-id="00187-117">True si les attributs principaux doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="00187-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="00187-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="00187-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="00187-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="00187-119">bit, not null</span></span>  <br/> |<span data-ttu-id="00187-120">True si l’objet principal a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="00187-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="00187-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="00187-121">tryCount</span></span>  <br/> |<span data-ttu-id="00187-122">int</span><span class="sxs-lookup"><span data-stu-id="00187-122">int</span></span>  <br/> |<span data-ttu-id="00187-123">Nombre de tentatives d’actualisation du principal à partir d’AD DS qui est déjà en passe.</span><span class="sxs-lookup"><span data-stu-id="00187-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="00187-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="00187-124">lastTry</span></span>  <br/> |<span data-ttu-id="00187-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="00187-125">datetime</span></span>  <br/> |<span data-ttu-id="00187-126">Horodatage de la dernière tentative d’actualisation du principal.</span><span class="sxs-lookup"><span data-stu-id="00187-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="00187-127">Il peut s’agir de la valeur null s’il n’y a pas encore de tentative d’actualisation.</span><span class="sxs-lookup"><span data-stu-id="00187-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="00187-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="00187-128">nextTry</span></span>  <br/> |<span data-ttu-id="00187-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="00187-129">datetime</span></span>  <br/> |<span data-ttu-id="00187-130">Horodatage de la prochaine actualisation planifiée.</span><span class="sxs-lookup"><span data-stu-id="00187-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="00187-131">Peut être null s’il n’y a pas de planification ultérieure.</span><span class="sxs-lookup"><span data-stu-id="00187-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="00187-132">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="00187-132">**Keys**</span></span>

|<span data-ttu-id="00187-133">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="00187-133">**Column**</span></span>|<span data-ttu-id="00187-134">**Description**</span><span class="sxs-lookup"><span data-stu-id="00187-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00187-135">prinID</span><span class="sxs-lookup"><span data-stu-id="00187-135">prinID</span></span>  <br/> |<span data-ttu-id="00187-136">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="00187-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="00187-137">prinID</span><span class="sxs-lookup"><span data-stu-id="00187-137">prinID</span></span>  <br/> |<span data-ttu-id="00187-138">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="00187-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

