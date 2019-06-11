---
title: 'Lync Server 2013 : tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044a57645a8c49ea74ec4e003f9e12720d0b2268
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="c54cb-102">tblComplianceData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c54cb-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c54cb-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c54cb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c54cb-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par la carte de conformité.</span><span class="sxs-lookup"><span data-stu-id="c54cb-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="c54cb-105">Celles</span><span class="sxs-lookup"><span data-stu-id="c54cb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c54cb-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="c54cb-106">Column</span></span></th>
<th><span data-ttu-id="c54cb-107">Type</span><span class="sxs-lookup"><span data-stu-id="c54cb-107">Type</span></span></th>
<th><span data-ttu-id="c54cb-108">Description</span><span class="sxs-lookup"><span data-stu-id="c54cb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c54cb-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="c54cb-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="c54cb-110">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="c54cb-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="c54cb-111">ID de l’événement.</span><span class="sxs-lookup"><span data-stu-id="c54cb-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54cb-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="c54cb-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="c54cb-113">smalldatetime, pas null</span><span class="sxs-lookup"><span data-stu-id="c54cb-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="c54cb-114">Temps d’insertion (peut-être lointain dans le cas de cmplType = 9, car l’entrée n’est qu’un espace réservé dans le cas présent).</span><span class="sxs-lookup"><span data-stu-id="c54cb-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54cb-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="c54cb-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="c54cb-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="c54cb-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c54cb-117">Type d’événement de conformité:</span><span class="sxs-lookup"><span data-stu-id="c54cb-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="c54cb-118">1: conversation</span><span class="sxs-lookup"><span data-stu-id="c54cb-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="c54cb-119">2: discussions</span><span class="sxs-lookup"><span data-stu-id="c54cb-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="c54cb-120">3: Téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="c54cb-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="c54cb-121">4: Téléchargement de fichier</span><span class="sxs-lookup"><span data-stu-id="c54cb-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="c54cb-122">9: transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="c54cb-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="c54cb-123">10: suppression d’une discussion (avec remplacer)</span><span class="sxs-lookup"><span data-stu-id="c54cb-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="c54cb-124">11: suppression de conversation</span><span class="sxs-lookup"><span data-stu-id="c54cb-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54cb-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="c54cb-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="c54cb-126">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="c54cb-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="c54cb-127">Date et heure de l’événement.</span><span class="sxs-lookup"><span data-stu-id="c54cb-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54cb-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="c54cb-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="c54cb-129">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="c54cb-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="c54cb-130">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="c54cb-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54cb-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="c54cb-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="c54cb-132">bigint</span><span class="sxs-lookup"><span data-stu-id="c54cb-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="c54cb-133">ID de conversation (correspondant à la table tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="c54cb-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54cb-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="c54cb-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="c54cb-135">ent, non null</span><span class="sxs-lookup"><span data-stu-id="c54cb-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c54cb-136">ID principal de l’affiche (correspondant à la table tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="c54cb-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54cb-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="c54cb-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="c54cb-138">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="c54cb-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="c54cb-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c54cb-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54cb-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="c54cb-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="c54cb-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="c54cb-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="c54cb-142">Le message (Encoding dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="c54cb-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c54cb-143">Clé</span><span class="sxs-lookup"><span data-stu-id="c54cb-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c54cb-144">Colonne</span><span class="sxs-lookup"><span data-stu-id="c54cb-144">Column</span></span></th>
<th><span data-ttu-id="c54cb-145">Description</span><span class="sxs-lookup"><span data-stu-id="c54cb-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c54cb-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="c54cb-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="c54cb-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="c54cb-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

