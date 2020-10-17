---
title: 'Lync Server 2013 : table CodecDescription'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed272afa7fe21a7b40004fb93dcdfa239b4caf8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520661"
---
# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="c2991-102">Table CodecDescription dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2991-102">CodecDescription table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2991-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="c2991-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="c2991-104">Le tableau CodecDescription mappe les identificateurs de codecs uniques à leur codec correspondant.</span><span class="sxs-lookup"><span data-stu-id="c2991-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="c2991-105">Les codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder ces signaux en vue de leur lecture.</span><span class="sxs-lookup"><span data-stu-id="c2991-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="c2991-106">Cette table a été introduite dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2991-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2991-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="c2991-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c2991-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="c2991-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c2991-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="c2991-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c2991-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c2991-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2991-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="c2991-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c2991-112">type</span><span class="sxs-lookup"><span data-stu-id="c2991-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="c2991-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="c2991-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c2991-114">Identificateur unique affecté au codec.</span><span class="sxs-lookup"><span data-stu-id="c2991-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2991-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="c2991-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="c2991-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2991-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2991-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="c2991-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="c2991-118">Description unique du codec correspondant au CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="c2991-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

