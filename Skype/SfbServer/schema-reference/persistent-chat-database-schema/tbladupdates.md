---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications de Services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory.
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a><span data-ttu-id="5382d-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="5382d-103">tblADUpdates</span></span>
 
<span data-ttu-id="5382d-104">tblADUpdates contient les modifications de Services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5382d-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="5382d-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="5382d-105">**Columns**</span></span>

|<span data-ttu-id="5382d-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5382d-106">**Column**</span></span>|<span data-ttu-id="5382d-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="5382d-107">**Type**</span></span>|<span data-ttu-id="5382d-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="5382d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5382d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="5382d-109">prinGuid</span></span>  <br/> |<span data-ttu-id="5382d-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="5382d-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="5382d-111">Entité de GUID de l’objet modifié.</span><span class="sxs-lookup"><span data-stu-id="5382d-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="5382d-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="5382d-112">prinADPath</span></span>  <br/> |<span data-ttu-id="5382d-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="5382d-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="5382d-114">Nom unique de l’objet.</span><span class="sxs-lookup"><span data-stu-id="5382d-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="5382d-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="5382d-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="5382d-116">bits, non null</span><span class="sxs-lookup"><span data-stu-id="5382d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5382d-117">True si au moins un attribut de l’objet modifié.</span><span class="sxs-lookup"><span data-stu-id="5382d-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="5382d-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="5382d-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="5382d-119">bits, non null</span><span class="sxs-lookup"><span data-stu-id="5382d-119">bit, not null</span></span>  <br/> |<span data-ttu-id="5382d-120">True si l’appartenance est modifiée.</span><span class="sxs-lookup"><span data-stu-id="5382d-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="5382d-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="5382d-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="5382d-122">bits, non null</span><span class="sxs-lookup"><span data-stu-id="5382d-122">bit, not null</span></span>  <br/> |<span data-ttu-id="5382d-123">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="5382d-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="5382d-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="5382d-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="5382d-125">bits, non null</span><span class="sxs-lookup"><span data-stu-id="5382d-125">bit, not null</span></span>  <br/> |<span data-ttu-id="5382d-126">True si l’objet a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="5382d-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="5382d-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="5382d-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="5382d-128">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="5382d-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="5382d-129">Date et heure du lorsque la ligne a été insérée.</span><span class="sxs-lookup"><span data-stu-id="5382d-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

