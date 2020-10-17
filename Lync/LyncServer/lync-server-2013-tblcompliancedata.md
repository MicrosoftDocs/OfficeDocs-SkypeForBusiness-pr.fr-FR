---
title: 'Lync Server 2013 : tblComplianceData'
description: 'Lync Server 2013 : tblComplianceData.'
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
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568100"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="95d21-103">tblComplianceData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95d21-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95d21-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="95d21-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="95d21-105">tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des traducteurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="95d21-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="95d21-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="95d21-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95d21-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="95d21-107">Column</span></span></th>
<th><span data-ttu-id="95d21-108">Type</span><span class="sxs-lookup"><span data-stu-id="95d21-108">Type</span></span></th>
<th><span data-ttu-id="95d21-109">Description</span><span class="sxs-lookup"><span data-stu-id="95d21-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95d21-110">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="95d21-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="95d21-111">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="95d21-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="95d21-112">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="95d21-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95d21-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="95d21-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="95d21-114">smalldatetime, non null</span><span class="sxs-lookup"><span data-stu-id="95d21-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="95d21-115">Moment de l’insertion (peut être éloigné dans le futur pour cmplType=9, car l’entrée est juste un espace réservé dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="95d21-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95d21-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="95d21-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="95d21-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="95d21-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="95d21-118">Type d’événement de conformité :</span><span class="sxs-lookup"><span data-stu-id="95d21-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="95d21-119">1: Conversation</span><span class="sxs-lookup"><span data-stu-id="95d21-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="95d21-120">2: Sauvegarde de conversation</span><span class="sxs-lookup"><span data-stu-id="95d21-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="95d21-121">3: Téléchargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="95d21-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="95d21-122">4: Chargement de fichiers</span><span class="sxs-lookup"><span data-stu-id="95d21-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="95d21-123">9: Transfert de fichier provisoire</span><span class="sxs-lookup"><span data-stu-id="95d21-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="95d21-124">10: Suppression de conversation (avec remplacement)</span><span class="sxs-lookup"><span data-stu-id="95d21-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="95d21-125">11: Purge des conversations</span><span class="sxs-lookup"><span data-stu-id="95d21-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95d21-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="95d21-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="95d21-127">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="95d21-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="95d21-128">Horodatage pour l’événement.</span><span class="sxs-lookup"><span data-stu-id="95d21-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95d21-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="95d21-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="95d21-130">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="95d21-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="95d21-131">URI (Uniform Resource Identifier) de canal.</span><span class="sxs-lookup"><span data-stu-id="95d21-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95d21-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="95d21-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="95d21-133">comportant</span><span class="sxs-lookup"><span data-stu-id="95d21-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="95d21-134">ID de conversation (correspondant à la table tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="95d21-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95d21-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="95d21-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="95d21-136">int, non null</span><span class="sxs-lookup"><span data-stu-id="95d21-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="95d21-137">ID principal de l’affiche (correspondant à la table tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="95d21-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95d21-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="95d21-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="95d21-139">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="95d21-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="95d21-140">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="95d21-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95d21-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="95d21-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="95d21-142">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="95d21-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="95d21-143">Message (le codage dépend de cmplType).</span><span class="sxs-lookup"><span data-stu-id="95d21-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="95d21-144">Clé</span><span class="sxs-lookup"><span data-stu-id="95d21-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95d21-145">Colonne</span><span class="sxs-lookup"><span data-stu-id="95d21-145">Column</span></span></th>
<th><span data-ttu-id="95d21-146">Description</span><span class="sxs-lookup"><span data-stu-id="95d21-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95d21-147">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="95d21-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="95d21-148">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="95d21-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

