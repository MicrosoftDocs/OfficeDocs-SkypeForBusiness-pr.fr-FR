---
title: 'Lync Server 2013 : tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="1404a-102">tblLastChatId dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1404a-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1404a-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1404a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1404a-104">tblLastChatId contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1404a-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="1404a-105">Celles</span><span class="sxs-lookup"><span data-stu-id="1404a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1404a-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="1404a-106">Column</span></span></th>
<th><span data-ttu-id="1404a-107">Type</span><span class="sxs-lookup"><span data-stu-id="1404a-107">Type</span></span></th>
<th><span data-ttu-id="1404a-108">Description</span><span class="sxs-lookup"><span data-stu-id="1404a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1404a-109">ID</span><span class="sxs-lookup"><span data-stu-id="1404a-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1404a-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="1404a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1404a-111">ID de nœud (salle de conversation-type uniquement).</span><span class="sxs-lookup"><span data-stu-id="1404a-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1404a-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="1404a-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="1404a-113">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="1404a-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1404a-114">Dernier ID de conversation utilisé.</span><span class="sxs-lookup"><span data-stu-id="1404a-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1404a-115">Permettent</span><span class="sxs-lookup"><span data-stu-id="1404a-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1404a-116">Colonne</span><span class="sxs-lookup"><span data-stu-id="1404a-116">Column</span></span></th>
<th><span data-ttu-id="1404a-117">Description</span><span class="sxs-lookup"><span data-stu-id="1404a-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1404a-118">&lt;nodeID, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="1404a-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="1404a-119">Clé primaire (uniquement nodeID est suffisante pour le traitement).</span><span class="sxs-lookup"><span data-stu-id="1404a-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1404a-120">ID</span><span class="sxs-lookup"><span data-stu-id="1404a-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1404a-121">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="1404a-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="1404a-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1404a-122">See Also</span></span>


[<span data-ttu-id="1404a-123">tblChat dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1404a-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

