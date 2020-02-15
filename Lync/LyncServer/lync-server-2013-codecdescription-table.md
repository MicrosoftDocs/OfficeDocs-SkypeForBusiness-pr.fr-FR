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
ms.openlocfilehash: 4be7b878d3d9b6457fbda7a081db9b6b6cb80314
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="7e014-102">Table CodecDescription dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e014-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e014-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="7e014-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="7e014-104">Le tableau CodecDescription mappe les identificateurs de codecs uniques à leur codec correspondant.</span><span class="sxs-lookup"><span data-stu-id="7e014-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="7e014-105">Les codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder ces signaux en vue de leur lecture.</span><span class="sxs-lookup"><span data-stu-id="7e014-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="7e014-106">Cette table a été introduite dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e014-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e014-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="7e014-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7e014-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="7e014-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7e014-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="7e014-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7e014-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="7e014-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e014-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="7e014-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7e014-112">type</span><span class="sxs-lookup"><span data-stu-id="7e014-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e014-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="7e014-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e014-114">Identificateur unique affecté au codec.</span><span class="sxs-lookup"><span data-stu-id="7e014-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e014-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="7e014-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="7e014-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e014-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e014-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="7e014-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="7e014-118">Description unique du codec correspondant au CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="7e014-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

