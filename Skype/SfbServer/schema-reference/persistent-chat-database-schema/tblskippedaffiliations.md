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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison des erreurs d’accès aux services de domaine Active Directory).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812012"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="13525-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="13525-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="13525-104">tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison des erreurs d’accès aux services de domaine Active Directory).</span><span class="sxs-lookup"><span data-stu-id="13525-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="13525-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="13525-105">**Columns**</span></span>

|<span data-ttu-id="13525-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="13525-106">**Column**</span></span>|<span data-ttu-id="13525-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="13525-107">**Type**</span></span>|<span data-ttu-id="13525-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="13525-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13525-109">prinID</span><span class="sxs-lookup"><span data-stu-id="13525-109">prinID</span></span>  <br/> |<span data-ttu-id="13525-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="13525-110">int, not null</span></span>  <br/> |<span data-ttu-id="13525-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="13525-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="13525-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="13525-112">affDescription</span></span>  <br/> |<span data-ttu-id="13525-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="13525-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="13525-114">Chaîne identifiant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="13525-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="13525-115">Le format est : GUID : _{0}_ uri : _{1}_> ID :_{2}_</span><span class="sxs-lookup"><span data-stu-id="13525-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="13525-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="13525-116">updatedBy</span></span>  <br/> |<span data-ttu-id="13525-117">ent, non null</span><span class="sxs-lookup"><span data-stu-id="13525-117">int, not null</span></span>  <br/> |<span data-ttu-id="13525-118">ID de l’objet principal qui a mis à jour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="13525-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="13525-119">Il est toujours 1 (utilisateur système), car la synchronisation Active Directory est la seule source de ces entrées.</span><span class="sxs-lookup"><span data-stu-id="13525-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="13525-120">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="13525-120">**Keys**</span></span>

|<span data-ttu-id="13525-121">**Colonne (s)**</span><span class="sxs-lookup"><span data-stu-id="13525-121">**Column(s)**</span></span>|<span data-ttu-id="13525-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="13525-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13525-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="13525-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="13525-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="13525-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="13525-125">prinID</span><span class="sxs-lookup"><span data-stu-id="13525-125">prinID</span></span>  <br/> |<span data-ttu-id="13525-126">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="13525-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

