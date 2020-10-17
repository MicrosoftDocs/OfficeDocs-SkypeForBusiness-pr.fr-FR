---
title: 'Lync Server 2013 : tblFileToken'
description: 'Lync Server 2013 : tblFileToken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547630"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="5fe27-103">tblFileToken dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fe27-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fe27-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5fe27-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5fe27-105">tblFileToken contient des jetons temporaires pour le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="5fe27-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="5fe27-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="5fe27-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fe27-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="5fe27-107">Column</span></span></th>
<th><span data-ttu-id="5fe27-108">Type</span><span class="sxs-lookup"><span data-stu-id="5fe27-108">Type</span></span></th>
<th><span data-ttu-id="5fe27-109">Description</span><span class="sxs-lookup"><span data-stu-id="5fe27-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fe27-110">fileToken</span><span class="sxs-lookup"><span data-stu-id="5fe27-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="5fe27-111">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="5fe27-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="5fe27-112">Jeton unique (un GUID).</span><span class="sxs-lookup"><span data-stu-id="5fe27-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe27-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="5fe27-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="5fe27-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="5fe27-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fe27-115">ID du principal qui transfère le fichier.</span><span class="sxs-lookup"><span data-stu-id="5fe27-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fe27-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5fe27-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="5fe27-117">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="5fe27-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5fe27-118">GUID du nœud de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="5fe27-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe27-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="5fe27-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="5fe27-120">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="5fe27-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="5fe27-p101">Heure d’expiration. Les jetons expirent après 30 minutes sauf s’ils sont épinglés (voir les descriptions suivantes dans cette colonne).</span><span class="sxs-lookup"><span data-stu-id="5fe27-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fe27-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="5fe27-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="5fe27-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5fe27-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fe27-125">URL du fichier transféré (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="5fe27-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe27-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="5fe27-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="5fe27-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5fe27-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fe27-128">URL de la miniature du fichier transféré (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="5fe27-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fe27-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="5fe27-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="5fe27-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="5fe27-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="5fe27-131">Horodatage de l’opération effective de transfert de fichier (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="5fe27-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe27-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="5fe27-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="5fe27-133">légèrement</span><span class="sxs-lookup"><span data-stu-id="5fe27-133">bit</span></span></p></td>
<td><p><span data-ttu-id="5fe27-134">True en cas de téléchargement sortant ; False en cas de téléchargement entrant (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="5fe27-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fe27-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="5fe27-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="5fe27-136">bit, non null</span><span class="sxs-lookup"><span data-stu-id="5fe27-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5fe27-p102">True si le jeton est épinglé. Cela permet de garder le jeton dans la table jusqu’à ce que le service de conformité puisse y récupérer les champs appropriés.</span><span class="sxs-lookup"><span data-stu-id="5fe27-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5fe27-139">Keys</span><span class="sxs-lookup"><span data-stu-id="5fe27-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fe27-140">Colonne</span><span class="sxs-lookup"><span data-stu-id="5fe27-140">Column</span></span></th>
<th><span data-ttu-id="5fe27-141">Description</span><span class="sxs-lookup"><span data-stu-id="5fe27-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fe27-142">fileToken</span><span class="sxs-lookup"><span data-stu-id="5fe27-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="5fe27-143">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5fe27-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe27-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5fe27-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="5fe27-145">Clé étrangère avec recherche dans la table tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="5fe27-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

