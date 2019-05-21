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
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient des appartenances principales.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295285"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="524c9-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="524c9-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="524c9-104">tblPrincipalMembers contient des appartenances principales.</span><span class="sxs-lookup"><span data-stu-id="524c9-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="524c9-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="524c9-105">**Columns**</span></span>

|<span data-ttu-id="524c9-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="524c9-106">**Column**</span></span>|<span data-ttu-id="524c9-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="524c9-107">**Type**</span></span>|<span data-ttu-id="524c9-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="524c9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="524c9-109">prinID</span><span class="sxs-lookup"><span data-stu-id="524c9-109">prinID</span></span>  <br/> |<span data-ttu-id="524c9-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="524c9-110">int, not null</span></span>  <br/> |<span data-ttu-id="524c9-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="524c9-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="524c9-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="524c9-112">memberADPath</span></span>  <br/> |<span data-ttu-id="524c9-113">nvarchar (384), pas null</span><span class="sxs-lookup"><span data-stu-id="524c9-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="524c9-114">Nom unique d’un membre.</span><span class="sxs-lookup"><span data-stu-id="524c9-114">Distinguished name of a member.</span></span> <span data-ttu-id="524c9-115">Un membre ne doit pas nécessairement être principal (dans la table tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="524c9-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="524c9-116">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="524c9-116">**Keys**</span></span>

|<span data-ttu-id="524c9-117">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="524c9-117">**Column**</span></span>|<span data-ttu-id="524c9-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="524c9-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="524c9-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="524c9-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="524c9-120">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="524c9-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="524c9-121">prinID</span><span class="sxs-lookup"><span data-stu-id="524c9-121">prinID</span></span>  <br/> |<span data-ttu-id="524c9-122">Clé étrangère avec recherche dans tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="524c9-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

