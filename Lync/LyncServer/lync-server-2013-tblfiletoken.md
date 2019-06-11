---
title: 'Lync Server 2013 : tblFileToken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146c168e62bd0602a76cd77ab678c84ba5e44da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="d352d-102">tblFileToken dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d352d-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d352d-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d352d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d352d-104">tblFileToken contient des jetons temporaires aux fins de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d352d-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="d352d-105">Celles</span><span class="sxs-lookup"><span data-stu-id="d352d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d352d-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="d352d-106">Column</span></span></th>
<th><span data-ttu-id="d352d-107">Type</span><span class="sxs-lookup"><span data-stu-id="d352d-107">Type</span></span></th>
<th><span data-ttu-id="d352d-108">Description</span><span class="sxs-lookup"><span data-stu-id="d352d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d352d-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="d352d-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="d352d-110">nvarchar (50), pas null</span><span class="sxs-lookup"><span data-stu-id="d352d-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="d352d-111">Jeton unique (GUID).</span><span class="sxs-lookup"><span data-stu-id="d352d-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d352d-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="d352d-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="d352d-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="d352d-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d352d-114">ID du principal qui transfère le fichier.</span><span class="sxs-lookup"><span data-stu-id="d352d-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d352d-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="d352d-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="d352d-116">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="d352d-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="d352d-117">GUID du nœud de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d352d-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d352d-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="d352d-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="d352d-119">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="d352d-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="d352d-120">Durée d’expiration.</span><span class="sxs-lookup"><span data-stu-id="d352d-120">Expiration time.</span></span> <span data-ttu-id="d352d-121">(Les jetons expirent au bout de 30 minutes, sauf s’ils sont épinglés (voir les descriptions suivies dans cette colonne).</span><span class="sxs-lookup"><span data-stu-id="d352d-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d352d-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="d352d-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="d352d-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d352d-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d352d-124">URL du fichier transféré (pour une utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="d352d-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d352d-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="d352d-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="d352d-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d352d-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d352d-127">URL de la miniature du fichier transféré (pour une utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="d352d-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d352d-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="d352d-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="d352d-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="d352d-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="d352d-130">Horodatage de l’opération de transfert de fichiers réelle (pour l’utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="d352d-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d352d-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="d352d-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="d352d-132">bit</span><span class="sxs-lookup"><span data-stu-id="d352d-132">bit</span></span></p></td>
<td><p><span data-ttu-id="d352d-133">True si Télécharger; Faux si Télécharger (pour une utilisation du service de conformité).</span><span class="sxs-lookup"><span data-stu-id="d352d-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d352d-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="d352d-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="d352d-135">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="d352d-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d352d-136">True si le jeton est épinglé.</span><span class="sxs-lookup"><span data-stu-id="d352d-136">True if token is pinned.</span></span> <span data-ttu-id="d352d-137">Il est utilisé pour conserver le jeton dans le tableau jusqu’à ce que le service de conformité puisse récupérer les champs appropriés.</span><span class="sxs-lookup"><span data-stu-id="d352d-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d352d-138">Permettent</span><span class="sxs-lookup"><span data-stu-id="d352d-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d352d-139">Colonne</span><span class="sxs-lookup"><span data-stu-id="d352d-139">Column</span></span></th>
<th><span data-ttu-id="d352d-140">Description</span><span class="sxs-lookup"><span data-stu-id="d352d-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d352d-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="d352d-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="d352d-142">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d352d-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d352d-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="d352d-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="d352d-144">Clé étrangère avec recherche dans la table tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="d352d-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

