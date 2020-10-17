---
title: 'Lync Server 2013 : table de médiane'
description: 'Lync Server 2013 : table de médiane.'
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
ms.openlocfilehash: 4e54535cd4a081657e7dcd59446cf65aaa3af7cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572070"
---
# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="e2d28-103">Table médial dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2d28-103">MediaList table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2d28-104">_**Dernière modification de la rubrique :** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="e2d28-104">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="e2d28-105">La table MediaList est une table statique qui stocke la liste de divers types de médias.</span><span class="sxs-lookup"><span data-stu-id="e2d28-105">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2d28-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="e2d28-106">Column</span></span></th>
<th><span data-ttu-id="e2d28-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="e2d28-107">Data Type</span></span></th>
<th><span data-ttu-id="e2d28-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="e2d28-108">Key/Index</span></span></th>
<th><span data-ttu-id="e2d28-109">Détails</span><span class="sxs-lookup"><span data-stu-id="e2d28-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2d28-110"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="e2d28-110"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d28-111">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e2d28-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e2d28-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="e2d28-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e2d28-113">Valeurs : 1-7</span><span class="sxs-lookup"><span data-stu-id="e2d28-113">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d28-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="e2d28-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d28-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2d28-115">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d28-116">Mappage statique des valeurs MediaID et multimédias :</span><span class="sxs-lookup"><span data-stu-id="e2d28-116">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2d28-117">1 – MESSAGERIE INSTANTANÉE</span><span class="sxs-lookup"><span data-stu-id="e2d28-117">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="e2d28-118">2 – Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="e2d28-118">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="e2d28-119">3 – Assistance à distance</span><span class="sxs-lookup"><span data-stu-id="e2d28-119">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="e2d28-120">4 – Partage d’application</span><span class="sxs-lookup"><span data-stu-id="e2d28-120">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="e2d28-121">5 – audio</span><span class="sxs-lookup"><span data-stu-id="e2d28-121">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="e2d28-122">6 – vidéo</span><span class="sxs-lookup"><span data-stu-id="e2d28-122">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="e2d28-123">7 – Invitation d’application</span><span class="sxs-lookup"><span data-stu-id="e2d28-123">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e2d28-124">Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR. SessionDetailsView. MediaTypes, vous devez utiliser l’extrait de code de jointure suivant :</span><span class="sxs-lookup"><span data-stu-id="e2d28-124">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

