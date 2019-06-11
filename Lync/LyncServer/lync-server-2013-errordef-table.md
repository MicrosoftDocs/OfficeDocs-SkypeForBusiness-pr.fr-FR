---
title: 'Lync Server 2013 : Table ErrorDef'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef21484d564419a5ab5cce7373ceb0b0b71e4a29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="f2949-102">Table ErrorDef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2949-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2949-103">_**Dernière modification de la rubrique:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="f2949-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="f2949-104">La table ErrorDef stocke des informations sur chaque type d’erreur pouvant se produire.</span><span class="sxs-lookup"><span data-stu-id="f2949-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="f2949-105">Chaque enregistrement correspond à un type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="f2949-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2949-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="f2949-106">Column</span></span></th>
<th><span data-ttu-id="f2949-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="f2949-107">Data Type</span></span></th>
<th><span data-ttu-id="f2949-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="f2949-108">Key/Index</span></span></th>
<th><span data-ttu-id="f2949-109">Détails</span><span class="sxs-lookup"><span data-stu-id="f2949-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2949-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="f2949-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2949-111">int</span><span class="sxs-lookup"><span data-stu-id="f2949-111">int</span></span></p></td>
<td><p><span data-ttu-id="f2949-112">Principal</span><span class="sxs-lookup"><span data-stu-id="f2949-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f2949-113">Numéro d’identification unique identifiant ce type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="f2949-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2949-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f2949-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f2949-115">int</span><span class="sxs-lookup"><span data-stu-id="f2949-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f2949-116">Code de réponse SIP standard associé à cette erreur.</span><span class="sxs-lookup"><span data-stu-id="f2949-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2949-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="f2949-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2949-118">int</span><span class="sxs-lookup"><span data-stu-id="f2949-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f2949-119">ID de diagnostic Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2949-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2949-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f2949-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2949-121">Ent</span><span class="sxs-lookup"><span data-stu-id="f2949-121">Int</span></span></p></td>
<td><p><span data-ttu-id="f2949-122">Externes</span><span class="sxs-lookup"><span data-stu-id="f2949-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2949-123">Type de l’appel.</span><span class="sxs-lookup"><span data-stu-id="f2949-123">Type of the call.</span></span> <span data-ttu-id="f2949-124">Pour plus d’informations, voir la <a href="lync-server-2013-calltype-table.md">table CallType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2949-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2949-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="f2949-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="f2949-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="f2949-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f2949-127">Type de requête ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="f2949-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="f2949-128">Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:</span><span class="sxs-lookup"><span data-stu-id="f2949-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2949-129"><strong>Indiquez</strong></span><span class="sxs-lookup"><span data-stu-id="f2949-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="f2949-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="f2949-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f2949-131">Type de contenu de la requête qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="f2949-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="f2949-132">Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:</span><span class="sxs-lookup"><span data-stu-id="f2949-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

