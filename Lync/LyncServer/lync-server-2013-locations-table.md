---
title: 'Lync Server 2013 : table locations'
description: 'Lync Server 2013 : table locations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570580"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="62238-103">Table locations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62238-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62238-104">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="62238-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="62238-105">Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple un appel E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="62238-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62238-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="62238-106">Column</span></span></th>
<th><span data-ttu-id="62238-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="62238-107">Data Type</span></span></th>
<th><span data-ttu-id="62238-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="62238-108">Key/Index</span></span></th>
<th><span data-ttu-id="62238-109">Détails</span><span class="sxs-lookup"><span data-stu-id="62238-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62238-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="62238-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="62238-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="62238-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="62238-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="62238-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="62238-113">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="62238-113">Time of session request.</span></span> <span data-ttu-id="62238-114">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="62238-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="62238-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62238-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62238-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="62238-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="62238-117">int</span><span class="sxs-lookup"><span data-stu-id="62238-117">int</span></span></p></td>
<td><p><span data-ttu-id="62238-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="62238-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="62238-119">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="62238-119">ID number to identify the session.</span></span> <span data-ttu-id="62238-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="62238-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="62238-121">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62238-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62238-122"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="62238-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="62238-123">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="62238-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62238-124">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="62238-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

