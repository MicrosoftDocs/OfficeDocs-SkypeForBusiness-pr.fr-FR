---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes de synchronisation des services de domaine Active Directory ultérieures.
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809704"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="d3a17-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="d3a17-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="d3a17-104">tblPrincipalMemberDifference contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes de synchronisation des services de domaine Active Directory ultérieures.</span><span class="sxs-lookup"><span data-stu-id="d3a17-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="d3a17-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d3a17-105">**Columns**</span></span>

|<span data-ttu-id="d3a17-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d3a17-106">**Column**</span></span>|<span data-ttu-id="d3a17-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="d3a17-107">**Type**</span></span>|<span data-ttu-id="d3a17-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d3a17-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3a17-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d3a17-109">prinGuid</span></span>  <br/> |<span data-ttu-id="d3a17-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="d3a17-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d3a17-111">GUID principal du groupe qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="d3a17-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="d3a17-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="d3a17-112">memberADPath</span></span>  <br/> |<span data-ttu-id="d3a17-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d3a17-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="d3a17-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="d3a17-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="d3a17-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="d3a17-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="d3a17-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="d3a17-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d3a17-p101">False si le membre a été ajouté. True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="d3a17-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="d3a17-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="d3a17-119">**Key**</span></span>

|<span data-ttu-id="d3a17-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d3a17-120">**Column**</span></span>|<span data-ttu-id="d3a17-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="d3a17-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="d3a17-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d3a17-122">Primary key.</span></span>  <br/> |
   

