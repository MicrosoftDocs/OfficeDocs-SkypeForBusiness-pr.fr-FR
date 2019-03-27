---
title: tblFileToken
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contient des jetons temporaires pour le transfert de fichiers.
ms.openlocfilehash: 46553a4b8752e2a95691dc2042a2632845166fc7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881297"
---
# <a name="tblfiletoken"></a><span data-ttu-id="cb83d-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="cb83d-103">tblFileToken</span></span>
 
<span data-ttu-id="cb83d-104">tblFileToken contient des jetons temporaires pour le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cb83d-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="cb83d-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="cb83d-105">**Columns**</span></span>

|<span data-ttu-id="cb83d-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cb83d-106">**Column**</span></span>|<span data-ttu-id="cb83d-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="cb83d-107">**Type**</span></span>|<span data-ttu-id="cb83d-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="cb83d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb83d-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="cb83d-109">fileToken</span></span>  <br/> |<span data-ttu-id="cb83d-110">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="cb83d-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="cb83d-111">Jeton unique (GUID).</span><span class="sxs-lookup"><span data-stu-id="cb83d-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="cb83d-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="cb83d-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="cb83d-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="cb83d-113">int, not null</span></span>  <br/> |<span data-ttu-id="cb83d-114">ID du principal qui transfère le fichier.</span><span class="sxs-lookup"><span data-stu-id="cb83d-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="cb83d-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="cb83d-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="cb83d-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="cb83d-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="cb83d-117">GUID du nœud de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="cb83d-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="cb83d-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="cb83d-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="cb83d-119">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="cb83d-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="cb83d-120">Délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="cb83d-120">Expiration time.</span></span> <span data-ttu-id="cb83d-121">(Jetons expirent au bout de 30 minutes, à moins qu’épinglé (consultez les descriptions suivantes dans cette colonne).</span><span class="sxs-lookup"><span data-stu-id="cb83d-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="cb83d-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="cb83d-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="cb83d-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cb83d-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cb83d-124">URL du fichier transféré (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="cb83d-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="cb83d-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="cb83d-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="cb83d-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cb83d-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cb83d-127">URL de la miniature du fichier transféré (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="cb83d-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="cb83d-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="cb83d-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="cb83d-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="cb83d-129">datetime2</span></span>  <br/> |<span data-ttu-id="cb83d-130">Horodatage de l’opération de transfert de fichier (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="cb83d-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="cb83d-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="cb83d-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="cb83d-132">bit</span><span class="sxs-lookup"><span data-stu-id="cb83d-132">bit</span></span>  <br/> |<span data-ttu-id="cb83d-133">True si télécharger ; False si Téléchargez (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="cb83d-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="cb83d-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="cb83d-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="cb83d-135">bit, non null</span><span class="sxs-lookup"><span data-stu-id="cb83d-135">bit, not null</span></span>  <br/> |<span data-ttu-id="cb83d-136">True si le jeton est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="cb83d-136">True if token is pinned.</span></span> <span data-ttu-id="cb83d-137">Il est utilisé pour conserver le jeton dans la table jusqu'à ce que le service de conformité pour extraire les champs appropriés.</span><span class="sxs-lookup"><span data-stu-id="cb83d-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="cb83d-138">**Clés**</span><span class="sxs-lookup"><span data-stu-id="cb83d-138">**Keys**</span></span>

|<span data-ttu-id="cb83d-139">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cb83d-139">**Column**</span></span>|<span data-ttu-id="cb83d-140">**Description**</span><span class="sxs-lookup"><span data-stu-id="cb83d-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cb83d-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="cb83d-141">fileToken</span></span>  <br/> |<span data-ttu-id="cb83d-142">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="cb83d-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="cb83d-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="cb83d-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="cb83d-144">Clé étrangère avec recherche dans la table tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="cb83d-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

