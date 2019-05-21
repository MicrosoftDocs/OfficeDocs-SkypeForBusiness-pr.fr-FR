---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences client de l’utilisateur. Il est généralement utilisé par les clients antérieurs à Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295341"
---
# <a name="tblpreference"></a><span data-ttu-id="16910-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="16910-104">tblPreference</span></span>

<span data-ttu-id="16910-105">tblPreference contient les préférences client de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="16910-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="16910-106">Il est généralement utilisé par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="16910-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="16910-107">**Celles**</span><span class="sxs-lookup"><span data-stu-id="16910-107">**Columns**</span></span>


| <span data-ttu-id="16910-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="16910-108">**Column**</span></span>            | <span data-ttu-id="16910-109">**Type**</span><span class="sxs-lookup"><span data-stu-id="16910-109">**Type**</span></span>                        | <span data-ttu-id="16910-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="16910-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="16910-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="16910-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="16910-112">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="16910-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="16910-113">Étiquette avec un format tel que: \<URI SIP utilisateur\></span><span class="sxs-lookup"><span data-stu-id="16910-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="16910-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="16910-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="16910-115">ent, non null</span><span class="sxs-lookup"><span data-stu-id="16910-115">int, not null</span></span>  <br/>            | <span data-ttu-id="16910-116">Un numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="16910-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="16910-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="16910-117">prefContent</span></span>  <br/>    | <span data-ttu-id="16910-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="16910-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="16910-119">Contenu encodé.</span><span class="sxs-lookup"><span data-stu-id="16910-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="16910-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="16910-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="16910-121">ent, non null</span><span class="sxs-lookup"><span data-stu-id="16910-121">int, not null</span></span>  <br/>            | <span data-ttu-id="16910-122">ID de l’objet principal qui a mis à jour la préférence.</span><span class="sxs-lookup"><span data-stu-id="16910-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="16910-123">**Clé**</span><span class="sxs-lookup"><span data-stu-id="16910-123">**Key**</span></span>

|<span data-ttu-id="16910-124">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="16910-124">**Column**</span></span>|<span data-ttu-id="16910-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="16910-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16910-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="16910-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="16910-127">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="16910-127">Primary key.</span></span>  <br/> |


