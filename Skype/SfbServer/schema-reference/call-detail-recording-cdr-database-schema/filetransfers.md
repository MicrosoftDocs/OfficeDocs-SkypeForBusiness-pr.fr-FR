---
title: Vue filetransfers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Le mode de transfert de fichiers stocke des informations sur les sessions de transfert de fichiers d’égal à égal. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 97bc5f957192c8a2c6d888f81fce0891aa2b4f75
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531218"
---
# <a name="filetransfers-view"></a><span data-ttu-id="676fb-104">Vue filetransfers</span><span class="sxs-lookup"><span data-stu-id="676fb-104">FileTransfers view</span></span>
 
<span data-ttu-id="676fb-105">Le mode de transfert de fichiers stocke des informations sur les sessions de transfert de fichiers d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="676fb-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="676fb-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="676fb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="676fb-107">La vue filetransfers contient toutes les colonnes de [SessionDetails view](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="676fb-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="676fb-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="676fb-108">**Column**</span></span>|<span data-ttu-id="676fb-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="676fb-109">**Data Type**</span></span>|<span data-ttu-id="676fb-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="676fb-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="676fb-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="676fb-111">**FileName**</span></span> <br/> |<span data-ttu-id="676fb-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="676fb-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="676fb-113">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="676fb-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="676fb-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="676fb-114">**Cookie**</span></span> <br/> |<span data-ttu-id="676fb-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="676fb-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="676fb-116">Utilisé pour identifier chaque message de suivi comme étant associé à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="676fb-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="676fb-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="676fb-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="676fb-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="676fb-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="676fb-119">Identificateur unique pour distinguer les transferts de fichiers impliquant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="676fb-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="676fb-120">**Accepter**</span><span class="sxs-lookup"><span data-stu-id="676fb-120">**Accept**</span></span> <br/> |<span data-ttu-id="676fb-121">bit</span><span class="sxs-lookup"><span data-stu-id="676fb-121">bit</span></span>  <br/> |<span data-ttu-id="676fb-122">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="676fb-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="676fb-123">Si TRUE, refuser et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="676fb-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="676fb-124">**Rejeter**</span><span class="sxs-lookup"><span data-stu-id="676fb-124">**Reject**</span></span> <br/> |<span data-ttu-id="676fb-125">bit</span><span class="sxs-lookup"><span data-stu-id="676fb-125">bit</span></span>  <br/> |<span data-ttu-id="676fb-126">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="676fb-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="676fb-127">Si la valeur TRUE, puis accepter et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="676fb-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="676fb-128">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="676fb-128">**Cancel**</span></span> <br/> |<span data-ttu-id="676fb-129">bit</span><span class="sxs-lookup"><span data-stu-id="676fb-129">bit</span></span>  <br/> |<span data-ttu-id="676fb-130">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="676fb-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="676fb-131">Si la valeur TRUE, puis accepter et rejeter sera NULL.</span><span class="sxs-lookup"><span data-stu-id="676fb-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

