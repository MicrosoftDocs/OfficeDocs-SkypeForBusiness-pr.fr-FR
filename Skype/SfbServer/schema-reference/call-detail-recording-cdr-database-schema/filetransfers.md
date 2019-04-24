---
title: Vue filetransfers
ms.reviewer: ''
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
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213087"
---
# <a name="filetransfers-view"></a><span data-ttu-id="84f6a-104">Vue filetransfers</span><span class="sxs-lookup"><span data-stu-id="84f6a-104">FileTransfers view</span></span>
 
<span data-ttu-id="84f6a-105">Le mode de transfert de fichiers stocke des informations sur les sessions de transfert de fichiers d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="84f6a-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="84f6a-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84f6a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="84f6a-107">La vue filetransfers contient toutes les colonnes de [SessionDetails view](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="84f6a-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="84f6a-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="84f6a-108">**Column**</span></span>|<span data-ttu-id="84f6a-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="84f6a-109">**Data Type**</span></span>|<span data-ttu-id="84f6a-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="84f6a-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84f6a-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="84f6a-111">**FileName**</span></span> <br/> |<span data-ttu-id="84f6a-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="84f6a-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="84f6a-113">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="84f6a-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="84f6a-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="84f6a-114">**Cookie**</span></span> <br/> |<span data-ttu-id="84f6a-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="84f6a-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="84f6a-116">Utilisé pour identifier chaque message de suivi comme étant associé à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="84f6a-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="84f6a-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="84f6a-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="84f6a-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="84f6a-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="84f6a-119">Identificateur unique pour distinguer les transferts de fichiers impliquant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="84f6a-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="84f6a-120">**Accepter**</span><span class="sxs-lookup"><span data-stu-id="84f6a-120">**Accept**</span></span> <br/> |<span data-ttu-id="84f6a-121">bit</span><span class="sxs-lookup"><span data-stu-id="84f6a-121">bit</span></span>  <br/> |<span data-ttu-id="84f6a-122">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="84f6a-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="84f6a-123">Si TRUE, refuser et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="84f6a-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="84f6a-124">**Rejeter**</span><span class="sxs-lookup"><span data-stu-id="84f6a-124">**Reject**</span></span> <br/> |<span data-ttu-id="84f6a-125">bit</span><span class="sxs-lookup"><span data-stu-id="84f6a-125">bit</span></span>  <br/> |<span data-ttu-id="84f6a-126">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="84f6a-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="84f6a-127">Si la valeur TRUE, puis accepter et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="84f6a-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="84f6a-128">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="84f6a-128">**Cancel**</span></span> <br/> |<span data-ttu-id="84f6a-129">bit</span><span class="sxs-lookup"><span data-stu-id="84f6a-129">bit</span></span>  <br/> |<span data-ttu-id="84f6a-130">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="84f6a-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="84f6a-131">Si la valeur TRUE, puis accepter et rejeter sera NULL.</span><span class="sxs-lookup"><span data-stu-id="84f6a-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

