---
title: 'Lync Server 2013 : table table errordef'
description: 'Lync Server 2013 : table table errordef.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542750"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="30ab5-103">Table table errordef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30ab5-103">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30ab5-104">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="30ab5-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="30ab5-105">La table table errordef stocke des informations sur chaque type d’erreur pouvant se produire.</span><span class="sxs-lookup"><span data-stu-id="30ab5-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="30ab5-106">Chaque enregistrement est un type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="30ab5-106">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30ab5-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="30ab5-107">Column</span></span></th>
<th><span data-ttu-id="30ab5-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="30ab5-108">Data Type</span></span></th>
<th><span data-ttu-id="30ab5-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="30ab5-109">Key/Index</span></span></th>
<th><span data-ttu-id="30ab5-110">Détails</span><span class="sxs-lookup"><span data-stu-id="30ab5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30ab5-111"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="30ab5-111"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="30ab5-112">int</span><span class="sxs-lookup"><span data-stu-id="30ab5-112">int</span></span></p></td>
<td><p><span data-ttu-id="30ab5-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="30ab5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="30ab5-114">Numéro d’identification unique identifiant ce type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="30ab5-114">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30ab5-115"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="30ab5-115"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="30ab5-116">int</span><span class="sxs-lookup"><span data-stu-id="30ab5-116">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30ab5-117">Code de réponse SIP standard associé à cette erreur.</span><span class="sxs-lookup"><span data-stu-id="30ab5-117">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30ab5-118"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="30ab5-118"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="30ab5-119">int</span><span class="sxs-lookup"><span data-stu-id="30ab5-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30ab5-120">ID de diagnostic Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30ab5-120">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30ab5-121"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="30ab5-121"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="30ab5-122">Int</span><span class="sxs-lookup"><span data-stu-id="30ab5-122">Int</span></span></p></td>
<td><p><span data-ttu-id="30ab5-123">Etranger</span><span class="sxs-lookup"><span data-stu-id="30ab5-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30ab5-124">Type de l’appel.</span><span class="sxs-lookup"><span data-stu-id="30ab5-124">Type of the call.</span></span> <span data-ttu-id="30ab5-125">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-calltype-table.md">table CallType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30ab5-125">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30ab5-126"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="30ab5-126"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="30ab5-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="30ab5-127">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30ab5-128">Type de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="30ab5-128">Type of request that failed.</span></span></p>
<p><span data-ttu-id="30ab5-129">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="30ab5-129">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30ab5-130"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="30ab5-130"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="30ab5-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="30ab5-131">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30ab5-132">Type de contenu de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="30ab5-132">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="30ab5-133">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="30ab5-133">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

