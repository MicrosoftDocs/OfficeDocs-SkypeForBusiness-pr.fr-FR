---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient des membres principaux.
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="0eec7-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="0eec7-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="0eec7-104">tblPrincipalMembers contient des membres principaux.</span><span class="sxs-lookup"><span data-stu-id="0eec7-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="0eec7-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="0eec7-105">**Columns**</span></span>

|<span data-ttu-id="0eec7-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0eec7-106">**Column**</span></span>|<span data-ttu-id="0eec7-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="0eec7-107">**Type**</span></span>|<span data-ttu-id="0eec7-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="0eec7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0eec7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="0eec7-109">prinID</span></span>  <br/> |<span data-ttu-id="0eec7-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="0eec7-110">int, not null</span></span>  <br/> |<span data-ttu-id="0eec7-111">ID d’entité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0eec7-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="0eec7-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="0eec7-112">memberADPath</span></span>  <br/> |<span data-ttu-id="0eec7-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="0eec7-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="0eec7-114">Nom unique d’un membre.</span><span class="sxs-lookup"><span data-stu-id="0eec7-114">Distinguished name of a member.</span></span> <span data-ttu-id="0eec7-115">Un membre n’a pas à être une entité (dans la table de tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="0eec7-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="0eec7-116">**Clés**</span><span class="sxs-lookup"><span data-stu-id="0eec7-116">**Keys**</span></span>

|<span data-ttu-id="0eec7-117">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0eec7-117">**Column**</span></span>|<span data-ttu-id="0eec7-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="0eec7-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0eec7-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="0eec7-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="0eec7-120">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0eec7-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0eec7-121">prinID</span><span class="sxs-lookup"><span data-stu-id="0eec7-121">prinID</span></span>  <br/> |<span data-ttu-id="0eec7-122">Clé étrangère avec la recherche dans tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="0eec7-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

