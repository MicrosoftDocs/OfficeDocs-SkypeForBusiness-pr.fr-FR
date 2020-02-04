---
title: 'Tableau Lync Server 2013 : IMReportSummary'
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
ms.openlocfilehash: a7a6be73d31892b5a0d5a3a5b10ad136f92afbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="ca9b6-102">Table IMReportSummary dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca9b6-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca9b6-103">_**Dernière modification de la rubrique :** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="ca9b6-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="ca9b6-104">Le IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="ca9b6-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="ca9b6-105">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca9b6-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca9b6-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="ca9b6-106">Column</span></span></th>
<th><span data-ttu-id="ca9b6-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="ca9b6-107">Data Type</span></span></th>
<th><span data-ttu-id="ca9b6-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="ca9b6-108">Key/Index</span></span></th>
<th><span data-ttu-id="ca9b6-109">Détails</span><span class="sxs-lookup"><span data-stu-id="ca9b6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca9b6-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca9b6-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9b6-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ca9b6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca9b6-112">Principal</span><span class="sxs-lookup"><span data-stu-id="ca9b6-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca9b6-113">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="ca9b6-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca9b6-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="ca9b6-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9b6-115">Char(1</span><span class="sxs-lookup"><span data-stu-id="ca9b6-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="ca9b6-116">Principal</span><span class="sxs-lookup"><span data-stu-id="ca9b6-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca9b6-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="ca9b6-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9b6-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="ca9b6-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="ca9b6-119">Principal</span><span class="sxs-lookup"><span data-stu-id="ca9b6-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca9b6-120">Nom de domaine complet du pool hébergeant la session.</span><span class="sxs-lookup"><span data-stu-id="ca9b6-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca9b6-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="ca9b6-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9b6-122">int</span><span class="sxs-lookup"><span data-stu-id="ca9b6-122">int</span></span></p></td>
<td><p><span data-ttu-id="ca9b6-123">Principal</span><span class="sxs-lookup"><span data-stu-id="ca9b6-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca9b6-124">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="ca9b6-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="ca9b6-125">Les informations de priorité sont stockées dans la <a href="lync-server-2013-callpriorities-table.md">table CallPriorities dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ca9b6-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca9b6-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="ca9b6-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9b6-127">bigint</span><span class="sxs-lookup"><span data-stu-id="ca9b6-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca9b6-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="ca9b6-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ca9b6-129">bigint</span><span class="sxs-lookup"><span data-stu-id="ca9b6-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca9b6-130">Nombre total de messages instantanés échangés lors de la session.</span><span class="sxs-lookup"><span data-stu-id="ca9b6-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

