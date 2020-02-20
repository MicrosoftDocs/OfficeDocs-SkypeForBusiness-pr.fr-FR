---
title: 'Lync Server 2013 : analyse des performances de stockage back-end Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48db772a35177571b1affe7c69674cc7fce07ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="b7cec-102">Surveillance des performances de stockage principales de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7cec-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7cec-103">_**Dernière modification de la rubrique :** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="b7cec-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="b7cec-104">Les bases de données principales Lync Server 2013 sont un élément très important du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7cec-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="b7cec-105">Nous vous recommandons de surveiller en permanence les bases de données et les journaux de transactions respectifs afin de s’assurer que le serveur principal Lync Server 2013 fonctionne de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="b7cec-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="b7cec-106">Le tableau suivant identifie les compteurs de performance qui doivent être surveillés afin d’obtenir des informations sur les performances de stockage.</span><span class="sxs-lookup"><span data-stu-id="b7cec-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="b7cec-107">Les valeurs de base de ces compteurs doivent être définies en premier (lorsque le système est à sa charge normale et attendue) pour comprendre les changements de performances lorsque le système est surchargé.</span><span class="sxs-lookup"><span data-stu-id="b7cec-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="b7cec-108">Compteurs de performance à surveiller</span><span class="sxs-lookup"><span data-stu-id="b7cec-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7cec-109">Compteur de performance</span><span class="sxs-lookup"><span data-stu-id="b7cec-109">Performance Counter</span></span></th>
<th><span data-ttu-id="b7cec-110">Seuils de ligne de base</span><span class="sxs-lookup"><span data-stu-id="b7cec-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7cec-111">Transactions/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="b7cec-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7cec-112">Transactions/s (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="b7cec-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7cec-113">Transactions/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="b7cec-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7cec-114">Vidages du journal/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="b7cec-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7cec-115">Vidages du journal/s (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="b7cec-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7cec-116">Vidages du journal/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="b7cec-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7cec-117">Transferts disque/s (lecture + écriture)-RTC DB</span><span class="sxs-lookup"><span data-stu-id="b7cec-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7cec-118">Transferts disque/s-journal RTC</span><span class="sxs-lookup"><span data-stu-id="b7cec-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7cec-119">Transferts disque/s-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="b7cec-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7cec-120">Transferts disque/s-journal RTCDyn</span><span class="sxs-lookup"><span data-stu-id="b7cec-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

