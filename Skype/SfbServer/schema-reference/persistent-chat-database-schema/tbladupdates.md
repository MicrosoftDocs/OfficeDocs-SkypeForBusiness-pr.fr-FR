---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications de Services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory.
ms.openlocfilehash: 4ed1abe2d5926c8b34ddccb28133ecc34ddaa03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929860"
---
# <a name="tbladupdates"></a><span data-ttu-id="54e36-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="54e36-103">tblADUpdates</span></span>
 
<span data-ttu-id="54e36-104">tblADUpdates contient les modifications de Services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="54e36-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="54e36-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="54e36-105">**Columns**</span></span>

|<span data-ttu-id="54e36-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="54e36-106">**Column**</span></span>|<span data-ttu-id="54e36-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="54e36-107">**Type**</span></span>|<span data-ttu-id="54e36-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="54e36-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54e36-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="54e36-109">prinGuid</span></span>  <br/> |<span data-ttu-id="54e36-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="54e36-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="54e36-111">GUID principal de l’objet qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="54e36-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="54e36-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="54e36-112">prinADPath</span></span>  <br/> |<span data-ttu-id="54e36-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="54e36-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="54e36-114">Nom unique de l’objet.</span><span class="sxs-lookup"><span data-stu-id="54e36-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="54e36-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="54e36-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="54e36-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="54e36-116">bit, not null</span></span>  <br/> |<span data-ttu-id="54e36-117">True si au moins un attribut de l’objet a changé.</span><span class="sxs-lookup"><span data-stu-id="54e36-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="54e36-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="54e36-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="54e36-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="54e36-119">bit, not null</span></span>  <br/> |<span data-ttu-id="54e36-120">True si l’appartenance a changé.</span><span class="sxs-lookup"><span data-stu-id="54e36-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="54e36-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="54e36-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="54e36-122">bit, non null</span><span class="sxs-lookup"><span data-stu-id="54e36-122">bit, not null</span></span>  <br/> |<span data-ttu-id="54e36-123">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="54e36-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="54e36-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="54e36-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="54e36-125">bit, non null</span><span class="sxs-lookup"><span data-stu-id="54e36-125">bit, not null</span></span>  <br/> |<span data-ttu-id="54e36-126">True si l’objet a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="54e36-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="54e36-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="54e36-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="54e36-128">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="54e36-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="54e36-129">Horodatage de lors de l’insertion de la ligne.</span><span class="sxs-lookup"><span data-stu-id="54e36-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

