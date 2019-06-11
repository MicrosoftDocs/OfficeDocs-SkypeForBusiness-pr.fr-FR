---
title: 'Tableau Lync Server 2013: IMReportSummary'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2254bafe059cc1a4bc6436580e9d604711f5fb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="3f04a-102">Table IMReportSummary dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f04a-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f04a-103">_**Dernière modification de la rubrique:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="3f04a-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="3f04a-104">Le IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="3f04a-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="3f04a-105">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f04a-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f04a-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="3f04a-106">Column</span></span></th>
<th><span data-ttu-id="3f04a-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="3f04a-107">Data Type</span></span></th>
<th><span data-ttu-id="3f04a-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="3f04a-108">Key/Index</span></span></th>
<th><span data-ttu-id="3f04a-109">Détails</span><span class="sxs-lookup"><span data-stu-id="3f04a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f04a-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f04a-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f04a-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3f04a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3f04a-112">Principal</span><span class="sxs-lookup"><span data-stu-id="3f04a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f04a-113">Date et heure de début de la session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="3f04a-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f04a-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="3f04a-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="3f04a-115">Char(1</span><span class="sxs-lookup"><span data-stu-id="3f04a-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="3f04a-116">Principal</span><span class="sxs-lookup"><span data-stu-id="3f04a-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f04a-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="3f04a-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="3f04a-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="3f04a-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="3f04a-119">Principal</span><span class="sxs-lookup"><span data-stu-id="3f04a-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f04a-120">Nom de domaine complet du pool hébergeant la session.</span><span class="sxs-lookup"><span data-stu-id="3f04a-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f04a-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="3f04a-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="3f04a-122">int</span><span class="sxs-lookup"><span data-stu-id="3f04a-122">int</span></span></p></td>
<td><p><span data-ttu-id="3f04a-123">Principal</span><span class="sxs-lookup"><span data-stu-id="3f04a-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f04a-124">Priorité (par exemple, urgent ou non urgent) de l’appel.</span><span class="sxs-lookup"><span data-stu-id="3f04a-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="3f04a-125">Les informations de priorité sont stockées dans la <a href="lync-server-2013-callpriorities-table.md">table CallPriorities dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3f04a-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f04a-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="3f04a-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="3f04a-127">bigint</span><span class="sxs-lookup"><span data-stu-id="3f04a-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f04a-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="3f04a-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="3f04a-129">bigint</span><span class="sxs-lookup"><span data-stu-id="3f04a-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f04a-130">Nombre total de messages instantanés échangés lors de la session.</span><span class="sxs-lookup"><span data-stu-id="3f04a-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

