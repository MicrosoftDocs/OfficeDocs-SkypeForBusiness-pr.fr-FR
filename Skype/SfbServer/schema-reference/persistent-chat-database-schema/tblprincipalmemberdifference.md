---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient le groupe d’appartenance modifications (à la fois membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation des Services de domaine Active Directory.
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902235"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="57235-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="57235-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="57235-104">tblPrincipalMemberDifference contient le groupe d’appartenance modifications (à la fois membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation des Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="57235-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="57235-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="57235-105">**Columns**</span></span>

|<span data-ttu-id="57235-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="57235-106">**Column**</span></span>|<span data-ttu-id="57235-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="57235-107">**Type**</span></span>|<span data-ttu-id="57235-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="57235-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57235-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="57235-109">prinGuid</span></span>  <br/> |<span data-ttu-id="57235-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="57235-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="57235-111">GUID principal du groupe qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="57235-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="57235-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="57235-112">memberADPath</span></span>  <br/> |<span data-ttu-id="57235-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="57235-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="57235-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="57235-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="57235-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="57235-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="57235-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="57235-116">bit, not null</span></span>  <br/> |<span data-ttu-id="57235-117">False si le membre a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="57235-117">False if the member was added.</span></span> <span data-ttu-id="57235-118">True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="57235-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="57235-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="57235-119">**Key**</span></span>

|<span data-ttu-id="57235-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="57235-120">**Column**</span></span>|<span data-ttu-id="57235-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="57235-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="57235-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="57235-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="57235-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="57235-123">Primary key.</span></span>  <br/> |
   

