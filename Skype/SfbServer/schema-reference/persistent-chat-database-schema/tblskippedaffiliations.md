---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison d’erreurs d’accès aux services de domaine Active Directory).
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831424"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="39096-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="39096-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="39096-104">tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison d’erreurs d’accès aux services de domaine Active Directory).</span><span class="sxs-lookup"><span data-stu-id="39096-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="39096-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="39096-105">**Columns**</span></span>

|<span data-ttu-id="39096-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="39096-106">**Column**</span></span>|<span data-ttu-id="39096-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="39096-107">**Type**</span></span>|<span data-ttu-id="39096-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="39096-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39096-109">prinID</span><span class="sxs-lookup"><span data-stu-id="39096-109">prinID</span></span>  <br/> |<span data-ttu-id="39096-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="39096-110">int, not null</span></span>  <br/> |<span data-ttu-id="39096-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="39096-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="39096-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="39096-112">affDescription</span></span>  <br/> |<span data-ttu-id="39096-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="39096-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="39096-114">Chaîne identifiant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="39096-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="39096-115">Le format est : guid:  _{0}_ uri : _{1}_> id :  _{2}_</span><span class="sxs-lookup"><span data-stu-id="39096-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="39096-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="39096-116">updatedBy</span></span>  <br/> |<span data-ttu-id="39096-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="39096-117">int, not null</span></span>  <br/> |<span data-ttu-id="39096-p101">ID du principal qui a mis à jour cette ligne. Il s’agit toujours d’1 (utilisateur système) car la synchronisation Active Directory est la seule source pour ces entrées.</span><span class="sxs-lookup"><span data-stu-id="39096-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="39096-120">**Keys**</span><span class="sxs-lookup"><span data-stu-id="39096-120">**Keys**</span></span>

|<span data-ttu-id="39096-121">**Colonne(s)**</span><span class="sxs-lookup"><span data-stu-id="39096-121">**Column(s)**</span></span>|<span data-ttu-id="39096-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="39096-122">**Description**</span></span>|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |<span data-ttu-id="39096-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="39096-123">Primary key.</span></span>  <br/> |
|<span data-ttu-id="39096-124">prinID</span><span class="sxs-lookup"><span data-stu-id="39096-124">prinID</span></span>  <br/> |<span data-ttu-id="39096-125">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="39096-125">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

