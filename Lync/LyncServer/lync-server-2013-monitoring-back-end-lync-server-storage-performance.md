---
title: 'Lync Server 2013: surveillance des performances du stockage principal de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="f0d6a-102">Surveiller les performances de stockage de Lync Server 2013 en arrière-plan</span><span class="sxs-lookup"><span data-stu-id="f0d6a-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0d6a-103">_**Dernière modification de la rubrique:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="f0d6a-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="f0d6a-104">Les bases de données principales de Lync Server 2013 constituent un élément essentiel du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0d6a-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="f0d6a-105">Nous vous recommandons de surveiller en permanence les bases de données et les journaux de transactions correspondants pour vous assurer que le serveur Lync Server 2013 fonctionne de façon optimale.</span><span class="sxs-lookup"><span data-stu-id="f0d6a-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="f0d6a-106">Le tableau suivant identifie les compteurs de performance qui doivent être surveillés pour en savoir plus sur les performances de stockage.</span><span class="sxs-lookup"><span data-stu-id="f0d6a-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="f0d6a-107">Les valeurs de référence de ces compteurs doivent d’abord être définies (lorsque le système se trouve à sa normale, charge attendue) pour comprendre les changements de performance lorsque le système est surchargé.</span><span class="sxs-lookup"><span data-stu-id="f0d6a-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="f0d6a-108">Compteurs de performance à surveiller</span><span class="sxs-lookup"><span data-stu-id="f0d6a-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0d6a-109">Compteur de performance</span><span class="sxs-lookup"><span data-stu-id="f0d6a-109">Performance Counter</span></span></th>
<th><span data-ttu-id="f0d6a-110">Seuils de référence</span><span class="sxs-lookup"><span data-stu-id="f0d6a-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0d6a-111">Transactions/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="f0d6a-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d6a-112">Transactions/s (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="f0d6a-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0d6a-113">Transactions/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="f0d6a-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d6a-114">Vidages du journal/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="f0d6a-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0d6a-115">Vidages du journal/s (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="f0d6a-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d6a-116">Vidages du journal/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="f0d6a-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0d6a-117">Transferts de disque/s (lecture + écriture)-RTC DB</span><span class="sxs-lookup"><span data-stu-id="f0d6a-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d6a-118">Transferts de disque/s-journal RTC</span><span class="sxs-lookup"><span data-stu-id="f0d6a-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0d6a-119">Transferts de disque/s-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="f0d6a-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d6a-120">Transfert de disque/s-journal de RTCDyn</span><span class="sxs-lookup"><span data-stu-id="f0d6a-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

