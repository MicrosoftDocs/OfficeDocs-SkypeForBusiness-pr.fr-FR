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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient les modifications d’appartenance au groupe (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation des services de domaine Active Directory.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295299"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="1cc81-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="1cc81-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="1cc81-104">tblPrincipalMemberDifference contient les modifications d’appartenance au groupe (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1cc81-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="1cc81-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="1cc81-105">**Columns**</span></span>

|<span data-ttu-id="1cc81-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1cc81-106">**Column**</span></span>|<span data-ttu-id="1cc81-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="1cc81-107">**Type**</span></span>|<span data-ttu-id="1cc81-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="1cc81-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1cc81-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="1cc81-109">prinGuid</span></span>  <br/> |<span data-ttu-id="1cc81-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="1cc81-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="1cc81-111">GUID principal du groupe qui a changé.</span><span class="sxs-lookup"><span data-stu-id="1cc81-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="1cc81-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="1cc81-112">memberADPath</span></span>  <br/> |<span data-ttu-id="1cc81-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1cc81-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="1cc81-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="1cc81-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="1cc81-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="1cc81-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="1cc81-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="1cc81-116">bit, not null</span></span>  <br/> |<span data-ttu-id="1cc81-117">False si le membre a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="1cc81-117">False if the member was added.</span></span> <span data-ttu-id="1cc81-118">True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="1cc81-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="1cc81-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="1cc81-119">**Key**</span></span>

|<span data-ttu-id="1cc81-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1cc81-120">**Column**</span></span>|<span data-ttu-id="1cc81-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="1cc81-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1cc81-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="1cc81-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="1cc81-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="1cc81-123">Primary key.</span></span>  <br/> |
   

