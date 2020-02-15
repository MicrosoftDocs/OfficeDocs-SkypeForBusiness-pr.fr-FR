---
title: 'Lync Server 2013 : table de médiane'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fe16e903a1dfbc958336dca68903ca80770995d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="d90ca-102">Table médial dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d90ca-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d90ca-103">_**Dernière modification de la rubrique :** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="d90ca-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="d90ca-104">La table MediaList est une table statique qui stocke la liste de divers types de médias.</span><span class="sxs-lookup"><span data-stu-id="d90ca-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d90ca-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="d90ca-105">Column</span></span></th>
<th><span data-ttu-id="d90ca-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="d90ca-106">Data Type</span></span></th>
<th><span data-ttu-id="d90ca-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="d90ca-107">Key/Index</span></span></th>
<th><span data-ttu-id="d90ca-108">Détails</span><span class="sxs-lookup"><span data-stu-id="d90ca-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d90ca-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="d90ca-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="d90ca-110">entier très petit</span><span class="sxs-lookup"><span data-stu-id="d90ca-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d90ca-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="d90ca-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="d90ca-112">Valeurs : 1-7</span><span class="sxs-lookup"><span data-stu-id="d90ca-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d90ca-113"><strong>Support</strong></span><span class="sxs-lookup"><span data-stu-id="d90ca-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="d90ca-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d90ca-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d90ca-115">Mappage statique des valeurs MediaID et multimédias :</span><span class="sxs-lookup"><span data-stu-id="d90ca-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d90ca-116">1 – MESSAGERIE INSTANTANÉE</span><span class="sxs-lookup"><span data-stu-id="d90ca-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="d90ca-117">2 – Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="d90ca-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="d90ca-118">3 – Assistance à distance</span><span class="sxs-lookup"><span data-stu-id="d90ca-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="d90ca-119">4 – Partage d’application</span><span class="sxs-lookup"><span data-stu-id="d90ca-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="d90ca-120">5 – audio</span><span class="sxs-lookup"><span data-stu-id="d90ca-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="d90ca-121">6 – vidéo</span><span class="sxs-lookup"><span data-stu-id="d90ca-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="d90ca-122">7 – Invitation d’application</span><span class="sxs-lookup"><span data-stu-id="d90ca-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d90ca-123">Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR. SessionDetailsView. MediaTypes, vous devez utiliser l’extrait de code de jointure suivant :</span><span class="sxs-lookup"><span data-stu-id="d90ca-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

