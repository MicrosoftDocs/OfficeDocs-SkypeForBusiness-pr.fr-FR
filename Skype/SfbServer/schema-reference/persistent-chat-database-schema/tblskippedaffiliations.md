---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lues (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).
ms.openlocfilehash: 85fe836e75409a0a6aae22583358f9f88dc8d4e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924940"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="e3a5c-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="e3a5c-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="e3a5c-104">tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lues (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).</span><span class="sxs-lookup"><span data-stu-id="e3a5c-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="e3a5c-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="e3a5c-105">**Columns**</span></span>

|<span data-ttu-id="e3a5c-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e3a5c-106">**Column**</span></span>|<span data-ttu-id="e3a5c-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="e3a5c-107">**Type**</span></span>|<span data-ttu-id="e3a5c-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e3a5c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3a5c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e3a5c-109">prinID</span></span>  <br/> |<span data-ttu-id="e3a5c-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="e3a5c-110">int, not null</span></span>  <br/> |<span data-ttu-id="e3a5c-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e3a5c-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="e3a5c-112">affDescription</span></span>  <br/> |<span data-ttu-id="e3a5c-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="e3a5c-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e3a5c-114">Chaîne identifiant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="e3a5c-115">Le format est : guid : _{0}_ uri : _{1}_> id :_{2}_</span><span class="sxs-lookup"><span data-stu-id="e3a5c-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="e3a5c-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e3a5c-116">updatedBy</span></span>  <br/> |<span data-ttu-id="e3a5c-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="e3a5c-117">int, not null</span></span>  <br/> |<span data-ttu-id="e3a5c-118">ID du principal ayant mis à jour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="e3a5c-119">Il est toujours 1 (utilisateur système), car la synchronisation Active Directory est la seule source pour ces entrées.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="e3a5c-120">**Clés**</span><span class="sxs-lookup"><span data-stu-id="e3a5c-120">**Keys**</span></span>

|<span data-ttu-id="e3a5c-121">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="e3a5c-121">**Column(s)**</span></span>|<span data-ttu-id="e3a5c-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="e3a5c-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3a5c-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="e3a5c-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="e3a5c-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e3a5c-125">prinID</span><span class="sxs-lookup"><span data-stu-id="e3a5c-125">prinID</span></span>  <br/> |<span data-ttu-id="e3a5c-126">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

