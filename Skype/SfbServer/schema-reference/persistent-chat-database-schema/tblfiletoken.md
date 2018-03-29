---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contient les jetons temporaires à des fins de transfert de fichier.
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a><span data-ttu-id="1170e-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="1170e-103">tblFileToken</span></span>
 
<span data-ttu-id="1170e-104">tblFileToken contient les jetons temporaires à des fins de transfert de fichier.</span><span class="sxs-lookup"><span data-stu-id="1170e-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="1170e-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="1170e-105">**Columns**</span></span>

|<span data-ttu-id="1170e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1170e-106">**Column**</span></span>|<span data-ttu-id="1170e-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="1170e-107">**Type**</span></span>|<span data-ttu-id="1170e-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="1170e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1170e-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="1170e-109">fileToken</span></span>  <br/> |<span data-ttu-id="1170e-110">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="1170e-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="1170e-111">Jeton unique (un GUID).</span><span class="sxs-lookup"><span data-stu-id="1170e-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="1170e-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="1170e-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="1170e-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="1170e-113">int, not null</span></span>  <br/> |<span data-ttu-id="1170e-114">ID de l’entité de sécurité qui est de transférer le fichier.</span><span class="sxs-lookup"><span data-stu-id="1170e-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="1170e-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="1170e-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="1170e-116">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="1170e-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="1170e-117">GUID du nœud de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="1170e-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="1170e-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="1170e-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="1170e-119">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="1170e-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="1170e-120">Délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="1170e-120">Expiration time.</span></span> <span data-ttu-id="1170e-121">(Les jetons expirent après 30 minutes, à moins qu’épinglé (voir les descriptions suivantes dans cette colonne).</span><span class="sxs-lookup"><span data-stu-id="1170e-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="1170e-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="1170e-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="1170e-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1170e-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1170e-124">URL du fichier transféré (pour une utilisation du service de mise en conformité).</span><span class="sxs-lookup"><span data-stu-id="1170e-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="1170e-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="1170e-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="1170e-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1170e-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1170e-127">URL de la miniature représentant le fichier transféré (pour une utilisation du service de mise en conformité).</span><span class="sxs-lookup"><span data-stu-id="1170e-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="1170e-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="1170e-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="1170e-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="1170e-129">datetime2</span></span>  <br/> |<span data-ttu-id="1170e-130">Horodateur de l’opération de transfert de fichier (pour une utilisation du service de mise en conformité).</span><span class="sxs-lookup"><span data-stu-id="1170e-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="1170e-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="1170e-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="1170e-132">bit</span><span class="sxs-lookup"><span data-stu-id="1170e-132">bit</span></span>  <br/> |<span data-ttu-id="1170e-133">True si le téléchargement ; False si télécharger (pour une utilisation du service de mise en conformité).</span><span class="sxs-lookup"><span data-stu-id="1170e-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="1170e-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="1170e-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="1170e-135">bits, non null</span><span class="sxs-lookup"><span data-stu-id="1170e-135">bit, not null</span></span>  <br/> |<span data-ttu-id="1170e-136">True si le jeton est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="1170e-136">True if token is pinned.</span></span> <span data-ttu-id="1170e-137">Il est utilisé pour conserver le jeton dans la table jusqu'à ce que le service de mise en conformité pour extraire les champs appropriés.</span><span class="sxs-lookup"><span data-stu-id="1170e-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="1170e-138">**Clés**</span><span class="sxs-lookup"><span data-stu-id="1170e-138">**Keys**</span></span>

|<span data-ttu-id="1170e-139">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1170e-139">**Column**</span></span>|<span data-ttu-id="1170e-140">**Description**</span><span class="sxs-lookup"><span data-stu-id="1170e-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1170e-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="1170e-141">fileToken</span></span>  <br/> |<span data-ttu-id="1170e-142">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="1170e-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1170e-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="1170e-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="1170e-144">Clé étrangère avec la recherche dans la table de tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="1170e-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

