---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences de l’utilisateur client. Elle est généralement utilisée par des clients antérieurs à Lync 2013.
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a><span data-ttu-id="a42fa-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="a42fa-104">tblPreference</span></span>
 
<span data-ttu-id="a42fa-105">tblPreference contient les préférences de l’utilisateur client.</span><span class="sxs-lookup"><span data-stu-id="a42fa-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="a42fa-106">Elle est généralement utilisée par des clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a42fa-106">This is generally used by clients previous to Lync 2013.</span></span>
  
<span data-ttu-id="a42fa-107">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="a42fa-107">**Columns**</span></span>

|<span data-ttu-id="a42fa-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a42fa-108">**Column**</span></span>|<span data-ttu-id="a42fa-109">**Type de**</span><span class="sxs-lookup"><span data-stu-id="a42fa-109">**Type**</span></span>|<span data-ttu-id="a42fa-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="a42fa-110">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a42fa-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="a42fa-111">prefLabel</span></span>  <br/> |<span data-ttu-id="a42fa-112">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="a42fa-112">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a42fa-113">Étiquette avec un format tel que : \<utilisateur sip uri\></span><span class="sxs-lookup"><span data-stu-id="a42fa-113">Label with a format such as: \<user sip uri\></span></span>|<span data-ttu-id="a42fa-114">nom d’utilisateur. \<préférences\>.</span><span class="sxs-lookup"><span data-stu-id="a42fa-114">username.\<preference set\>.</span></span>  <br/> |
|<span data-ttu-id="a42fa-115">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="a42fa-115">prefSeqID</span></span>  <br/> |<span data-ttu-id="a42fa-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="a42fa-116">int, not null</span></span>  <br/> |<span data-ttu-id="a42fa-117">Un numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="a42fa-117">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
|<span data-ttu-id="a42fa-118">prefContent</span><span class="sxs-lookup"><span data-stu-id="a42fa-118">prefContent</span></span>  <br/> |<span data-ttu-id="a42fa-119">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a42fa-119">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="a42fa-120">Contenu codé.</span><span class="sxs-lookup"><span data-stu-id="a42fa-120">Encoded content.</span></span>  <br/> |
|<span data-ttu-id="a42fa-121">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="a42fa-121">lastModifiedBy</span></span>  <br/> |<span data-ttu-id="a42fa-122">int, non null</span><span class="sxs-lookup"><span data-stu-id="a42fa-122">int, not null</span></span>  <br/> |<span data-ttu-id="a42fa-123">ID de l’entité de la préférence de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a42fa-123">ID of the principal that updated the preference.</span></span>  <br/> |
   
<span data-ttu-id="a42fa-124">**Clé**</span><span class="sxs-lookup"><span data-stu-id="a42fa-124">**Key**</span></span>

|<span data-ttu-id="a42fa-125">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a42fa-125">**Column**</span></span>|<span data-ttu-id="a42fa-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="a42fa-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a42fa-127">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="a42fa-127">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="a42fa-128">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a42fa-128">Primary key.</span></span>  <br/> |
   

