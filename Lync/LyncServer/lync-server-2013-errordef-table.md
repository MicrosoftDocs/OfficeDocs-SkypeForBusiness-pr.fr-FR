---
title: 'Lync Server 2013 : table table errordef'
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
ms.openlocfilehash: 6db93ea1b09e50d48ee5e0276d90e3db3975e9fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="954ef-102">Table table errordef dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="954ef-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="954ef-103">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="954ef-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="954ef-104">La table table errordef stocke des informations sur chaque type d’erreur pouvant se produire.</span><span class="sxs-lookup"><span data-stu-id="954ef-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="954ef-105">Chaque enregistrement est un type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="954ef-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="954ef-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="954ef-106">Column</span></span></th>
<th><span data-ttu-id="954ef-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="954ef-107">Data Type</span></span></th>
<th><span data-ttu-id="954ef-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="954ef-108">Key/Index</span></span></th>
<th><span data-ttu-id="954ef-109">Détails</span><span class="sxs-lookup"><span data-stu-id="954ef-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="954ef-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="954ef-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="954ef-111">int</span><span class="sxs-lookup"><span data-stu-id="954ef-111">int</span></span></p></td>
<td><p><span data-ttu-id="954ef-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="954ef-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="954ef-113">Numéro d’identification unique identifiant ce type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="954ef-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="954ef-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="954ef-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="954ef-115">int</span><span class="sxs-lookup"><span data-stu-id="954ef-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="954ef-116">Code de réponse SIP standard associé à cette erreur.</span><span class="sxs-lookup"><span data-stu-id="954ef-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="954ef-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="954ef-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="954ef-118">int</span><span class="sxs-lookup"><span data-stu-id="954ef-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="954ef-119">ID de diagnostic Microsoft.</span><span class="sxs-lookup"><span data-stu-id="954ef-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="954ef-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="954ef-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="954ef-121">Int</span><span class="sxs-lookup"><span data-stu-id="954ef-121">Int</span></span></p></td>
<td><p><span data-ttu-id="954ef-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="954ef-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="954ef-123">Type de l’appel.</span><span class="sxs-lookup"><span data-stu-id="954ef-123">Type of the call.</span></span> <span data-ttu-id="954ef-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-calltype-table.md">table CallType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="954ef-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="954ef-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="954ef-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="954ef-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="954ef-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="954ef-127">Type de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="954ef-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="954ef-128">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="954ef-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="954ef-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="954ef-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="954ef-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="954ef-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="954ef-131">Type de contenu de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="954ef-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="954ef-132">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="954ef-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

