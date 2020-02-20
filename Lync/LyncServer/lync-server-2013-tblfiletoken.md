---
title: 'Lync Server 2013 : tblFileToken'
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
ms.openlocfilehash: 9e3d80b1a326140a94b840c212fc8577a73e468f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="510c7-102">tblFileToken dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="510c7-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="510c7-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="510c7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="510c7-104">tblFileToken contient des jetons temporaires pour le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="510c7-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="510c7-105">Columns</span><span class="sxs-lookup"><span data-stu-id="510c7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="510c7-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="510c7-106">Column</span></span></th>
<th><span data-ttu-id="510c7-107">Type</span><span class="sxs-lookup"><span data-stu-id="510c7-107">Type</span></span></th>
<th><span data-ttu-id="510c7-108">Description</span><span class="sxs-lookup"><span data-stu-id="510c7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="510c7-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="510c7-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="510c7-110">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="510c7-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="510c7-111">Jeton unique (un GUID).</span><span class="sxs-lookup"><span data-stu-id="510c7-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="510c7-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="510c7-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="510c7-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="510c7-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="510c7-114">ID du principal qui transfère le fichier.</span><span class="sxs-lookup"><span data-stu-id="510c7-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="510c7-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="510c7-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="510c7-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="510c7-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="510c7-117">GUID du nœud de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="510c7-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="510c7-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="510c7-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="510c7-119">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="510c7-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="510c7-p101">Heure d’expiration. Les jetons expirent après 30 minutes sauf s’ils sont épinglés (voir les descriptions suivantes dans cette colonne).</span><span class="sxs-lookup"><span data-stu-id="510c7-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="510c7-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="510c7-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="510c7-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="510c7-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="510c7-124">URL du fichier transféré (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="510c7-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="510c7-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="510c7-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="510c7-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="510c7-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="510c7-127">URL de la miniature du fichier transféré (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="510c7-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="510c7-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="510c7-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="510c7-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="510c7-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="510c7-130">Horodatage de l’opération effective de transfert de fichier (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="510c7-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="510c7-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="510c7-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="510c7-132">légèrement</span><span class="sxs-lookup"><span data-stu-id="510c7-132">bit</span></span></p></td>
<td><p><span data-ttu-id="510c7-133">True en cas de téléchargement sortant ; False en cas de téléchargement entrant (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="510c7-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="510c7-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="510c7-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="510c7-135">bit, non null</span><span class="sxs-lookup"><span data-stu-id="510c7-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="510c7-p102">True si le jeton est épinglé. Cela permet de garder le jeton dans la table jusqu’à ce que le service de conformité puisse y récupérer les champs appropriés.</span><span class="sxs-lookup"><span data-stu-id="510c7-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="510c7-138">Keys</span><span class="sxs-lookup"><span data-stu-id="510c7-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="510c7-139">Colonne</span><span class="sxs-lookup"><span data-stu-id="510c7-139">Column</span></span></th>
<th><span data-ttu-id="510c7-140">Description</span><span class="sxs-lookup"><span data-stu-id="510c7-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="510c7-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="510c7-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="510c7-142">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="510c7-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="510c7-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="510c7-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="510c7-144">Clé étrangère avec recherche dans la table tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="510c7-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

