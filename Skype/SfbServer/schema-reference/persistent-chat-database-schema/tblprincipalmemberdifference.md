---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient le groupe d’appartenance modifications (à la fois membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation des Services de domaine Active Directory.
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212445"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="8e72d-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="8e72d-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="8e72d-104">tblPrincipalMemberDifference contient le groupe d’appartenance modifications (à la fois membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation des Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8e72d-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="8e72d-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="8e72d-105">**Columns**</span></span>

|<span data-ttu-id="8e72d-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8e72d-106">**Column**</span></span>|<span data-ttu-id="8e72d-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="8e72d-107">**Type**</span></span>|<span data-ttu-id="8e72d-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="8e72d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8e72d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8e72d-109">prinGuid</span></span>  <br/> |<span data-ttu-id="8e72d-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="8e72d-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="8e72d-111">GUID principal du groupe qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="8e72d-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="8e72d-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="8e72d-112">memberADPath</span></span>  <br/> |<span data-ttu-id="8e72d-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e72d-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="8e72d-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="8e72d-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="8e72d-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="8e72d-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="8e72d-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="8e72d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="8e72d-117">False si le membre a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="8e72d-117">False if the member was added.</span></span> <span data-ttu-id="8e72d-118">True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="8e72d-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="8e72d-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="8e72d-119">**Key**</span></span>

|<span data-ttu-id="8e72d-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8e72d-120">**Column**</span></span>|<span data-ttu-id="8e72d-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="8e72d-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8e72d-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="8e72d-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="8e72d-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="8e72d-123">Primary key.</span></span>  <br/> |
   

