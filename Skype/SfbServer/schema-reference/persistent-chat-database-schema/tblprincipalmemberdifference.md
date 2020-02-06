---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient les modifications d’appartenance au groupe (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation des services de domaine Active Directory.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814072"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="5f6bc-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="5f6bc-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="5f6bc-104">tblPrincipalMemberDifference contient les modifications d’appartenance au groupe (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="5f6bc-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="5f6bc-105">**Columns**</span></span>

|<span data-ttu-id="5f6bc-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5f6bc-106">**Column**</span></span>|<span data-ttu-id="5f6bc-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="5f6bc-107">**Type**</span></span>|<span data-ttu-id="5f6bc-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="5f6bc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f6bc-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="5f6bc-109">prinGuid</span></span>  <br/> |<span data-ttu-id="5f6bc-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="5f6bc-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="5f6bc-111">GUID principal du groupe qui a changé.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="5f6bc-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="5f6bc-112">memberADPath</span></span>  <br/> |<span data-ttu-id="5f6bc-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f6bc-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="5f6bc-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="5f6bc-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="5f6bc-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="5f6bc-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="5f6bc-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5f6bc-117">False si le membre a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-117">False if the member was added.</span></span> <span data-ttu-id="5f6bc-118">True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="5f6bc-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="5f6bc-119">**Key**</span></span>

|<span data-ttu-id="5f6bc-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5f6bc-120">**Column**</span></span>|<span data-ttu-id="5f6bc-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="5f6bc-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f6bc-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="5f6bc-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="5f6bc-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5f6bc-123">Primary key.</span></span>  <br/> |
   

