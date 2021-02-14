---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contient des jetons temporaires pour le transfert de fichiers.
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816014"
---
# <a name="tblfiletoken"></a><span data-ttu-id="c0571-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="c0571-103">tblFileToken</span></span>
 
<span data-ttu-id="c0571-104">tblFileToken contient des jetons temporaires pour le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c0571-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="c0571-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="c0571-105">**Columns**</span></span>

|<span data-ttu-id="c0571-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c0571-106">**Column**</span></span>|<span data-ttu-id="c0571-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="c0571-107">**Type**</span></span>|<span data-ttu-id="c0571-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="c0571-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0571-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="c0571-109">fileToken</span></span>  <br/> |<span data-ttu-id="c0571-110">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="c0571-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="c0571-111">Jeton unique (un GUID).</span><span class="sxs-lookup"><span data-stu-id="c0571-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="c0571-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="c0571-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="c0571-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="c0571-113">int, not null</span></span>  <br/> |<span data-ttu-id="c0571-114">ID du principal qui transfère le fichier.</span><span class="sxs-lookup"><span data-stu-id="c0571-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="c0571-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="c0571-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="c0571-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="c0571-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="c0571-117">GUID du nœud de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="c0571-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="c0571-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="c0571-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="c0571-119">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="c0571-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="c0571-p101">Heure d’expiration. Les jetons expirent après 30 minutes sauf s’ils sont épinglés (voir les descriptions suivantes dans cette colonne).</span><span class="sxs-lookup"><span data-stu-id="c0571-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="c0571-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="c0571-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="c0571-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c0571-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c0571-124">URL du fichier transféré (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="c0571-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="c0571-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="c0571-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="c0571-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c0571-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c0571-127">URL de la miniature du fichier transféré (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="c0571-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="c0571-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="c0571-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="c0571-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="c0571-129">datetime2</span></span>  <br/> |<span data-ttu-id="c0571-130">Horodatage de l’opération effective de transfert de fichier (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="c0571-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="c0571-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="c0571-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="c0571-132">bit</span><span class="sxs-lookup"><span data-stu-id="c0571-132">bit</span></span>  <br/> |<span data-ttu-id="c0571-133">True en cas de téléchargement sortant ; False en cas de téléchargement entrant (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="c0571-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="c0571-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="c0571-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="c0571-135">bit, non null</span><span class="sxs-lookup"><span data-stu-id="c0571-135">bit, not null</span></span>  <br/> |<span data-ttu-id="c0571-136">True si le jeton est épinglé.</span><span class="sxs-lookup"><span data-stu-id="c0571-136">True if token is pinned.</span></span> <span data-ttu-id="c0571-137">Il est utilisé pour conserver le jeton dans la table jusqu’à ce que le service de conformité ait la possibilité d’extraire les champs pertinents de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="c0571-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="c0571-138">**Keys**</span><span class="sxs-lookup"><span data-stu-id="c0571-138">**Keys**</span></span>

|<span data-ttu-id="c0571-139">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c0571-139">**Column**</span></span>|<span data-ttu-id="c0571-140">**Description**</span><span class="sxs-lookup"><span data-stu-id="c0571-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0571-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="c0571-141">fileToken</span></span>  <br/> |<span data-ttu-id="c0571-142">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="c0571-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c0571-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="c0571-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="c0571-144">Clé étrangère avec recherche dans la table tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="c0571-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

