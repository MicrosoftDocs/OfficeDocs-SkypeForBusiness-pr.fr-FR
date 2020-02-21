---
title: 'Lync Server 2013 : table IMReportSummary'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d13401f38677d75bc40cbb4c1bd56f2fbb7fbb4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="23010-102">Table IMReportSummary dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23010-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23010-103">_**Dernière modification de la rubrique :** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="23010-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="23010-104">Le IMReportSummaryTable fournit un rapport général sur les sessions de messagerie instantanée organisées dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="23010-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="23010-105">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23010-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23010-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="23010-106">Column</span></span></th>
<th><span data-ttu-id="23010-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="23010-107">Data Type</span></span></th>
<th><span data-ttu-id="23010-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="23010-108">Key/Index</span></span></th>
<th><span data-ttu-id="23010-109">Détails</span><span class="sxs-lookup"><span data-stu-id="23010-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23010-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="23010-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="23010-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="23010-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="23010-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="23010-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="23010-113">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="23010-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23010-114"><strong>Période</strong></span><span class="sxs-lookup"><span data-stu-id="23010-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="23010-115">Char(1</span><span class="sxs-lookup"><span data-stu-id="23010-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="23010-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="23010-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23010-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="23010-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="23010-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="23010-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="23010-119">Primaire</span><span class="sxs-lookup"><span data-stu-id="23010-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="23010-120">Nom de domaine complet du pool qui héberge la session.</span><span class="sxs-lookup"><span data-stu-id="23010-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23010-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="23010-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="23010-122">int</span><span class="sxs-lookup"><span data-stu-id="23010-122">int</span></span></p></td>
<td><p><span data-ttu-id="23010-123">Primaire</span><span class="sxs-lookup"><span data-stu-id="23010-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="23010-124">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="23010-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="23010-125">Les informations sur la priorité sont stockées dans la <a href="lync-server-2013-callpriorities-table.md">table table callpriorities dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="23010-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23010-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="23010-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="23010-127">comportant</span><span class="sxs-lookup"><span data-stu-id="23010-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23010-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="23010-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="23010-129">comportant</span><span class="sxs-lookup"><span data-stu-id="23010-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23010-130">Nombre total de messages instantanés échangés pendant la session.</span><span class="sxs-lookup"><span data-stu-id="23010-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

