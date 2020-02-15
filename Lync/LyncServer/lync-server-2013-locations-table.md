---
title: 'Lync Server 2013 : table locations'
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
ms.openlocfilehash: accab39d1f1f7cb1855ba651ea217aa3b0a4bd8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="d216e-102">Table locations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d216e-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d216e-103">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="d216e-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="d216e-104">Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple un appel E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d216e-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d216e-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="d216e-105">Column</span></span></th>
<th><span data-ttu-id="d216e-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="d216e-106">Data Type</span></span></th>
<th><span data-ttu-id="d216e-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="d216e-107">Key/Index</span></span></th>
<th><span data-ttu-id="d216e-108">Détails</span><span class="sxs-lookup"><span data-stu-id="d216e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d216e-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d216e-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d216e-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d216e-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d216e-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="d216e-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d216e-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="d216e-112">Time of session request.</span></span> <span data-ttu-id="d216e-113">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="d216e-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d216e-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d216e-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d216e-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d216e-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d216e-116">int</span><span class="sxs-lookup"><span data-stu-id="d216e-116">int</span></span></p></td>
<td><p><span data-ttu-id="d216e-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="d216e-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d216e-118">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="d216e-118">ID number to identify the session.</span></span> <span data-ttu-id="d216e-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="d216e-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d216e-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d216e-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d216e-121"><strong>Emplacement</strong></span><span class="sxs-lookup"><span data-stu-id="d216e-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="d216e-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="d216e-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d216e-123">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="d216e-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

