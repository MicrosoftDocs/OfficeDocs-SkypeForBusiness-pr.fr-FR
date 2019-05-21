---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295558"
---
# <a name="tbladupdates"></a><span data-ttu-id="a46c8-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="a46c8-103">tblADUpdates</span></span>
 
<span data-ttu-id="a46c8-104">tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a46c8-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="a46c8-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="a46c8-105">**Columns**</span></span>

|<span data-ttu-id="a46c8-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a46c8-106">**Column**</span></span>|<span data-ttu-id="a46c8-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="a46c8-107">**Type**</span></span>|<span data-ttu-id="a46c8-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a46c8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a46c8-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a46c8-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a46c8-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="a46c8-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a46c8-111">GUID principal de l’objet qui a changé.</span><span class="sxs-lookup"><span data-stu-id="a46c8-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="a46c8-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="a46c8-112">prinADPath</span></span>  <br/> |<span data-ttu-id="a46c8-113">nvarchar (384), pas null</span><span class="sxs-lookup"><span data-stu-id="a46c8-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="a46c8-114">Nom unique de l’objet.</span><span class="sxs-lookup"><span data-stu-id="a46c8-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="a46c8-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="a46c8-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="a46c8-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="a46c8-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a46c8-117">Vrai si au moins un attribut de l’objet a changé.</span><span class="sxs-lookup"><span data-stu-id="a46c8-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="a46c8-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="a46c8-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="a46c8-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="a46c8-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a46c8-120">True si l’appartenance a changé.</span><span class="sxs-lookup"><span data-stu-id="a46c8-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="a46c8-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="a46c8-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="a46c8-122">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="a46c8-122">bit, not null</span></span>  <br/> |<span data-ttu-id="a46c8-123">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="a46c8-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="a46c8-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="a46c8-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="a46c8-125">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="a46c8-125">bit, not null</span></span>  <br/> |<span data-ttu-id="a46c8-126">True si l’objet a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="a46c8-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="a46c8-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a46c8-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="a46c8-128">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="a46c8-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="a46c8-129">Horodatage de la date d’insertion de la ligne.</span><span class="sxs-lookup"><span data-stu-id="a46c8-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

