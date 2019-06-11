---
title: 'Lync Server 2013 : tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="ea7c3-102">tblRoleType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea7c3-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea7c3-103">_**Dernière modification de la rubrique:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="ea7c3-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="ea7c3-104">tblRoleType est une table de recherche statique avec les types de rôles et leurs jeux d’autorisations associés.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="ea7c3-105">Celles</span><span class="sxs-lookup"><span data-stu-id="ea7c3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea7c3-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="ea7c3-106">Column</span></span></th>
<th><span data-ttu-id="ea7c3-107">Type</span><span class="sxs-lookup"><span data-stu-id="ea7c3-107">Type</span></span></th>
<th><span data-ttu-id="ea7c3-108">Description</span><span class="sxs-lookup"><span data-stu-id="ea7c3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea7c3-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ea7c3-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="ea7c3-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="ea7c3-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ea7c3-111">ID du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea7c3-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="ea7c3-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="ea7c3-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="ea7c3-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ea7c3-114">Description du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-114">Role type description.</span></span> <span data-ttu-id="ea7c3-115">Il existe quatre rôles disponibles:</span><span class="sxs-lookup"><span data-stu-id="ea7c3-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea7c3-116">Membre: membres de salle de conversation</span><span class="sxs-lookup"><span data-stu-id="ea7c3-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-117">Manager: gestionnaire de salle de conversation</span><span class="sxs-lookup"><span data-stu-id="ea7c3-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-118">Voix: présentateur pour une salle de conversation Auditorium</span><span class="sxs-lookup"><span data-stu-id="ea7c3-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-119">Créateur: peut créer des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="ea7c3-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea7c3-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="ea7c3-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="ea7c3-121">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="ea7c3-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="ea7c3-122">Autorisation définie pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-122">Permission set for the role.</span></span> <span data-ttu-id="ea7c3-123">Les bits utilisés sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="ea7c3-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea7c3-124">2: true si le rôle peut gérer des nœuds.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-125">4: true si le rôle peut créer des nœuds enfants.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-126">7: true si le rôle peut rejoindre une salle de conversation (ou des salles de conversation enfant d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="ea7c3-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-127">8: true si le rôle peut discuter dans une salle de conversation (ou dans des salles de conversation enfant d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="ea7c3-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-128">10: true si le rôle peut lire l’historique des conversations même en l’absence de participation à une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-129">11: true si le rôle peut voir la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="ea7c3-130">(Cette valeur est améliorée par des facteurs tels que Scope et Visibility.)</span><span class="sxs-lookup"><span data-stu-id="ea7c3-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-131">12: true si le rôle peut discuter dans une salle de conversation Auditorium.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="ea7c3-132">13: true si le rôle peut ignorer les règles de visibilité lors de la consultation des nœuds.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="ea7c3-133">Clé</span><span class="sxs-lookup"><span data-stu-id="ea7c3-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea7c3-134">Colonne</span><span class="sxs-lookup"><span data-stu-id="ea7c3-134">Column</span></span></th>
<th><span data-ttu-id="ea7c3-135">Description</span><span class="sxs-lookup"><span data-stu-id="ea7c3-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea7c3-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ea7c3-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="ea7c3-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ea7c3-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

