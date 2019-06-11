---
title: 'Tableau Lync Server 2013: SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31df563172cce2e6ac9780511665ef563532a7d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="194e7-102">Table SIPResponseMetaData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="194e7-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="194e7-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="194e7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="194e7-104">Le SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes.</span><span class="sxs-lookup"><span data-stu-id="194e7-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="194e7-105">Ces codes sont générés en réponse à des événements affectant des périphériques SIP et des sessions de communication SIP; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais que le serveur décline la demande.</span><span class="sxs-lookup"><span data-stu-id="194e7-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="194e7-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="194e7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="194e7-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="194e7-107">Column</span></span></th>
<th><span data-ttu-id="194e7-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="194e7-108">Data Type</span></span></th>
<th><span data-ttu-id="194e7-109">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="194e7-109">Key/Index</span></span></th>
<th><span data-ttu-id="194e7-110">Détails</span><span class="sxs-lookup"><span data-stu-id="194e7-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="194e7-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="194e7-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="194e7-112">int</span><span class="sxs-lookup"><span data-stu-id="194e7-112">int</span></span></p></td>
<td><p><span data-ttu-id="194e7-113">Principal</span><span class="sxs-lookup"><span data-stu-id="194e7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="194e7-114">Valeur numérique qui représente le code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="194e7-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="194e7-115"><strong>Cours</strong></span><span class="sxs-lookup"><span data-stu-id="194e7-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="194e7-116">int</span><span class="sxs-lookup"><span data-stu-id="194e7-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194e7-117">Classification générale du code de réponse.</span><span class="sxs-lookup"><span data-stu-id="194e7-117">General classification for the response code.</span></span> <span data-ttu-id="194e7-118">Les classifications sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="194e7-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="194e7-119">1 – réponses d’information</span><span class="sxs-lookup"><span data-stu-id="194e7-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="194e7-120">2 – réponses réussies</span><span class="sxs-lookup"><span data-stu-id="194e7-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="194e7-121">3 – réponses de redirection</span><span class="sxs-lookup"><span data-stu-id="194e7-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="194e7-122">4 – réponses d’échec client</span><span class="sxs-lookup"><span data-stu-id="194e7-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="194e7-123">5 réponses aux échecs sur le serveur</span><span class="sxs-lookup"><span data-stu-id="194e7-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="194e7-124">6-réponse d’échec globale</span><span class="sxs-lookup"><span data-stu-id="194e7-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="194e7-125"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="194e7-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="194e7-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="194e7-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194e7-127">Description du code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="194e7-127">Description of the SIP response code.</span></span> <span data-ttu-id="194e7-128">Par exemple, le code de réponse 181 contient la description suivante:</span><span class="sxs-lookup"><span data-stu-id="194e7-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="194e7-129">Appel en cours de transfert</span><span class="sxs-lookup"><span data-stu-id="194e7-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

