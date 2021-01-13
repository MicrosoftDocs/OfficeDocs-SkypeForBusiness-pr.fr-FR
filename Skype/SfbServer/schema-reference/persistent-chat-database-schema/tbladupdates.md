---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes de synchronisation Active Directory ultérieures.
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821384"
---
# <a name="tbladupdates"></a><span data-ttu-id="61fd7-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="61fd7-103">tblADUpdates</span></span>
 
<span data-ttu-id="61fd7-104">tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes de synchronisation Active Directory ultérieures.</span><span class="sxs-lookup"><span data-stu-id="61fd7-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="61fd7-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="61fd7-105">**Columns**</span></span>

|<span data-ttu-id="61fd7-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="61fd7-106">**Column**</span></span>|<span data-ttu-id="61fd7-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="61fd7-107">**Type**</span></span>|<span data-ttu-id="61fd7-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="61fd7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61fd7-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="61fd7-109">prinGuid</span></span>  <br/> |<span data-ttu-id="61fd7-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="61fd7-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="61fd7-111">GUID de principal de l’objet qui a changé.</span><span class="sxs-lookup"><span data-stu-id="61fd7-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="61fd7-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="61fd7-112">prinADPath</span></span>  <br/> |<span data-ttu-id="61fd7-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="61fd7-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="61fd7-114">Nom unique de l’objet.</span><span class="sxs-lookup"><span data-stu-id="61fd7-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="61fd7-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="61fd7-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="61fd7-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="61fd7-116">bit, not null</span></span>  <br/> |<span data-ttu-id="61fd7-117">True si au moins un attribut de l’objet a changé.</span><span class="sxs-lookup"><span data-stu-id="61fd7-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="61fd7-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="61fd7-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="61fd7-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="61fd7-119">bit, not null</span></span>  <br/> |<span data-ttu-id="61fd7-120">True si l’appartenance a changé.</span><span class="sxs-lookup"><span data-stu-id="61fd7-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="61fd7-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="61fd7-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="61fd7-122">bit, non null</span><span class="sxs-lookup"><span data-stu-id="61fd7-122">bit, not null</span></span>  <br/> |<span data-ttu-id="61fd7-123">Inutilisé.</span><span class="sxs-lookup"><span data-stu-id="61fd7-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="61fd7-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="61fd7-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="61fd7-125">bit, non null</span><span class="sxs-lookup"><span data-stu-id="61fd7-125">bit, not null</span></span>  <br/> |<span data-ttu-id="61fd7-126">True si l’objet a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="61fd7-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="61fd7-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="61fd7-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="61fd7-128">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="61fd7-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="61fd7-129">Horodatage de l’insertion de la ligne.</span><span class="sxs-lookup"><span data-stu-id="61fd7-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

