---
title: 'Lync Server 2013 : tblLastInviteId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 702c754830a34a445b11da394fc15add20ab4b0b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="366d1-102">tblLastInviteId dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="366d1-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="366d1-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="366d1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="366d1-104">La table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="366d1-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="366d1-105">Columns</span><span class="sxs-lookup"><span data-stu-id="366d1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="366d1-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="366d1-106">Column</span></span></th>
<th><span data-ttu-id="366d1-107">Type</span><span class="sxs-lookup"><span data-stu-id="366d1-107">Type</span></span></th>
<th><span data-ttu-id="366d1-108">Description</span><span class="sxs-lookup"><span data-stu-id="366d1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="366d1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="366d1-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="366d1-110">entier, non null</span><span class="sxs-lookup"><span data-stu-id="366d1-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="366d1-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="366d1-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="366d1-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="366d1-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="366d1-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="366d1-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="366d1-114">ID d’invitation le plus récemment utilisé.</span><span class="sxs-lookup"><span data-stu-id="366d1-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="366d1-115">Keys</span><span class="sxs-lookup"><span data-stu-id="366d1-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="366d1-116">Colonne</span><span class="sxs-lookup"><span data-stu-id="366d1-116">Column</span></span></th>
<th><span data-ttu-id="366d1-117">Description</span><span class="sxs-lookup"><span data-stu-id="366d1-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="366d1-118">prinID</span><span class="sxs-lookup"><span data-stu-id="366d1-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="366d1-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="366d1-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="366d1-120">prinID</span><span class="sxs-lookup"><span data-stu-id="366d1-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="366d1-121">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="366d1-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="366d1-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="366d1-122">See Also</span></span>


[<span data-ttu-id="366d1-123">tblPrincipalInvites dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="366d1-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

