---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient les appartenances principales.
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831594"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="acd68-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="acd68-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="acd68-104">tblPrincipalMembers contient les appartenances principales.</span><span class="sxs-lookup"><span data-stu-id="acd68-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="acd68-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="acd68-105">**Columns**</span></span>

|<span data-ttu-id="acd68-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="acd68-106">**Column**</span></span>|<span data-ttu-id="acd68-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="acd68-107">**Type**</span></span>|<span data-ttu-id="acd68-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="acd68-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="acd68-109">prinID</span><span class="sxs-lookup"><span data-stu-id="acd68-109">prinID</span></span>  <br/> |<span data-ttu-id="acd68-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="acd68-110">int, not null</span></span>  <br/> |<span data-ttu-id="acd68-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="acd68-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="acd68-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="acd68-112">memberADPath</span></span>  <br/> |<span data-ttu-id="acd68-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="acd68-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="acd68-114">Nom d’un membre.</span><span class="sxs-lookup"><span data-stu-id="acd68-114">Distinguished name of a member.</span></span> <span data-ttu-id="acd68-115">Un membre n’a pas besoin d’être un principal (dans la table tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="acd68-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="acd68-116">**Keys**</span><span class="sxs-lookup"><span data-stu-id="acd68-116">**Keys**</span></span>

|<span data-ttu-id="acd68-117">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="acd68-117">**Column**</span></span>|<span data-ttu-id="acd68-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="acd68-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="acd68-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="acd68-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="acd68-120">prinID</span><span class="sxs-lookup"><span data-stu-id="acd68-120">prinID</span></span>  <br/> |<span data-ttu-id="acd68-121">Clé étrangère avec recherche dans tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="acd68-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

