---
title: 'Lync Server 2013 : tblActivePeers'
description: 'Lync Server 2013 : tblActivePeers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f274f82a280883e38e8e02409305982b64c18e4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573740"
---
# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="bf882-103">tblActivePeers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf882-103">tblActivePeers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf882-104">_**Dernière modification de la rubrique :** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="bf882-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="bf882-105">tblActivePeers contient les connexions d’égal à égal actuelles entre les services de conversation.</span><span class="sxs-lookup"><span data-stu-id="bf882-105">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="bf882-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="bf882-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf882-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="bf882-107">Column</span></span></th>
<th><span data-ttu-id="bf882-108">Type</span><span class="sxs-lookup"><span data-stu-id="bf882-108">Type</span></span></th>
<th><span data-ttu-id="bf882-109">Description</span><span class="sxs-lookup"><span data-stu-id="bf882-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf882-110">aplServerID</span><span class="sxs-lookup"><span data-stu-id="bf882-110">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="bf882-111">int, non null</span><span class="sxs-lookup"><span data-stu-id="bf882-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bf882-112">ID du serveur qui a publié l’entrée.</span><span class="sxs-lookup"><span data-stu-id="bf882-112">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf882-113">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="bf882-113">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="bf882-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="bf882-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bf882-115">ID de l’homologue auquel le serveur de publication est connecté.</span><span class="sxs-lookup"><span data-stu-id="bf882-115">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bf882-116">Keys</span><span class="sxs-lookup"><span data-stu-id="bf882-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf882-117">Colonne</span><span class="sxs-lookup"><span data-stu-id="bf882-117">Column</span></span></th>
<th><span data-ttu-id="bf882-118">Description</span><span class="sxs-lookup"><span data-stu-id="bf882-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf882-119">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="bf882-119">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="bf882-120">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="bf882-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf882-121">aplServerID</span><span class="sxs-lookup"><span data-stu-id="bf882-121">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="bf882-122">Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="bf882-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf882-123">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="bf882-123">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="bf882-124">Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="bf882-124">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

