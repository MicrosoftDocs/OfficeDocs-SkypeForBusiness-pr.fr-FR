---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences du client les utilisateurs. Cela est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929917"
---
# <a name="tblpreference"></a><span data-ttu-id="07712-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="07712-104">tblPreference</span></span>

<span data-ttu-id="07712-105">tblPreference contient les préférences du client les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="07712-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="07712-106">Cela est généralement utilisé par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="07712-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="07712-107">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="07712-107">**Columns**</span></span>


| <span data-ttu-id="07712-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="07712-108">**Column**</span></span>            | <span data-ttu-id="07712-109">**Type**</span><span class="sxs-lookup"><span data-stu-id="07712-109">**Type**</span></span>                        | <span data-ttu-id="07712-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="07712-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="07712-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="07712-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="07712-112">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="07712-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="07712-113">Étiquette dont le format telle que : \<uri sip utilisateur\></span><span class="sxs-lookup"><span data-stu-id="07712-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="07712-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="07712-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="07712-115">int, non null</span><span class="sxs-lookup"><span data-stu-id="07712-115">int, not null</span></span>  <br/>            | <span data-ttu-id="07712-116">Un numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="07712-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="07712-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="07712-117">prefContent</span></span>  <br/>    | <span data-ttu-id="07712-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="07712-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="07712-119">Contenu codé.</span><span class="sxs-lookup"><span data-stu-id="07712-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="07712-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="07712-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="07712-121">int, non null</span><span class="sxs-lookup"><span data-stu-id="07712-121">int, not null</span></span>  <br/>            | <span data-ttu-id="07712-122">ID du principal ayant la préférence de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="07712-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="07712-123">**Clé**</span><span class="sxs-lookup"><span data-stu-id="07712-123">**Key**</span></span>

|<span data-ttu-id="07712-124">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="07712-124">**Column**</span></span>|<span data-ttu-id="07712-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="07712-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07712-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="07712-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="07712-127">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="07712-127">Primary key.</span></span>  <br/> |


