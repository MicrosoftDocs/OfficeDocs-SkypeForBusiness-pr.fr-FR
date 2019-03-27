---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lues (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874786"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="15d13-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="15d13-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="15d13-104">tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lues (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).</span><span class="sxs-lookup"><span data-stu-id="15d13-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="15d13-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="15d13-105">**Columns**</span></span>

|<span data-ttu-id="15d13-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="15d13-106">**Column**</span></span>|<span data-ttu-id="15d13-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="15d13-107">**Type**</span></span>|<span data-ttu-id="15d13-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="15d13-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15d13-109">prinID</span><span class="sxs-lookup"><span data-stu-id="15d13-109">prinID</span></span>  <br/> |<span data-ttu-id="15d13-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="15d13-110">int, not null</span></span>  <br/> |<span data-ttu-id="15d13-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="15d13-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="15d13-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="15d13-112">affDescription</span></span>  <br/> |<span data-ttu-id="15d13-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="15d13-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="15d13-114">Chaîne identifiant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="15d13-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="15d13-115">Le format est : guid : _{0}_ uri : _{1}_> id :_{2}_</span><span class="sxs-lookup"><span data-stu-id="15d13-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="15d13-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="15d13-116">updatedBy</span></span>  <br/> |<span data-ttu-id="15d13-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="15d13-117">int, not null</span></span>  <br/> |<span data-ttu-id="15d13-118">ID du principal ayant mis à jour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="15d13-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="15d13-119">Il est toujours 1 (utilisateur système), car la synchronisation Active Directory est la seule source pour ces entrées.</span><span class="sxs-lookup"><span data-stu-id="15d13-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="15d13-120">**Clés**</span><span class="sxs-lookup"><span data-stu-id="15d13-120">**Keys**</span></span>

|<span data-ttu-id="15d13-121">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="15d13-121">**Column(s)**</span></span>|<span data-ttu-id="15d13-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="15d13-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="15d13-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="15d13-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="15d13-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="15d13-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="15d13-125">prinID</span><span class="sxs-lookup"><span data-stu-id="15d13-125">prinID</span></span>  <br/> |<span data-ttu-id="15d13-126">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="15d13-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

