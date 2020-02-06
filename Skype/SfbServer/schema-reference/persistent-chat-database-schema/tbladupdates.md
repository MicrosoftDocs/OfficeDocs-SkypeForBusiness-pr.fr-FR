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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814682"
---
# <a name="tbladupdates"></a><span data-ttu-id="10671-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="10671-103">tblADUpdates</span></span>
 
<span data-ttu-id="10671-104">tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10671-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="10671-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="10671-105">**Columns**</span></span>

|<span data-ttu-id="10671-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="10671-106">**Column**</span></span>|<span data-ttu-id="10671-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="10671-107">**Type**</span></span>|<span data-ttu-id="10671-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="10671-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10671-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="10671-109">prinGuid</span></span>  <br/> |<span data-ttu-id="10671-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="10671-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="10671-111">GUID principal de l’objet qui a changé.</span><span class="sxs-lookup"><span data-stu-id="10671-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="10671-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="10671-112">prinADPath</span></span>  <br/> |<span data-ttu-id="10671-113">nvarchar (384), pas null</span><span class="sxs-lookup"><span data-stu-id="10671-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="10671-114">Nom unique de l’objet.</span><span class="sxs-lookup"><span data-stu-id="10671-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="10671-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="10671-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="10671-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="10671-116">bit, not null</span></span>  <br/> |<span data-ttu-id="10671-117">Vrai si au moins un attribut de l’objet a changé.</span><span class="sxs-lookup"><span data-stu-id="10671-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="10671-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="10671-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="10671-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="10671-119">bit, not null</span></span>  <br/> |<span data-ttu-id="10671-120">True si l’appartenance a changé.</span><span class="sxs-lookup"><span data-stu-id="10671-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="10671-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="10671-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="10671-122">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="10671-122">bit, not null</span></span>  <br/> |<span data-ttu-id="10671-123">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="10671-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="10671-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="10671-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="10671-125">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="10671-125">bit, not null</span></span>  <br/> |<span data-ttu-id="10671-126">True si l’objet a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="10671-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="10671-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="10671-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="10671-128">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="10671-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="10671-129">Horodatage de la date d’insertion de la ligne.</span><span class="sxs-lookup"><span data-stu-id="10671-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

