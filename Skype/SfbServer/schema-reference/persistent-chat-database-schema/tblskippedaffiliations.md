---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison des erreurs d’accès aux services de domaine Active Directory).
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295152"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="e98ed-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="e98ed-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="e98ed-104">tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison des erreurs d’accès aux services de domaine Active Directory).</span><span class="sxs-lookup"><span data-stu-id="e98ed-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="e98ed-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="e98ed-105">**Columns**</span></span>

|<span data-ttu-id="e98ed-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e98ed-106">**Column**</span></span>|<span data-ttu-id="e98ed-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="e98ed-107">**Type**</span></span>|<span data-ttu-id="e98ed-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e98ed-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e98ed-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e98ed-109">prinID</span></span>  <br/> |<span data-ttu-id="e98ed-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="e98ed-110">int, not null</span></span>  <br/> |<span data-ttu-id="e98ed-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="e98ed-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e98ed-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="e98ed-112">affDescription</span></span>  <br/> |<span data-ttu-id="e98ed-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="e98ed-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e98ed-114">Chaîne identifiant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="e98ed-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="e98ed-115">Le format est: GUID: _{0}_ URI: _{1}_> ID:_{2}_</span><span class="sxs-lookup"><span data-stu-id="e98ed-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="e98ed-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e98ed-116">updatedBy</span></span>  <br/> |<span data-ttu-id="e98ed-117">ent, non null</span><span class="sxs-lookup"><span data-stu-id="e98ed-117">int, not null</span></span>  <br/> |<span data-ttu-id="e98ed-118">ID de l’objet principal qui a mis à jour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="e98ed-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="e98ed-119">Il est toujours 1 (utilisateur système), car la synchronisation Active Directory est la seule source de ces entrées.</span><span class="sxs-lookup"><span data-stu-id="e98ed-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="e98ed-120">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="e98ed-120">**Keys**</span></span>

|<span data-ttu-id="e98ed-121">**Colonne (s)**</span><span class="sxs-lookup"><span data-stu-id="e98ed-121">**Column(s)**</span></span>|<span data-ttu-id="e98ed-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="e98ed-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e98ed-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="e98ed-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="e98ed-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e98ed-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e98ed-125">prinID</span><span class="sxs-lookup"><span data-stu-id="e98ed-125">prinID</span></span>  <br/> |<span data-ttu-id="e98ed-126">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="e98ed-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

