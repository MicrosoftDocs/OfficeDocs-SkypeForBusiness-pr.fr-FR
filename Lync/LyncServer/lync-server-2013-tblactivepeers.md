---
title: 'Lync Server 2013 : tblActivePeers'
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
ms.openlocfilehash: c49ddc7a1355e7108f1bcb9c13394dd3305190c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509551"
---
# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="39280-102">tblActivePeers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39280-102">tblActivePeers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39280-103">_**Dernière modification de la rubrique :** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="39280-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="39280-104">tblActivePeers contient les connexions d’égal à égal actuelles entre les services de conversation.</span><span class="sxs-lookup"><span data-stu-id="39280-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="39280-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="39280-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39280-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="39280-106">Column</span></span></th>
<th><span data-ttu-id="39280-107">Type</span><span class="sxs-lookup"><span data-stu-id="39280-107">Type</span></span></th>
<th><span data-ttu-id="39280-108">Description</span><span class="sxs-lookup"><span data-stu-id="39280-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39280-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="39280-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="39280-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="39280-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="39280-111">ID du serveur qui a publié l’entrée.</span><span class="sxs-lookup"><span data-stu-id="39280-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39280-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="39280-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="39280-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="39280-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="39280-114">ID de l’homologue auquel le serveur de publication est connecté.</span><span class="sxs-lookup"><span data-stu-id="39280-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="39280-115">Keys</span><span class="sxs-lookup"><span data-stu-id="39280-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39280-116">Colonne</span><span class="sxs-lookup"><span data-stu-id="39280-116">Column</span></span></th>
<th><span data-ttu-id="39280-117">Description</span><span class="sxs-lookup"><span data-stu-id="39280-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39280-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="39280-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="39280-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="39280-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39280-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="39280-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="39280-121">Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="39280-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39280-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="39280-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="39280-123">Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="39280-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

