---
title: 'Lync Server 2013 : tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="62d52-102">tblComplianceParticipant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62d52-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62d52-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="62d52-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="62d52-104">tblComplianceParticipant contient les participants actuels par canal et par serveur.</span><span class="sxs-lookup"><span data-stu-id="62d52-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="62d52-105">Celles</span><span class="sxs-lookup"><span data-stu-id="62d52-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62d52-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="62d52-106">Column</span></span></th>
<th><span data-ttu-id="62d52-107">Type</span><span class="sxs-lookup"><span data-stu-id="62d52-107">Type</span></span></th>
<th><span data-ttu-id="62d52-108">Description</span><span class="sxs-lookup"><span data-stu-id="62d52-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62d52-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="62d52-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="62d52-110">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="62d52-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="62d52-111">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="62d52-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d52-112">userId</span><span class="sxs-lookup"><span data-stu-id="62d52-112">userId</span></span></p></td>
<td><p><span data-ttu-id="62d52-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="62d52-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="62d52-114">ID principal du participant (correspondant à la table tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="62d52-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d52-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="62d52-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="62d52-116">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="62d52-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="62d52-117">Date et heure de l’événement de jointure.</span><span class="sxs-lookup"><span data-stu-id="62d52-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d52-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="62d52-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="62d52-119">bigint</span><span class="sxs-lookup"><span data-stu-id="62d52-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="62d52-120">NULL si le participant reste connecté.</span><span class="sxs-lookup"><span data-stu-id="62d52-120">Null if participant is still joined.</span></span> <span data-ttu-id="62d52-121">Horodatage du canal quittant l’événement s’il n’a pas la valeur null.</span><span class="sxs-lookup"><span data-stu-id="62d52-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="62d52-122">Ces entrées sont finalement supprimées lorsque tous les traducteurs traitent l’événement.</span><span class="sxs-lookup"><span data-stu-id="62d52-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d52-123">userUri</span><span class="sxs-lookup"><span data-stu-id="62d52-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="62d52-124">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="62d52-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="62d52-125">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62d52-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d52-126">serverID</span><span class="sxs-lookup"><span data-stu-id="62d52-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="62d52-127">int</span><span class="sxs-lookup"><span data-stu-id="62d52-127">int</span></span></p></td>
<td><p><span data-ttu-id="62d52-128">Identité du serveur (comme dans la table tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="62d52-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d52-129">ID</span><span class="sxs-lookup"><span data-stu-id="62d52-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="62d52-130">bigint</span><span class="sxs-lookup"><span data-stu-id="62d52-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="62d52-131">Session du serveur.</span><span class="sxs-lookup"><span data-stu-id="62d52-131">Server session.</span></span> <span data-ttu-id="62d52-132">Il s’agit d’un nombre aléatoire généré chaque fois qu’un service de conversation démarre.</span><span class="sxs-lookup"><span data-stu-id="62d52-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="62d52-133">Il est utilisé pour différencier les sessions à des fins d’identification de participants orphelins.</span><span class="sxs-lookup"><span data-stu-id="62d52-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="62d52-134">Clé</span><span class="sxs-lookup"><span data-stu-id="62d52-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62d52-135">Colonne</span><span class="sxs-lookup"><span data-stu-id="62d52-135">Column</span></span></th>
<th><span data-ttu-id="62d52-136">Description</span><span class="sxs-lookup"><span data-stu-id="62d52-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62d52-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="62d52-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="62d52-138">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="62d52-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

