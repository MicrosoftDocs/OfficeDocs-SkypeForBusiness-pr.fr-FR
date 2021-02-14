---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences client des utilisateurs. Il est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815904"
---
# <a name="tblpreference"></a><span data-ttu-id="231a8-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="231a8-104">tblPreference</span></span>

<span data-ttu-id="231a8-105">tblPreference contient les préférences client des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="231a8-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="231a8-106">Il est généralement utilisé par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="231a8-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="231a8-107">**Columns**</span><span class="sxs-lookup"><span data-stu-id="231a8-107">**Columns**</span></span>


| <span data-ttu-id="231a8-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="231a8-108">**Column**</span></span>            | <span data-ttu-id="231a8-109">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="231a8-109">**Type**</span></span>                        | <span data-ttu-id="231a8-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="231a8-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="231a8-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="231a8-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="231a8-112">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="231a8-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="231a8-113">Étiquette avec un format tel que : \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="231a8-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="231a8-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="231a8-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="231a8-115">entier, non null</span><span class="sxs-lookup"><span data-stu-id="231a8-115">int, not null</span></span>  <br/>            | <span data-ttu-id="231a8-116">Numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="231a8-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="231a8-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="231a8-117">prefContent</span></span>  <br/>    | <span data-ttu-id="231a8-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="231a8-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="231a8-119">Contenu codé.</span><span class="sxs-lookup"><span data-stu-id="231a8-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="231a8-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="231a8-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="231a8-121">entier, non null</span><span class="sxs-lookup"><span data-stu-id="231a8-121">int, not null</span></span>  <br/>            | <span data-ttu-id="231a8-122">ID du principal qui à mis à jour la préférence.</span><span class="sxs-lookup"><span data-stu-id="231a8-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="231a8-123">**Clé**</span><span class="sxs-lookup"><span data-stu-id="231a8-123">**Key**</span></span>

|<span data-ttu-id="231a8-124">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="231a8-124">**Column**</span></span>|<span data-ttu-id="231a8-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="231a8-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="231a8-126">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="231a8-126">Primary key.</span></span>  <br/> |


