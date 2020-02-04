---
title: 'Lync Server 2013 : Table FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="06e88-102">Table FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06e88-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06e88-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="06e88-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="06e88-104">Chaque enregistrement représente une session de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="06e88-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06e88-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="06e88-105">Column</span></span></th>
<th><span data-ttu-id="06e88-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="06e88-106">Data Type</span></span></th>
<th><span data-ttu-id="06e88-107">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="06e88-107">Key/Index</span></span></th>
<th><span data-ttu-id="06e88-108">Détails</span><span class="sxs-lookup"><span data-stu-id="06e88-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06e88-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="06e88-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="06e88-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="06e88-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="06e88-111">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="06e88-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="06e88-112">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="06e88-112">Time of session request.</span></span> <span data-ttu-id="06e88-113">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="06e88-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="06e88-114">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="06e88-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06e88-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="06e88-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="06e88-116">int</span><span class="sxs-lookup"><span data-stu-id="06e88-116">int</span></span></p></td>
<td><p><span data-ttu-id="06e88-117">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="06e88-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="06e88-118">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="06e88-118">ID number to identify the session.</span></span> <span data-ttu-id="06e88-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="06e88-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="06e88-120">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="06e88-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06e88-121"><strong>Nom de fichier</strong></span><span class="sxs-lookup"><span data-stu-id="06e88-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="06e88-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06e88-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06e88-123">Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="06e88-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06e88-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="06e88-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="06e88-125">identificateur</span><span class="sxs-lookup"><span data-stu-id="06e88-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06e88-126">Identificateur unique permettant de faire la distinction entre les transferts de fichiers impliquant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="06e88-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06e88-127"><strong>Sans</strong></span><span class="sxs-lookup"><span data-stu-id="06e88-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="06e88-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="06e88-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="06e88-129">Principal</span><span class="sxs-lookup"><span data-stu-id="06e88-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="06e88-130">Permet de détecter chaque message de suivi associé à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="06e88-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06e88-131"><strong>Valide</strong></span><span class="sxs-lookup"><span data-stu-id="06e88-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="06e88-132">bit</span><span class="sxs-lookup"><span data-stu-id="06e88-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06e88-133">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="06e88-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="06e88-134">Si vrai, l’argument refuser et annuler est nul.</span><span class="sxs-lookup"><span data-stu-id="06e88-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06e88-135"><strong>Rejeter</strong></span><span class="sxs-lookup"><span data-stu-id="06e88-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="06e88-136">bit</span><span class="sxs-lookup"><span data-stu-id="06e88-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06e88-137">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="06e88-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="06e88-138">Si vrai, l’argument accepter et annuler est nul.</span><span class="sxs-lookup"><span data-stu-id="06e88-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06e88-139"><strong>Annuler</strong></span><span class="sxs-lookup"><span data-stu-id="06e88-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="06e88-140">bit</span><span class="sxs-lookup"><span data-stu-id="06e88-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06e88-141">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="06e88-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="06e88-142">Si vrai, l’argument accepter et refuser est nul.</span><span class="sxs-lookup"><span data-stu-id="06e88-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

