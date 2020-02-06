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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory (AD FS).
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813572"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="b95aa-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="b95aa-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="b95aa-104">tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="b95aa-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="b95aa-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="b95aa-105">**Columns**</span></span>

|<span data-ttu-id="b95aa-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b95aa-106">**Column**</span></span>|<span data-ttu-id="b95aa-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="b95aa-107">**Type**</span></span>|<span data-ttu-id="b95aa-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="b95aa-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b95aa-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b95aa-109">prinID</span></span>  <br/> |<span data-ttu-id="b95aa-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="b95aa-110">int, not null</span></span>  <br/> |<span data-ttu-id="b95aa-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="b95aa-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b95aa-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="b95aa-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="b95aa-113">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="b95aa-113">bit, not null</span></span>  <br/> |<span data-ttu-id="b95aa-114">True si les affiliations principales doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="b95aa-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="b95aa-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="b95aa-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="b95aa-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="b95aa-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b95aa-117">True si les attributs principaux doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="b95aa-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="b95aa-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="b95aa-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="b95aa-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="b95aa-119">bit, not null</span></span>  <br/> |<span data-ttu-id="b95aa-120">True si l’objet principal a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="b95aa-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="b95aa-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="b95aa-121">tryCount</span></span>  <br/> |<span data-ttu-id="b95aa-122">int</span><span class="sxs-lookup"><span data-stu-id="b95aa-122">int</span></span>  <br/> |<span data-ttu-id="b95aa-123">Nombre de tentatives d’actualisation du principal à partir d’AD DS qui est déjà en passe.</span><span class="sxs-lookup"><span data-stu-id="b95aa-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="b95aa-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="b95aa-124">lastTry</span></span>  <br/> |<span data-ttu-id="b95aa-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b95aa-125">datetime</span></span>  <br/> |<span data-ttu-id="b95aa-126">Horodatage de la dernière tentative d’actualisation du principal.</span><span class="sxs-lookup"><span data-stu-id="b95aa-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="b95aa-127">Il peut s’agir de la valeur null s’il n’y a pas encore de tentative d’actualisation.</span><span class="sxs-lookup"><span data-stu-id="b95aa-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="b95aa-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="b95aa-128">nextTry</span></span>  <br/> |<span data-ttu-id="b95aa-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b95aa-129">datetime</span></span>  <br/> |<span data-ttu-id="b95aa-130">Horodatage de la prochaine actualisation planifiée.</span><span class="sxs-lookup"><span data-stu-id="b95aa-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="b95aa-131">Peut être null s’il n’y a pas de planification ultérieure.</span><span class="sxs-lookup"><span data-stu-id="b95aa-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="b95aa-132">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="b95aa-132">**Keys**</span></span>

|<span data-ttu-id="b95aa-133">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b95aa-133">**Column**</span></span>|<span data-ttu-id="b95aa-134">**Description**</span><span class="sxs-lookup"><span data-stu-id="b95aa-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b95aa-135">prinID</span><span class="sxs-lookup"><span data-stu-id="b95aa-135">prinID</span></span>  <br/> |<span data-ttu-id="b95aa-136">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="b95aa-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b95aa-137">prinID</span><span class="sxs-lookup"><span data-stu-id="b95aa-137">prinID</span></span>  <br/> |<span data-ttu-id="b95aa-138">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="b95aa-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

