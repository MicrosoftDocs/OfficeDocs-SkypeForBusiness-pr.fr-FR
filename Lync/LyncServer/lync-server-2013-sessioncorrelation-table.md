---
title: 'Lync Server 2013 : Table SessionCorrelation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c588a58126fb83df08550a6300ca8db36cceb647
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="69a4c-102">Table SessionCorrelation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69a4c-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69a4c-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="69a4c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="69a4c-104">La table SessionCorrelation est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="69a4c-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="69a4c-105">Chaque enregistrement représente une corrélation qui est utilisée pour mettre en corrélation plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="69a4c-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69a4c-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="69a4c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="69a4c-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="69a4c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="69a4c-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="69a4c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="69a4c-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="69a4c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69a4c-110"><strong>1018</strong></span><span class="sxs-lookup"><span data-stu-id="69a4c-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="69a4c-111">int</span><span class="sxs-lookup"><span data-stu-id="69a4c-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69a4c-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="69a4c-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="69a4c-113">int</span><span class="sxs-lookup"><span data-stu-id="69a4c-113">int</span></span></p></td>
<td><p><span data-ttu-id="69a4c-114">Principal</span><span class="sxs-lookup"><span data-stu-id="69a4c-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="69a4c-115">Numéro unique identifiant ce serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="69a4c-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69a4c-116"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="69a4c-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="69a4c-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="69a4c-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="69a4c-118">Différent</span><span class="sxs-lookup"><span data-stu-id="69a4c-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="69a4c-119">Les sessions corrélées auront le même ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="69a4c-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69a4c-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="69a4c-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="69a4c-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="69a4c-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69a4c-122">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="69a4c-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

