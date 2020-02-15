---
title: 'Lync Server 2013 : table SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 164c6e1541869a2976f283443f2fae9246f28007
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="3d0a6-102">Table SIPResponseMetaData dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d0a6-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d0a6-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3d0a6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3d0a6-p101">La table SIPResponseMetaDataTable contient la liste des codes de réponse SIP et les classification et définition de chacun de ces codes. Ceux-ci sont générés en réponse aux événements affectant les périphériques SIP et les sessions de communication SIP. Par exemple, le code de réponse 403 est généré quand un périphérique SIP effectue une requête, mais que le serveur refuse d’honorer cette requête.</span><span class="sxs-lookup"><span data-stu-id="3d0a6-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="3d0a6-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d0a6-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d0a6-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="3d0a6-107">Column</span></span></th>
<th><span data-ttu-id="3d0a6-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="3d0a6-108">Data Type</span></span></th>
<th><span data-ttu-id="3d0a6-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="3d0a6-109">Key/Index</span></span></th>
<th><span data-ttu-id="3d0a6-110">Détails</span><span class="sxs-lookup"><span data-stu-id="3d0a6-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d0a6-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3d0a6-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3d0a6-112">int</span><span class="sxs-lookup"><span data-stu-id="3d0a6-112">int</span></span></p></td>
<td><p><span data-ttu-id="3d0a6-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="3d0a6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3d0a6-114">Valeur numérique qui représente le code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="3d0a6-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d0a6-115"><strong>Classe</strong></span><span class="sxs-lookup"><span data-stu-id="3d0a6-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="3d0a6-116">int</span><span class="sxs-lookup"><span data-stu-id="3d0a6-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3d0a6-p102">Classification générale pour le code de réponse. Les classifications comprennent :</span><span class="sxs-lookup"><span data-stu-id="3d0a6-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3d0a6-119">1 – Réponses informatives</span><span class="sxs-lookup"><span data-stu-id="3d0a6-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="3d0a6-120">2 – Réponses réussies</span><span class="sxs-lookup"><span data-stu-id="3d0a6-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="3d0a6-121">3 – Réponses de redirection</span><span class="sxs-lookup"><span data-stu-id="3d0a6-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="3d0a6-122">4 – Réponses d’échec de client</span><span class="sxs-lookup"><span data-stu-id="3d0a6-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="3d0a6-123">5--réponses d’échec de serveur</span><span class="sxs-lookup"><span data-stu-id="3d0a6-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="3d0a6-124">6 – Réponse d’échec global</span><span class="sxs-lookup"><span data-stu-id="3d0a6-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d0a6-125"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="3d0a6-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="3d0a6-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3d0a6-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3d0a6-p103">Description du code de réponse SIP. Par exemple, le code de réponse 181 a la description suivante :</span><span class="sxs-lookup"><span data-stu-id="3d0a6-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="3d0a6-129">L’appel est en cours de transfert</span><span class="sxs-lookup"><span data-stu-id="3d0a6-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

