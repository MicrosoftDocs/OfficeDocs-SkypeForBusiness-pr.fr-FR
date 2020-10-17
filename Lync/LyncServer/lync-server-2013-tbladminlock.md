---
title: 'Lync Server 2013 : tblAdminLock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 608dcc5d8044b5e1dd62166bfd13124013b3979f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509521"
---
# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="4444b-102">tblAdminLock dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4444b-102">tblAdminLock in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4444b-103">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="4444b-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="4444b-104">tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.</span><span class="sxs-lookup"><span data-stu-id="4444b-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="4444b-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="4444b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4444b-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="4444b-106">Column</span></span></th>
<th><span data-ttu-id="4444b-107">Type</span><span class="sxs-lookup"><span data-stu-id="4444b-107">Type</span></span></th>
<th><span data-ttu-id="4444b-108">Description</span><span class="sxs-lookup"><span data-stu-id="4444b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4444b-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="4444b-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="4444b-110">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="4444b-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="4444b-p101">Date et heure d’expiration du verrou. Le propriétaire peut étendre cette valeur de manière périodique.</span><span class="sxs-lookup"><span data-stu-id="4444b-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4444b-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="4444b-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="4444b-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="4444b-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4444b-115">ID du serveur qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="4444b-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4444b-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="4444b-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="4444b-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="4444b-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4444b-118">ID du principal qui détient le verrou.</span><span class="sxs-lookup"><span data-stu-id="4444b-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

