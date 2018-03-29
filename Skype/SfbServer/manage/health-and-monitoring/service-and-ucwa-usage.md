---
title: Surveillance de l’utilisation du service de mobilité et UCWA dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé : Gérer le Service de mobilité (Mcx) et le site Web de Communications unifiées API (UCWA) dans Skype pour Business Server 2015.'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a><span data-ttu-id="8d65f-103">Surveillance de l’utilisation du service de mobilité et UCWA dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d65f-103">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d65f-104">**Résumé :** Gérer le Service de mobilité (Mcx) et le site Web de Communications unifiées API (UCWA) dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8d65f-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8d65f-105">Régulièrement, vous devez analyser le processeur et la mémoire qui est utilisée par le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifiée.</span><span class="sxs-lookup"><span data-stu-id="8d65f-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="8d65f-106">Pour cela, vous pouvez utiliser l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="8d65f-106">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="8d65f-107">**Pour l’API web de communications unifiées (UCWA) :**</span><span class="sxs-lookup"><span data-stu-id="8d65f-107">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="8d65f-108">Le processus de travail **LyncUcwa** , dans le Gestionnaire des Services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="8d65f-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="8d65f-109">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="8d65f-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="8d65f-110">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="8d65f-110">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="8d65f-111">Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="8d65f-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="8d65f-112">Utilisation de la mémoire doit être dans les limites décrites dans le [moniteur pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="8d65f-112">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="8d65f-113">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="8d65f-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="8d65f-114">**LS:WEB - la limitation et Authentication\WEB - nombre Total de demandes dans le traitement de**, qui indique le nombre de demandes web sur le serveur en attente.</span><span class="sxs-lookup"><span data-stu-id="8d65f-114">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="8d65f-115">Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="8d65f-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="8d65f-116">**La file d’attente ASP.NET\Requests** (doit être toujours égal à zéro).</span><span class="sxs-lookup"><span data-stu-id="8d65f-116">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8d65f-117">Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.</span><span class="sxs-lookup"><span data-stu-id="8d65f-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="8d65f-118">**Pour le service de mobilité (Mcx) :**</span><span class="sxs-lookup"><span data-stu-id="8d65f-118">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="8d65f-119">Les processus de travail **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le Gestionnaire des Services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="8d65f-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="8d65f-120">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="8d65f-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="8d65f-121">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="8d65f-121">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="8d65f-122">Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="8d65f-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="8d65f-123">Utilisation de la mémoire doit être dans les limites décrites dans le [moniteur pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="8d65f-123">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="8d65f-124">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="8d65f-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="8d65f-125">**ASP.NET v2.0.50727\Requests actuel**, qui indique le nombre de demandes web sur le serveur en attente.</span><span class="sxs-lookup"><span data-stu-id="8d65f-125">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="8d65f-126">Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="8d65f-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="8d65f-127">**La file d’attente ASP.NET\Requests** (doit être toujours égal à zéro).</span><span class="sxs-lookup"><span data-stu-id="8d65f-127">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8d65f-128">Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.</span><span class="sxs-lookup"><span data-stu-id="8d65f-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8d65f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d65f-129">See also</span></span>

#### 

[<span data-ttu-id="8d65f-130">Moniteur pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d65f-130">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)

