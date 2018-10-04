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
description: tblPreference contient les préférences du client les utilisateurs. Cela est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375942"
---
# <a name="tblpreference"></a><span data-ttu-id="95b1c-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="95b1c-104">tblPreference</span></span>

<span data-ttu-id="95b1c-105">tblPreference contient les préférences du client les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="95b1c-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="95b1c-106">Cela est généralement utilisé par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="95b1c-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="95b1c-107">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="95b1c-107">**Columns**</span></span>


| <span data-ttu-id="95b1c-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="95b1c-108">**Column**</span></span>            | <span data-ttu-id="95b1c-109">**Type**</span><span class="sxs-lookup"><span data-stu-id="95b1c-109">**Type**</span></span>                        | <span data-ttu-id="95b1c-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="95b1c-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="95b1c-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="95b1c-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="95b1c-112">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="95b1c-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="95b1c-113">Étiquette dont le format telle que : \<uri sip utilisateur\></span><span class="sxs-lookup"><span data-stu-id="95b1c-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="95b1c-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="95b1c-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="95b1c-115">int, non null</span><span class="sxs-lookup"><span data-stu-id="95b1c-115">int, not null</span></span>  <br/>            | <span data-ttu-id="95b1c-116">Un numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="95b1c-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="95b1c-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="95b1c-117">prefContent</span></span>  <br/>    | <span data-ttu-id="95b1c-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="95b1c-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="95b1c-119">Contenu codé.</span><span class="sxs-lookup"><span data-stu-id="95b1c-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="95b1c-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="95b1c-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="95b1c-121">int, non null</span><span class="sxs-lookup"><span data-stu-id="95b1c-121">int, not null</span></span>  <br/>            | <span data-ttu-id="95b1c-122">ID du principal ayant la préférence de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="95b1c-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="95b1c-123">**Clé**</span><span class="sxs-lookup"><span data-stu-id="95b1c-123">**Key**</span></span>

|<span data-ttu-id="95b1c-124">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="95b1c-124">**Column**</span></span>|<span data-ttu-id="95b1c-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="95b1c-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="95b1c-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="95b1c-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="95b1c-127">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="95b1c-127">Primary key.</span></span>  <br/> |


