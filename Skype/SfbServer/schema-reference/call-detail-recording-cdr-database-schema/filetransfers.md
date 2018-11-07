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
ms.sourcegitcommit: 27cd6d540485d5a1557a6131612894ca2f3516ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025156"
---
# <a name="filetransfers-view"></a><span data-ttu-id="0dfd9-104">Vue filetransfers</span><span class="sxs-lookup"><span data-stu-id="0dfd9-104">FileTransfers view</span></span>
 
<span data-ttu-id="0dfd9-105">Le mode de transfert de fichiers stocke des informations sur les sessions de transfert de fichiers d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="0dfd9-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0dfd9-107">La vue filetransfers contient toutes les colonnes de [SessionDetails view](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="0dfd9-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-108">**Column**</span></span>|<span data-ttu-id="0dfd9-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-109">**Data Type**</span></span>|<span data-ttu-id="0dfd9-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0dfd9-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-111">**FileName**</span></span> <br/> |<span data-ttu-id="0dfd9-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0dfd9-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0dfd9-113">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="0dfd9-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-114">**Cookie**</span></span> <br/> |<span data-ttu-id="0dfd9-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="0dfd9-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="0dfd9-116">Utilisé pour identifier chaque message de suivi comme étant associé à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="0dfd9-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="0dfd9-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="0dfd9-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="0dfd9-119">Identificateur unique pour distinguer les transferts de fichiers impliquant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="0dfd9-120">**Accepter**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-120">**Accept**</span></span> <br/> |<span data-ttu-id="0dfd9-121">bit</span><span class="sxs-lookup"><span data-stu-id="0dfd9-121">bit</span></span>  <br/> |<span data-ttu-id="0dfd9-122">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="0dfd9-123">Si TRUE, refuser et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="0dfd9-124">**Rejeter**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-124">**Reject**</span></span> <br/> |<span data-ttu-id="0dfd9-125">bit</span><span class="sxs-lookup"><span data-stu-id="0dfd9-125">bit</span></span>  <br/> |<span data-ttu-id="0dfd9-126">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="0dfd9-127">Si la valeur TRUE, puis accepter et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="0dfd9-128">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="0dfd9-128">**Cancel**</span></span> <br/> |<span data-ttu-id="0dfd9-129">bit</span><span class="sxs-lookup"><span data-stu-id="0dfd9-129">bit</span></span>  <br/> |<span data-ttu-id="0dfd9-130">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="0dfd9-131">Si la valeur TRUE, puis accepter et rejeter sera NULL.</span><span class="sxs-lookup"><span data-stu-id="0dfd9-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

