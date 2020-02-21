---
title: 'Lync Server 2013 : tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 721932aa2929930b3da742355a46c5e2066c5c83
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="88151-102">tblRoleType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88151-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88151-103">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="88151-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="88151-104">tblRoleType est une table de choix statique contenant des types de rôles et leurs jeux d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="88151-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="88151-105">Columns</span><span class="sxs-lookup"><span data-stu-id="88151-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88151-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="88151-106">Column</span></span></th>
<th><span data-ttu-id="88151-107">Type</span><span class="sxs-lookup"><span data-stu-id="88151-107">Type</span></span></th>
<th><span data-ttu-id="88151-108">Description</span><span class="sxs-lookup"><span data-stu-id="88151-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88151-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="88151-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="88151-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="88151-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="88151-111">ID de type de rôle.</span><span class="sxs-lookup"><span data-stu-id="88151-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88151-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="88151-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="88151-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="88151-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="88151-p101">Description de type de rôle. Les quatre rôles disponibles sont :</span><span class="sxs-lookup"><span data-stu-id="88151-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="88151-116">Membre : membre de la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="88151-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="88151-117">Responsable : responsable de la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="88151-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="88151-118">Membre sonore : présentateur de la salle de conversation de type auditorium</span><span class="sxs-lookup"><span data-stu-id="88151-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="88151-119">Créateur : peut créer des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="88151-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88151-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="88151-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="88151-121">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="88151-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="88151-p102">Définition de l’autorisation du rôle. Les bits utilisés sont :</span><span class="sxs-lookup"><span data-stu-id="88151-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="88151-124">2 : True si le rôle peut gérer des nœuds.</span><span class="sxs-lookup"><span data-stu-id="88151-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="88151-125">4 : True si le rôle peut créer des nœuds enfants.</span><span class="sxs-lookup"><span data-stu-id="88151-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="88151-126">7 : True si le rôle peut rejoindre une salle de conversation (ou les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="88151-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="88151-127">8 : True si le rôle peut converser dans une salle de conversation (ou les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="88151-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="88151-128">10 : True si le rôle peut lire l’historique d’une conversation même s’il n’a pas rejoint une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="88151-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="88151-p103">11 : True si le rôle peut voir la salle de conversation. (Les facteurs tels que l’étendue et la visibilité permettent d’affiner davantage).</span><span class="sxs-lookup"><span data-stu-id="88151-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="88151-131">12 : True si le rôle peut converser dans la salle de conversation de type auditorium.</span><span class="sxs-lookup"><span data-stu-id="88151-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="88151-132">13 : True si le rôle peut contourner les règles de visibilité lors de la visualisation des nœuds.</span><span class="sxs-lookup"><span data-stu-id="88151-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="88151-133">Clé</span><span class="sxs-lookup"><span data-stu-id="88151-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88151-134">Colonne</span><span class="sxs-lookup"><span data-stu-id="88151-134">Column</span></span></th>
<th><span data-ttu-id="88151-135">Description</span><span class="sxs-lookup"><span data-stu-id="88151-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88151-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="88151-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="88151-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="88151-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

