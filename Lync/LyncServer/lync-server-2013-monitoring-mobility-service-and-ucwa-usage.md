---
title: 'Lync Server 2013: analyse du service de mobilité et de l’utilisation de UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="af6c9-102">Surveiller l’utilisation du service de mobilité et de UCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af6c9-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af6c9-103">_**Dernière modification de la rubrique:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="af6c9-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="af6c9-104">En continu, vous devez surveiller le processeur et la mémoire utilisés par le service de mobilité Lync Server (MCX) et l’API UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="af6c9-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="af6c9-105">Pour cela, vous pouvez utiliser l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="af6c9-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="af6c9-106">**Pour l’API web de communications unifiées (UCWA) :**</span><span class="sxs-lookup"><span data-stu-id="af6c9-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="af6c9-107">Processus de travail **LyncUcwa** dans le gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="af6c9-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="af6c9-108">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="af6c9-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="af6c9-109">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="af6c9-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="af6c9-110">Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="af6c9-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="af6c9-111">L’utilisation de la mémoire doit être comprise dans les limites décrites dans [surveiller les limites de capacité de mémoire serveur dans Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="af6c9-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="af6c9-112">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="af6c9-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="af6c9-113">**Ls: Web – limitation et authentification\\Web: nombre total de demandes de traitement**indiquant le nombre de demandes Web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="af6c9-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="af6c9-114">Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="af6c9-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="af6c9-115">**Demandes\\ASP.net en file d’attente** (doit toujours être zéro).</span><span class="sxs-lookup"><span data-stu-id="af6c9-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af6c9-116">Si vous atteignez ou dépassez ces valeurs, vous devez recommencer et recalculer la planification de la capacité pour obtenir le dimensionnement correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs hébergeant les services Web.</span><span class="sxs-lookup"><span data-stu-id="af6c9-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="af6c9-117">**Pour le service de mobilité (Mcx) :**</span><span class="sxs-lookup"><span data-stu-id="af6c9-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="af6c9-118">Processus du travailleur **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="af6c9-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="af6c9-119">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="af6c9-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="af6c9-120">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="af6c9-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="af6c9-121">Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="af6c9-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="af6c9-122">L’utilisation de la mémoire doit être comprise dans les limites décrites dans [surveiller les limites de capacité de mémoire serveur dans Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="af6c9-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="af6c9-123">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="af6c9-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="af6c9-124">Les **requêtes d'\\ASP.net v 2.0.50727**indiquent le nombre de demandes Web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="af6c9-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="af6c9-125">Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="af6c9-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="af6c9-126">**Demandes\\ASP.net en file d’attente** (doit toujours être zéro).</span><span class="sxs-lookup"><span data-stu-id="af6c9-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af6c9-127">Si vous répondez ou dépassez ces valeurs, vous devez reconsulter et recalculer la planification de la capacité pour le dimensionnement correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs qui hébergent les services Web.</span><span class="sxs-lookup"><span data-stu-id="af6c9-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af6c9-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af6c9-128">See Also</span></span>


[<span data-ttu-id="af6c9-129">Surveiller les limites de capacité de mémoire serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af6c9-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

