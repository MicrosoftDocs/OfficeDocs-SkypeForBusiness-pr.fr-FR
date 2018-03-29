---
title: tblPrincipalMemberDifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient le groupe d’appartenance modifications (ajout et suppression de membres) qui n’ont pas encore été traitées par les étapes ultérieures de Sync Services de domaine Active Directory.
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="dd9d4-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="dd9d4-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="dd9d4-104">tblPrincipalMemberDifference contient le groupe d’appartenance modifications (ajout et suppression de membres) qui n’ont pas encore été traitées par les étapes ultérieures de Sync Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dd9d4-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="dd9d4-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="dd9d4-105">**Columns**</span></span>

|<span data-ttu-id="dd9d4-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="dd9d4-106">**Column**</span></span>|<span data-ttu-id="dd9d4-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="dd9d4-107">**Type**</span></span>|<span data-ttu-id="dd9d4-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="dd9d4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dd9d4-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="dd9d4-109">prinGuid</span></span>  <br/> |<span data-ttu-id="dd9d4-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="dd9d4-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="dd9d4-111">GUID principal du groupe qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="dd9d4-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="dd9d4-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="dd9d4-112">memberADPath</span></span>  <br/> |<span data-ttu-id="dd9d4-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dd9d4-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="dd9d4-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="dd9d4-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="dd9d4-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="dd9d4-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="dd9d4-116">bits, non null</span><span class="sxs-lookup"><span data-stu-id="dd9d4-116">bit, not null</span></span>  <br/> |<span data-ttu-id="dd9d4-117">False si le membre a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="dd9d4-117">False if the member was added.</span></span> <span data-ttu-id="dd9d4-118">True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="dd9d4-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="dd9d4-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="dd9d4-119">**Key**</span></span>

|<span data-ttu-id="dd9d4-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="dd9d4-120">**Column**</span></span>|<span data-ttu-id="dd9d4-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="dd9d4-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd9d4-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="dd9d4-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="dd9d4-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="dd9d4-123">Primary key.</span></span>  <br/> |
   

