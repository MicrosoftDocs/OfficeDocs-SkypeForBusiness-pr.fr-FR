---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient des appartenances principales.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813942"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="fca2a-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="fca2a-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="fca2a-104">tblPrincipalMembers contient des appartenances principales.</span><span class="sxs-lookup"><span data-stu-id="fca2a-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="fca2a-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="fca2a-105">**Columns**</span></span>

|<span data-ttu-id="fca2a-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fca2a-106">**Column**</span></span>|<span data-ttu-id="fca2a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="fca2a-107">**Type**</span></span>|<span data-ttu-id="fca2a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="fca2a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fca2a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="fca2a-109">prinID</span></span>  <br/> |<span data-ttu-id="fca2a-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="fca2a-110">int, not null</span></span>  <br/> |<span data-ttu-id="fca2a-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="fca2a-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fca2a-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="fca2a-112">memberADPath</span></span>  <br/> |<span data-ttu-id="fca2a-113">nvarchar (384), pas null</span><span class="sxs-lookup"><span data-stu-id="fca2a-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="fca2a-114">Nom unique d’un membre.</span><span class="sxs-lookup"><span data-stu-id="fca2a-114">Distinguished name of a member.</span></span> <span data-ttu-id="fca2a-115">Un membre ne doit pas nécessairement être principal (dans la table tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="fca2a-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="fca2a-116">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="fca2a-116">**Keys**</span></span>

|<span data-ttu-id="fca2a-117">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fca2a-117">**Column**</span></span>|<span data-ttu-id="fca2a-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="fca2a-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fca2a-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="fca2a-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="fca2a-120">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="fca2a-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fca2a-121">prinID</span><span class="sxs-lookup"><span data-stu-id="fca2a-121">prinID</span></span>  <br/> |<span data-ttu-id="fca2a-122">Clé étrangère avec recherche dans tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="fca2a-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

