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
description: La vue FileTranfer stocke des informations sur les sessions de transfert de fichiers d’égal à égal. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 5b7369769d8091aa3354ea364c7073dfa388986f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296409"
---
# <a name="filetransfers-view"></a><span data-ttu-id="79e4d-104">Vue filetransfers</span><span class="sxs-lookup"><span data-stu-id="79e4d-104">FileTransfers view</span></span>
 
<span data-ttu-id="79e4d-105">La vue FileTranfer stocke des informations sur les sessions de transfert de fichiers d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="79e4d-105">The FileTranfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="79e4d-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79e4d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79e4d-107">La vue filetransfers contient toutes les colonnes de [SessionDetails view](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="79e4d-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="79e4d-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="79e4d-108">**Column**</span></span>|<span data-ttu-id="79e4d-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="79e4d-109">**Data Type**</span></span>|<span data-ttu-id="79e4d-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="79e4d-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79e4d-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="79e4d-111">**FileName**</span></span> <br/> |<span data-ttu-id="79e4d-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="79e4d-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="79e4d-113">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="79e4d-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="79e4d-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="79e4d-114">**Cookie**</span></span> <br/> |<span data-ttu-id="79e4d-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="79e4d-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="79e4d-116">Utilisé pour identifier chaque message de suivi comme étant associé à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="79e4d-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="79e4d-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="79e4d-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="79e4d-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="79e4d-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="79e4d-119">Identificateur unique pour distinguer les transferts de fichiers impliquant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="79e4d-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="79e4d-120">**Accepter**</span><span class="sxs-lookup"><span data-stu-id="79e4d-120">**Accept**</span></span> <br/> |<span data-ttu-id="79e4d-121">bit</span><span class="sxs-lookup"><span data-stu-id="79e4d-121">bit</span></span>  <br/> |<span data-ttu-id="79e4d-122">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="79e4d-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="79e4d-123">Si TRUE, refuser et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="79e4d-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="79e4d-124">**Rejeter**</span><span class="sxs-lookup"><span data-stu-id="79e4d-124">**Reject**</span></span> <br/> |<span data-ttu-id="79e4d-125">bit</span><span class="sxs-lookup"><span data-stu-id="79e4d-125">bit</span></span>  <br/> |<span data-ttu-id="79e4d-126">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="79e4d-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="79e4d-127">Si la valeur TRUE, puis accepter et annuler sera NULL.</span><span class="sxs-lookup"><span data-stu-id="79e4d-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="79e4d-128">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="79e4d-128">**Cancel**</span></span> <br/> |<span data-ttu-id="79e4d-129">bit</span><span class="sxs-lookup"><span data-stu-id="79e4d-129">bit</span></span>  <br/> |<span data-ttu-id="79e4d-130">Peut avoir la valeur TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="79e4d-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="79e4d-131">Si la valeur TRUE, puis accepter et rejeter sera NULL.</span><span class="sxs-lookup"><span data-stu-id="79e4d-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

