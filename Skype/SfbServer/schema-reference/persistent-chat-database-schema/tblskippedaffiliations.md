---
title: tblSkippedAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lue (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="39240-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="39240-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="39240-104">tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lue (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).</span><span class="sxs-lookup"><span data-stu-id="39240-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="39240-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="39240-105">**Columns**</span></span>

|<span data-ttu-id="39240-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="39240-106">**Column**</span></span>|<span data-ttu-id="39240-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="39240-107">**Type**</span></span>|<span data-ttu-id="39240-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="39240-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39240-109">prinID</span><span class="sxs-lookup"><span data-stu-id="39240-109">prinID</span></span>  <br/> |<span data-ttu-id="39240-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="39240-110">int, not null</span></span>  <br/> |<span data-ttu-id="39240-111">ID d’entité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="39240-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="39240-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="39240-112">affDescription</span></span>  <br/> |<span data-ttu-id="39240-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="39240-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="39240-114">Chaîne identifiant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="39240-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="39240-115">Le format est : guid : uri de _{0}_ : _{1}_> id : _{2}_</span><span class="sxs-lookup"><span data-stu-id="39240-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="39240-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="39240-116">updatedBy</span></span>  <br/> |<span data-ttu-id="39240-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="39240-117">int, not null</span></span>  <br/> |<span data-ttu-id="39240-118">ID de l’entité de sécurité mise à jour de cette ligne.</span><span class="sxs-lookup"><span data-stu-id="39240-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="39240-119">Il est toujours 1 (utilisateur du système) car la synchronisation Active Directory est la seule source pour ces écritures.</span><span class="sxs-lookup"><span data-stu-id="39240-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="39240-120">**Clés**</span><span class="sxs-lookup"><span data-stu-id="39240-120">**Keys**</span></span>

|<span data-ttu-id="39240-121">**Colonne (s)**</span><span class="sxs-lookup"><span data-stu-id="39240-121">**Column(s)**</span></span>|<span data-ttu-id="39240-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="39240-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39240-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="39240-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="39240-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="39240-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="39240-125">prinID</span><span class="sxs-lookup"><span data-stu-id="39240-125">prinID</span></span>  <br/> |<span data-ttu-id="39240-126">Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="39240-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

