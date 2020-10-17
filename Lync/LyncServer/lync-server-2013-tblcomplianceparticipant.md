---
title: 'Lync Server 2013 : tblComplianceParticipant'
description: 'Lync Server 2013 : tblComplianceParticipant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569070"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="93d10-103">tblComplianceParticipant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93d10-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93d10-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="93d10-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="93d10-105">tblComplianceParticipant contient les participants actifs, par canal et par serveur.</span><span class="sxs-lookup"><span data-stu-id="93d10-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="93d10-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="93d10-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93d10-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="93d10-107">Column</span></span></th>
<th><span data-ttu-id="93d10-108">Type</span><span class="sxs-lookup"><span data-stu-id="93d10-108">Type</span></span></th>
<th><span data-ttu-id="93d10-109">Description</span><span class="sxs-lookup"><span data-stu-id="93d10-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93d10-110">channelUri</span><span class="sxs-lookup"><span data-stu-id="93d10-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="93d10-111">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="93d10-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="93d10-112">URI (Uniform Resource Identifier) du canal.</span><span class="sxs-lookup"><span data-stu-id="93d10-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93d10-113">userId</span><span class="sxs-lookup"><span data-stu-id="93d10-113">userId</span></span></p></td>
<td><p><span data-ttu-id="93d10-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="93d10-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="93d10-115">ID Principal du participant (correspondant à la table tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="93d10-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93d10-116">joinedAt</span><span class="sxs-lookup"><span data-stu-id="93d10-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="93d10-117">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="93d10-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="93d10-118">Horodatage de l’événement qui se joint.</span><span class="sxs-lookup"><span data-stu-id="93d10-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93d10-119">partedAt</span><span class="sxs-lookup"><span data-stu-id="93d10-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="93d10-120">comportant</span><span class="sxs-lookup"><span data-stu-id="93d10-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="93d10-p101">Null si le participant est encore joint. Horodatage de l’événement qui quitte le canal s’il n’est pas null.</span><span class="sxs-lookup"><span data-stu-id="93d10-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="93d10-123">Ces entrées finissent par être supprimées lorsque tous les traducteurs traitent l’événement.</span><span class="sxs-lookup"><span data-stu-id="93d10-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93d10-124">userUri</span><span class="sxs-lookup"><span data-stu-id="93d10-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="93d10-125">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="93d10-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="93d10-126">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="93d10-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93d10-127">serverID</span><span class="sxs-lookup"><span data-stu-id="93d10-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="93d10-128">int</span><span class="sxs-lookup"><span data-stu-id="93d10-128">int</span></span></p></td>
<td><p><span data-ttu-id="93d10-129">Identité du serveur (comme dans tblServerIdentity.serverID table).</span><span class="sxs-lookup"><span data-stu-id="93d10-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93d10-130">Session</span><span class="sxs-lookup"><span data-stu-id="93d10-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="93d10-131">comportant</span><span class="sxs-lookup"><span data-stu-id="93d10-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="93d10-p102">Session du serveur. Il s’agit d’un nombre aléatoire généré chaque fois que le service de conversation démarre. Il sert à différencier les sessions dans le but d’identifier les participants orphelins.</span><span class="sxs-lookup"><span data-stu-id="93d10-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="93d10-135">Clé</span><span class="sxs-lookup"><span data-stu-id="93d10-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93d10-136">Colonne</span><span class="sxs-lookup"><span data-stu-id="93d10-136">Column</span></span></th>
<th><span data-ttu-id="93d10-137">Description</span><span class="sxs-lookup"><span data-stu-id="93d10-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93d10-138">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="93d10-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="93d10-139">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="93d10-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

