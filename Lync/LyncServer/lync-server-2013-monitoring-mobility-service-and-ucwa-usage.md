---
title: 'Lync Server 2013 : surveillance du service de mobilité et de l’utilisation de UCWA'
description: 'Lync Server 2013 : surveillance du service de mobilité et de l’utilisation d’UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6575941faf904e46cd1f66d7226a16c88e8cbaa3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548110"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="7601a-103">Surveillance du service de mobilité et de l’utilisation d’UCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7601a-103">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7601a-104">_**Dernière modification de la rubrique :** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="7601a-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="7601a-105">De façon continue, vous devez surveiller le processeur et la mémoire utilisés par le service Lync Server Mobility (MCX) et l’API Web Unified Communications (UCWA).</span><span class="sxs-lookup"><span data-stu-id="7601a-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="7601a-106">Pour surveiller l’utilisation, vous pouvez utiliser les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7601a-106">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="7601a-107">**Pour l’API Web de communications unifiées (UCWA) :**</span><span class="sxs-lookup"><span data-stu-id="7601a-107">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="7601a-108">Le processus de travail **LyncUcwa** dans le gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="7601a-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="7601a-109">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="7601a-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="7601a-110">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="7601a-110">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="7601a-111">Pour la plupart des déploiements, l’utilisation de l’UC UCWA doit être inférieure à 15% en moyenne.</span><span class="sxs-lookup"><span data-stu-id="7601a-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="7601a-112">L’utilisation de la mémoire doit être comprise dans les limites décrites dans [Monitoring for Server Memory Capacity Limits in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="7601a-112">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="7601a-113">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour vous aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="7601a-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="7601a-114">**Ls : Web – limitation et authentification \\ WEB : nombre total de demandes en cours de traitement**, ce qui indique le nombre de demandes Web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7601a-114">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="7601a-115">Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent, avec le message d’erreur « 503-Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="7601a-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="7601a-116">**ASP.NET \\ Demandes en file d’attente** (doit toujours être zéro).</span><span class="sxs-lookup"><span data-stu-id="7601a-116">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7601a-117">Si vous atteignez ou dépassez ces valeurs, vous devez reconsulter et recalculer la planification de la capacité pour le dimensionnement correct du processeur, le nombre de cœurs et de mémoire pour les ordinateurs hébergeant les services Web.</span><span class="sxs-lookup"><span data-stu-id="7601a-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="7601a-118">**Pour le service de mobilité (MCX) :**</span><span class="sxs-lookup"><span data-stu-id="7601a-118">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="7601a-119">Les processus de travail **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="7601a-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="7601a-120">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="7601a-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="7601a-121">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="7601a-121">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="7601a-122">Pour la plupart des déploiements, l’utilisation de l’UC du service de mobilité doit être inférieure à 15% en moyenne.</span><span class="sxs-lookup"><span data-stu-id="7601a-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="7601a-123">L’utilisation de la mémoire doit être comprise dans les limites décrites dans [Monitoring for Server Memory Capacity Limits in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="7601a-123">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="7601a-124">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="7601a-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="7601a-125">**ASP.net v 2.0.50727 \\ Demande les demandes en cours**, ce qui indique le nombre de demandes Web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7601a-125">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="7601a-126">Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503-Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="7601a-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="7601a-127">**ASP.NET \\ Demandes en file d’attente** (doit toujours être zéro).</span><span class="sxs-lookup"><span data-stu-id="7601a-127">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7601a-128">Si vous atteignez ou dépassez ces valeurs, vous devez revisiter et recalculer la planification de la capacité pour le dimensionnement correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs hébergeant les services Web.</span><span class="sxs-lookup"><span data-stu-id="7601a-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7601a-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7601a-129">See Also</span></span>


[<span data-ttu-id="7601a-130">Surveillance des limites de capacité de mémoire des serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7601a-130">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

