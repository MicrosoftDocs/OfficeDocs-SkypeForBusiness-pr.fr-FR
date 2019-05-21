---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contient des jetons temporaires aux fins de transfert de fichiers.
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295404"
---
# <a name="tblfiletoken"></a><span data-ttu-id="5601e-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="5601e-103">tblFileToken</span></span>
 
<span data-ttu-id="5601e-104">tblFileToken contient des jetons temporaires aux fins de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="5601e-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="5601e-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="5601e-105">**Columns**</span></span>

|<span data-ttu-id="5601e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5601e-106">**Column**</span></span>|<span data-ttu-id="5601e-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="5601e-107">**Type**</span></span>|<span data-ttu-id="5601e-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="5601e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5601e-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="5601e-109">fileToken</span></span>  <br/> |<span data-ttu-id="5601e-110">nvarchar (50), pas null</span><span class="sxs-lookup"><span data-stu-id="5601e-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="5601e-111">Jeton unique (GUID).</span><span class="sxs-lookup"><span data-stu-id="5601e-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="5601e-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="5601e-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="5601e-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="5601e-113">int, not null</span></span>  <br/> |<span data-ttu-id="5601e-114">ID du principal qui transfère le fichier.</span><span class="sxs-lookup"><span data-stu-id="5601e-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="5601e-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5601e-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="5601e-116">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="5601e-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="5601e-117">GUID du nœud de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="5601e-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="5601e-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="5601e-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="5601e-119">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="5601e-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="5601e-120">Durée d’expiration.</span><span class="sxs-lookup"><span data-stu-id="5601e-120">Expiration time.</span></span> <span data-ttu-id="5601e-121">(Les jetons expirent au bout de 30 minutes, sauf s’ils sont épinglés (voir les descriptions suivies dans cette colonne).</span><span class="sxs-lookup"><span data-stu-id="5601e-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="5601e-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="5601e-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="5601e-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5601e-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5601e-124">URL du fichier transféré (pour une utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="5601e-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="5601e-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="5601e-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="5601e-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5601e-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5601e-127">URL de la miniature du fichier transféré (pour une utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="5601e-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="5601e-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="5601e-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="5601e-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="5601e-129">datetime2</span></span>  <br/> |<span data-ttu-id="5601e-130">Horodatage de l’opération de transfert de fichiers réelle (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="5601e-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="5601e-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="5601e-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="5601e-132">bit</span><span class="sxs-lookup"><span data-stu-id="5601e-132">bit</span></span>  <br/> |<span data-ttu-id="5601e-133">True si Télécharger; Faux si Télécharger (pour une utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="5601e-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="5601e-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="5601e-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="5601e-135">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="5601e-135">bit, not null</span></span>  <br/> |<span data-ttu-id="5601e-136">True si le jeton est épinglé.</span><span class="sxs-lookup"><span data-stu-id="5601e-136">True if token is pinned.</span></span> <span data-ttu-id="5601e-137">Il est utilisé pour conserver le jeton dans le tableau jusqu’à ce que le service de conformité puisse récupérer les champs appropriés.</span><span class="sxs-lookup"><span data-stu-id="5601e-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="5601e-138">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="5601e-138">**Keys**</span></span>

|<span data-ttu-id="5601e-139">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5601e-139">**Column**</span></span>|<span data-ttu-id="5601e-140">**Description**</span><span class="sxs-lookup"><span data-stu-id="5601e-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5601e-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="5601e-141">fileToken</span></span>  <br/> |<span data-ttu-id="5601e-142">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5601e-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5601e-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5601e-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="5601e-144">Clé étrangère avec recherche dans la table tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="5601e-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

