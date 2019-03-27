---
title: tblPreference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences du client les utilisateurs. Cela est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879790"
---
# <a name="tblpreference"></a><span data-ttu-id="3c262-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="3c262-104">tblPreference</span></span>

<span data-ttu-id="3c262-105">tblPreference contient les préférences du client les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3c262-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="3c262-106">Cela est généralement utilisé par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3c262-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="3c262-107">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="3c262-107">**Columns**</span></span>


| <span data-ttu-id="3c262-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3c262-108">**Column**</span></span>            | <span data-ttu-id="3c262-109">**Type**</span><span class="sxs-lookup"><span data-stu-id="3c262-109">**Type**</span></span>                        | <span data-ttu-id="3c262-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="3c262-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="3c262-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="3c262-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="3c262-112">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="3c262-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="3c262-113">Étiquette dont le format telle que : \<uri sip utilisateur\></span><span class="sxs-lookup"><span data-stu-id="3c262-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="3c262-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="3c262-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="3c262-115">int, non null</span><span class="sxs-lookup"><span data-stu-id="3c262-115">int, not null</span></span>  <br/>            | <span data-ttu-id="3c262-116">Un numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="3c262-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="3c262-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="3c262-117">prefContent</span></span>  <br/>    | <span data-ttu-id="3c262-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="3c262-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="3c262-119">Contenu codé.</span><span class="sxs-lookup"><span data-stu-id="3c262-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="3c262-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="3c262-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="3c262-121">int, non null</span><span class="sxs-lookup"><span data-stu-id="3c262-121">int, not null</span></span>  <br/>            | <span data-ttu-id="3c262-122">ID du principal ayant la préférence de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="3c262-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="3c262-123">**Clé**</span><span class="sxs-lookup"><span data-stu-id="3c262-123">**Key**</span></span>

|<span data-ttu-id="3c262-124">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3c262-124">**Column**</span></span>|<span data-ttu-id="3c262-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="3c262-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c262-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="3c262-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="3c262-127">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="3c262-127">Primary key.</span></span>  <br/> |


