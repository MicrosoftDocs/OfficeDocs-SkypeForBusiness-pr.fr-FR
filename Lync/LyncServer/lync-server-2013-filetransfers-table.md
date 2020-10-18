---
title: 'Lync Server 2013 : table FileTransfers'
description: 'Lync Server 2013 : table FileTransfers.'
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
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573360"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="68cf8-103">Table FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68cf8-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68cf8-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="68cf8-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="68cf8-105">Chaque enregistrement représente une session de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="68cf8-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68cf8-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="68cf8-106">Column</span></span></th>
<th><span data-ttu-id="68cf8-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="68cf8-107">Data Type</span></span></th>
<th><span data-ttu-id="68cf8-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="68cf8-108">Key/Index</span></span></th>
<th><span data-ttu-id="68cf8-109">Détails</span><span class="sxs-lookup"><span data-stu-id="68cf8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68cf8-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="68cf8-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68cf8-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="68cf8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="68cf8-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="68cf8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="68cf8-113">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="68cf8-113">Time of session request.</span></span> <span data-ttu-id="68cf8-114">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="68cf8-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="68cf8-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68cf8-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cf8-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="68cf8-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="68cf8-117">int</span><span class="sxs-lookup"><span data-stu-id="68cf8-117">int</span></span></p></td>
<td><p><span data-ttu-id="68cf8-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="68cf8-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="68cf8-119">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="68cf8-119">ID number to identify the session.</span></span> <span data-ttu-id="68cf8-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="68cf8-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="68cf8-121">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68cf8-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68cf8-122"><strong>Nom de fichier</strong></span><span class="sxs-lookup"><span data-stu-id="68cf8-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="68cf8-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68cf8-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68cf8-124">Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="68cf8-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cf8-125"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="68cf8-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="68cf8-126">unique</span><span class="sxs-lookup"><span data-stu-id="68cf8-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68cf8-127">Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="68cf8-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68cf8-128"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="68cf8-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="68cf8-129">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="68cf8-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="68cf8-130">Primaire</span><span class="sxs-lookup"><span data-stu-id="68cf8-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="68cf8-131">Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="68cf8-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cf8-132"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="68cf8-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="68cf8-133">légèrement</span><span class="sxs-lookup"><span data-stu-id="68cf8-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68cf8-p103">Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="68cf8-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68cf8-136"><strong>Rejeter</strong></span><span class="sxs-lookup"><span data-stu-id="68cf8-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="68cf8-137">légèrement</span><span class="sxs-lookup"><span data-stu-id="68cf8-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68cf8-p104">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="68cf8-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cf8-140"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="68cf8-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="68cf8-141">légèrement</span><span class="sxs-lookup"><span data-stu-id="68cf8-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68cf8-p105">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.</span><span class="sxs-lookup"><span data-stu-id="68cf8-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

