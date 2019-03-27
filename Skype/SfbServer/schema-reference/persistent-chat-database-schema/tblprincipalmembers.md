---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient les appartenances des principaux.
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874251"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="78995-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="78995-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="78995-104">tblPrincipalMembers contient les appartenances des principaux.</span><span class="sxs-lookup"><span data-stu-id="78995-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="78995-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="78995-105">**Columns**</span></span>

|<span data-ttu-id="78995-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="78995-106">**Column**</span></span>|<span data-ttu-id="78995-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="78995-107">**Type**</span></span>|<span data-ttu-id="78995-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="78995-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78995-109">prinID</span><span class="sxs-lookup"><span data-stu-id="78995-109">prinID</span></span>  <br/> |<span data-ttu-id="78995-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="78995-110">int, not null</span></span>  <br/> |<span data-ttu-id="78995-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="78995-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="78995-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="78995-112">memberADPath</span></span>  <br/> |<span data-ttu-id="78995-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="78995-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="78995-114">Nom unique de membre.</span><span class="sxs-lookup"><span data-stu-id="78995-114">Distinguished name of a member.</span></span> <span data-ttu-id="78995-115">Un membre n’a pas à une entité (dans la table tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="78995-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="78995-116">**Clés**</span><span class="sxs-lookup"><span data-stu-id="78995-116">**Keys**</span></span>

|<span data-ttu-id="78995-117">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="78995-117">**Column**</span></span>|<span data-ttu-id="78995-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="78995-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78995-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="78995-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="78995-120">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="78995-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="78995-121">prinID</span><span class="sxs-lookup"><span data-stu-id="78995-121">prinID</span></span>  <br/> |<span data-ttu-id="78995-122">Clé étrangère avec recherche dans tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="78995-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

