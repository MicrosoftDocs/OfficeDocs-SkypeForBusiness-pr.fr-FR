---
title: Affichage FileTransfers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Le mode FileTransfer stocke les informations sur les sessions d’égal à égal de transfert de fichiers. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815202"
---
# <a name="filetransfers-view"></a><span data-ttu-id="866d9-104">Affichage FileTransfers</span><span class="sxs-lookup"><span data-stu-id="866d9-104">FileTransfers view</span></span>
 
<span data-ttu-id="866d9-105">Le mode FileTransfer stocke les informations sur les sessions d’égal à égal de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="866d9-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="866d9-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="866d9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="866d9-107">Le mode FileTransfers contient toutes les colonnes de la [vue SessionDetails](sessiondetails-0.md) , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="866d9-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="866d9-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="866d9-108">**Column**</span></span>|<span data-ttu-id="866d9-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="866d9-109">**Data Type**</span></span>|<span data-ttu-id="866d9-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="866d9-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="866d9-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="866d9-111">**FileName**</span></span> <br/> |<span data-ttu-id="866d9-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="866d9-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="866d9-113">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="866d9-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="866d9-114">**Sans**</span><span class="sxs-lookup"><span data-stu-id="866d9-114">**Cookie**</span></span> <br/> |<span data-ttu-id="866d9-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="866d9-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="866d9-116">Permet de détecter chaque message de suivi associé à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="866d9-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="866d9-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="866d9-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="866d9-118">identificateur</span><span class="sxs-lookup"><span data-stu-id="866d9-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="866d9-119">Identificateur unique permettant de faire la distinction entre les transferts de fichiers impliquant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="866d9-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="866d9-120">**Valide**</span><span class="sxs-lookup"><span data-stu-id="866d9-120">**Accept**</span></span> <br/> |<span data-ttu-id="866d9-121">bit</span><span class="sxs-lookup"><span data-stu-id="866d9-121">bit</span></span>  <br/> |<span data-ttu-id="866d9-122">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="866d9-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="866d9-123">Si vrai, l’argument refuser et annuler est nul.</span><span class="sxs-lookup"><span data-stu-id="866d9-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="866d9-124">**Rejeter**</span><span class="sxs-lookup"><span data-stu-id="866d9-124">**Reject**</span></span> <br/> |<span data-ttu-id="866d9-125">bit</span><span class="sxs-lookup"><span data-stu-id="866d9-125">bit</span></span>  <br/> |<span data-ttu-id="866d9-126">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="866d9-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="866d9-127">Si vrai, l’argument accepter et annuler est nul.</span><span class="sxs-lookup"><span data-stu-id="866d9-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="866d9-128">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="866d9-128">**Cancel**</span></span> <br/> |<span data-ttu-id="866d9-129">bit</span><span class="sxs-lookup"><span data-stu-id="866d9-129">bit</span></span>  <br/> |<span data-ttu-id="866d9-130">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="866d9-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="866d9-131">Si vrai, l’argument accepter et refuser est nul.</span><span class="sxs-lookup"><span data-stu-id="866d9-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

