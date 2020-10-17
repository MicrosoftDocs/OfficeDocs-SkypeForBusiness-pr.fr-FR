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
ms.openlocfilehash: 162676768c3cb358db436dc2ba40ce378a31ba6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509451"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="5f7de-102">tblComplianceData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f7de-102">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f7de-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5f7de-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5f7de-104">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des traducteurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="5f7de-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="5f7de-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="5f7de-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7de-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="5f7de-106">Column</span></span></th>
<th><span data-ttu-id="5f7de-107">Type</span><span class="sxs-lookup"><span data-stu-id="5f7de-107">Type</span></span></th>
<th><span data-ttu-id="5f7de-108">Description</span><span class="sxs-lookup"><span data-stu-id="5f7de-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7de-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="5f7de-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="5f7de-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="5f7de-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5f7de-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="5f7de-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7de-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="5f7de-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="5f7de-113">smalldatetime, non null</span><span class="sxs-lookup"><span data-stu-id="5f7de-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="5f7de-114">Moment de l’insertion (peut être éloigné dans le futur pour cmplType=9, car l’entrée est juste un espace réservé dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="5f7de-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f7de-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="5f7de-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="5f7de-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="5f7de-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f7de-117">Type d’événement de conformité :</span><span class="sxs-lookup"><span data-stu-id="5f7de-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="5f7de-118">1: Conversation</span><span class="sxs-lookup"><span data-stu-id="5f7de-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="5f7de-119">2: Sauvegarde de conversation</span><span class="sxs-lookup"><span data-stu-id="5f7de-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="5f7de-120">3: Téléchargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="5f7de-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="5f7de-121">4: Chargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="5f7de-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="5f7de-122">9: Transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="5f7de-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="5f7de-123">10: Suppression de conversation (avec remplacement)</span><span class="sxs-lookup"><span data-stu-id="5f7de-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="5f7de-124">11: Purge des conversations</span><span class="sxs-lookup"><span data-stu-id="5f7de-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7de-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="5f7de-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="5f7de-126">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="5f7de-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5f7de-127">Horodatage pour l’événement.</span><span class="sxs-lookup"><span data-stu-id="5f7de-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f7de-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="5f7de-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="5f7de-129">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="5f7de-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5f7de-130">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="5f7de-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7de-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="5f7de-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="5f7de-132">comportant</span><span class="sxs-lookup"><span data-stu-id="5f7de-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="5f7de-133">ID de conversation (correspondant à la table tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="5f7de-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f7de-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="5f7de-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="5f7de-135">int, non null</span><span class="sxs-lookup"><span data-stu-id="5f7de-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f7de-136">ID principal de l’affiche (correspondant à la table tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="5f7de-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7de-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="5f7de-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="5f7de-138">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="5f7de-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5f7de-139">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5f7de-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f7de-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="5f7de-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="5f7de-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5f7de-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="5f7de-142">Message (le codage dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="5f7de-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5f7de-143">Clé</span><span class="sxs-lookup"><span data-stu-id="5f7de-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7de-144">Colonne</span><span class="sxs-lookup"><span data-stu-id="5f7de-144">Column</span></span></th>
<th><span data-ttu-id="5f7de-145">Description</span><span class="sxs-lookup"><span data-stu-id="5f7de-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7de-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="5f7de-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="5f7de-147">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5f7de-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

