---
title: 'Lync Server 2013 : tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="5fd58-102">tblComplianceData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fd58-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fd58-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5fd58-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5fd58-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.</span><span class="sxs-lookup"><span data-stu-id="5fd58-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="5fd58-105">Celles</span><span class="sxs-lookup"><span data-stu-id="5fd58-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fd58-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="5fd58-106">Column</span></span></th>
<th><span data-ttu-id="5fd58-107">Type</span><span class="sxs-lookup"><span data-stu-id="5fd58-107">Type</span></span></th>
<th><span data-ttu-id="5fd58-108">Description</span><span class="sxs-lookup"><span data-stu-id="5fd58-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fd58-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="5fd58-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="5fd58-110">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="5fd58-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5fd58-111">ID de l’événement.</span><span class="sxs-lookup"><span data-stu-id="5fd58-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fd58-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="5fd58-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="5fd58-113">smalldatetime, pas null</span><span class="sxs-lookup"><span data-stu-id="5fd58-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="5fd58-114">Temps d’insertion (peut-être lointain dans le cas de cmplType = 9, car l’entrée n’est qu’un espace réservé dans le cas présent).</span><span class="sxs-lookup"><span data-stu-id="5fd58-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fd58-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="5fd58-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="5fd58-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="5fd58-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fd58-117">Type d’événement de conformité :</span><span class="sxs-lookup"><span data-stu-id="5fd58-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="5fd58-118">1 : conversation</span><span class="sxs-lookup"><span data-stu-id="5fd58-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="5fd58-119">2 : discussions</span><span class="sxs-lookup"><span data-stu-id="5fd58-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="5fd58-120">3 : Téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="5fd58-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="5fd58-121">4 : Téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="5fd58-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="5fd58-122">9 : transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="5fd58-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="5fd58-123">10 : suppression d’une discussion (avec remplacer)</span><span class="sxs-lookup"><span data-stu-id="5fd58-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="5fd58-124">11 : suppression de conversation</span><span class="sxs-lookup"><span data-stu-id="5fd58-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fd58-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="5fd58-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="5fd58-126">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="5fd58-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5fd58-127">Date et heure de l’événement.</span><span class="sxs-lookup"><span data-stu-id="5fd58-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fd58-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="5fd58-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="5fd58-129">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="5fd58-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5fd58-130">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="5fd58-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fd58-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="5fd58-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="5fd58-132">bigint</span><span class="sxs-lookup"><span data-stu-id="5fd58-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="5fd58-133">ID de conversation (correspondant à la table tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="5fd58-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fd58-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="5fd58-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="5fd58-135">ent, non null</span><span class="sxs-lookup"><span data-stu-id="5fd58-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fd58-136">ID principal de l’affiche (correspondant à la table tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="5fd58-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fd58-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="5fd58-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="5fd58-138">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="5fd58-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5fd58-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5fd58-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fd58-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="5fd58-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="5fd58-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5fd58-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="5fd58-142">Le message (Encoding dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="5fd58-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5fd58-143">Clé</span><span class="sxs-lookup"><span data-stu-id="5fd58-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fd58-144">Colonne</span><span class="sxs-lookup"><span data-stu-id="5fd58-144">Column</span></span></th>
<th><span data-ttu-id="5fd58-145">Description</span><span class="sxs-lookup"><span data-stu-id="5fd58-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fd58-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="5fd58-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="5fd58-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5fd58-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

