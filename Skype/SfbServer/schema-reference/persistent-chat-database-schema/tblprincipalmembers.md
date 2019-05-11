---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient les appartenances des principaux.
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904159"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="dd2df-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="dd2df-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="dd2df-104">tblPrincipalMembers contient les appartenances des principaux.</span><span class="sxs-lookup"><span data-stu-id="dd2df-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="dd2df-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="dd2df-105">**Columns**</span></span>

|<span data-ttu-id="dd2df-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="dd2df-106">**Column**</span></span>|<span data-ttu-id="dd2df-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="dd2df-107">**Type**</span></span>|<span data-ttu-id="dd2df-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="dd2df-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dd2df-109">prinID</span><span class="sxs-lookup"><span data-stu-id="dd2df-109">prinID</span></span>  <br/> |<span data-ttu-id="dd2df-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="dd2df-110">int, not null</span></span>  <br/> |<span data-ttu-id="dd2df-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="dd2df-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="dd2df-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="dd2df-112">memberADPath</span></span>  <br/> |<span data-ttu-id="dd2df-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="dd2df-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="dd2df-114">Nom unique de membre.</span><span class="sxs-lookup"><span data-stu-id="dd2df-114">Distinguished name of a member.</span></span> <span data-ttu-id="dd2df-115">Un membre n’a pas à une entité (dans la table tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="dd2df-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="dd2df-116">**Clés**</span><span class="sxs-lookup"><span data-stu-id="dd2df-116">**Keys**</span></span>

|<span data-ttu-id="dd2df-117">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="dd2df-117">**Column**</span></span>|<span data-ttu-id="dd2df-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="dd2df-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd2df-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="dd2df-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="dd2df-120">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="dd2df-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="dd2df-121">prinID</span><span class="sxs-lookup"><span data-stu-id="dd2df-121">prinID</span></span>  <br/> |<span data-ttu-id="dd2df-122">Clé étrangère avec recherche dans tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="dd2df-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

