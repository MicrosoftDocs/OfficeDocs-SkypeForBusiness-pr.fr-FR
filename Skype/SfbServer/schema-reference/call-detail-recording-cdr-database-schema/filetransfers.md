---
title: Vue de FileTransfers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vue FileTranfer stocke des informations sur les sessions de transfert de fichier de peer-to-peer. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a><span data-ttu-id="323a0-104">Vue de FileTransfers</span><span class="sxs-lookup"><span data-stu-id="323a0-104">FileTransfers view</span></span>
 
<span data-ttu-id="323a0-105">La vue FileTranfer stocke des informations sur les sessions de transfert de fichier de peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="323a0-105">The FileTranfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="323a0-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="323a0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="323a0-107">La vue FileTransfers contient toutes les colonnes dans la [vue de le SessionDetails](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="323a0-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="323a0-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="323a0-108">**Column**</span></span>|<span data-ttu-id="323a0-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="323a0-109">**Data Type**</span></span>|<span data-ttu-id="323a0-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="323a0-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="323a0-111">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="323a0-111">**FileName**</span></span> <br/> |<span data-ttu-id="323a0-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="323a0-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="323a0-113">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="323a0-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="323a0-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="323a0-114">**Cookie**</span></span> <br/> |<span data-ttu-id="323a0-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="323a0-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="323a0-116">Utilisé pour identifier chaque message suivi comme étant associée à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="323a0-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="323a0-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="323a0-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="323a0-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="323a0-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="323a0-119">Identificateur unique pour faire la distinction entre les transferts de fichiers portant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="323a0-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="323a0-120">**Accepter**</span><span class="sxs-lookup"><span data-stu-id="323a0-120">**Accept**</span></span> <br/> |<span data-ttu-id="323a0-121">bit</span><span class="sxs-lookup"><span data-stu-id="323a0-121">bit</span></span>  <br/> |<span data-ttu-id="323a0-122">Peut être TRUE ou la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="323a0-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="323a0-123">Si TRUE, refuser et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="323a0-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="323a0-124">**Rejeter**</span><span class="sxs-lookup"><span data-stu-id="323a0-124">**Reject**</span></span> <br/> |<span data-ttu-id="323a0-125">bit</span><span class="sxs-lookup"><span data-stu-id="323a0-125">bit</span></span>  <br/> |<span data-ttu-id="323a0-126">Peut être TRUE ou la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="323a0-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="323a0-127">Si TRUE, alors accepter et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="323a0-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="323a0-128">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="323a0-128">**Cancel**</span></span> <br/> |<span data-ttu-id="323a0-129">bit</span><span class="sxs-lookup"><span data-stu-id="323a0-129">bit</span></span>  <br/> |<span data-ttu-id="323a0-130">Peut être TRUE ou la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="323a0-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="323a0-131">Si TRUE, alors accepter et rejeter sera NULL.</span><span class="sxs-lookup"><span data-stu-id="323a0-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

