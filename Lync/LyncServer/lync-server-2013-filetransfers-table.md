---
title: 'Lync Server 2013 : table FileTransfers'
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
ms.openlocfilehash: 33dbfdc6d7b0c8317b0f6ec56f837023398c0696
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="4ad72-102">Table FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad72-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ad72-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4ad72-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4ad72-104">Chaque enregistrement représente une session de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="4ad72-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ad72-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="4ad72-105">Column</span></span></th>
<th><span data-ttu-id="4ad72-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="4ad72-106">Data Type</span></span></th>
<th><span data-ttu-id="4ad72-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="4ad72-107">Key/Index</span></span></th>
<th><span data-ttu-id="4ad72-108">Détails</span><span class="sxs-lookup"><span data-stu-id="4ad72-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ad72-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ad72-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ad72-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="4ad72-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ad72-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="4ad72-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ad72-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="4ad72-112">Time of session request.</span></span> <span data-ttu-id="4ad72-113">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="4ad72-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4ad72-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ad72-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ad72-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4ad72-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4ad72-116">int</span><span class="sxs-lookup"><span data-stu-id="4ad72-116">int</span></span></p></td>
<td><p><span data-ttu-id="4ad72-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="4ad72-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ad72-118">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="4ad72-118">ID number to identify the session.</span></span> <span data-ttu-id="4ad72-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="4ad72-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4ad72-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ad72-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ad72-121"><strong>Nom de fichier</strong></span><span class="sxs-lookup"><span data-stu-id="4ad72-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="4ad72-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ad72-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ad72-123">Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="4ad72-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ad72-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="4ad72-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="4ad72-125">unique</span><span class="sxs-lookup"><span data-stu-id="4ad72-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ad72-126">Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="4ad72-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ad72-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="4ad72-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="4ad72-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4ad72-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4ad72-129">Primaire</span><span class="sxs-lookup"><span data-stu-id="4ad72-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="4ad72-130">Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="4ad72-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ad72-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="4ad72-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="4ad72-132">légèrement</span><span class="sxs-lookup"><span data-stu-id="4ad72-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ad72-p103">Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="4ad72-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ad72-135"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="4ad72-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="4ad72-136">légèrement</span><span class="sxs-lookup"><span data-stu-id="4ad72-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ad72-p104">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="4ad72-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ad72-139"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="4ad72-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="4ad72-140">légèrement</span><span class="sxs-lookup"><span data-stu-id="4ad72-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ad72-p105">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.</span><span class="sxs-lookup"><span data-stu-id="4ad72-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

