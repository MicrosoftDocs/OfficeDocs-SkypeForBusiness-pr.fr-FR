---
title: 'Lync Server 2013 : tblComplianceData'
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
ms.openlocfilehash: 03f5a65b11c610849c5b9d031f24d236dcbcf332
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="4f1b6-102">tblComplianceData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f1b6-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f1b6-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4f1b6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4f1b6-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des traducteurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="4f1b6-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="4f1b6-105">Columns</span><span class="sxs-lookup"><span data-stu-id="4f1b6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f1b6-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="4f1b6-106">Column</span></span></th>
<th><span data-ttu-id="4f1b6-107">Type</span><span class="sxs-lookup"><span data-stu-id="4f1b6-107">Type</span></span></th>
<th><span data-ttu-id="4f1b6-108">Description</span><span class="sxs-lookup"><span data-stu-id="4f1b6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f1b6-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="4f1b6-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="4f1b6-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="4f1b6-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1b6-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="4f1b6-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-113">smalldatetime, non null</span><span class="sxs-lookup"><span data-stu-id="4f1b6-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-114">Moment de l’insertion (peut être éloigné dans le futur pour cmplType=9, car l’entrée est juste un espace réservé dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="4f1b6-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1b6-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="4f1b6-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="4f1b6-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-117">Type d’événement de conformité :</span><span class="sxs-lookup"><span data-stu-id="4f1b6-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f1b6-118">1: Conversation</span><span class="sxs-lookup"><span data-stu-id="4f1b6-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="4f1b6-119">2: Sauvegarde de conversation</span><span class="sxs-lookup"><span data-stu-id="4f1b6-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="4f1b6-120">3: Téléchargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="4f1b6-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="4f1b6-121">4: Chargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="4f1b6-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="4f1b6-122">9: Transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="4f1b6-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="4f1b6-123">10: Suppression de conversation (avec remplacement)</span><span class="sxs-lookup"><span data-stu-id="4f1b6-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="4f1b6-124">11: Purge des conversations</span><span class="sxs-lookup"><span data-stu-id="4f1b6-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1b6-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="4f1b6-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-126">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="4f1b6-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-127">Horodatage pour l’événement.</span><span class="sxs-lookup"><span data-stu-id="4f1b6-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1b6-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="4f1b6-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-129">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="4f1b6-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-130">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="4f1b6-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1b6-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="4f1b6-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-132">comportant</span><span class="sxs-lookup"><span data-stu-id="4f1b6-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-133">ID de conversation (correspondant à la table tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="4f1b6-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1b6-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="4f1b6-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-135">int, non null</span><span class="sxs-lookup"><span data-stu-id="4f1b6-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-136">ID principal de l’affiche (correspondant à la table tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="4f1b6-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1b6-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="4f1b6-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-138">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="4f1b6-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f1b6-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1b6-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="4f1b6-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="4f1b6-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-142">Message (le codage dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="4f1b6-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4f1b6-143">Clé</span><span class="sxs-lookup"><span data-stu-id="4f1b6-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f1b6-144">Colonne</span><span class="sxs-lookup"><span data-stu-id="4f1b6-144">Column</span></span></th>
<th><span data-ttu-id="4f1b6-145">Description</span><span class="sxs-lookup"><span data-stu-id="4f1b6-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f1b6-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="4f1b6-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="4f1b6-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="4f1b6-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

