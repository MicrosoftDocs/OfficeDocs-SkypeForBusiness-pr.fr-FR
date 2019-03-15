---
title: Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé : Gérer le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.'
ms.openlocfilehash: 6856235e5e5a8179e52836901598f7fbe2852a57
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "21227015"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="3eca3-103">Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="3eca3-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="3eca3-104">**Résumé :** Gérer le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="3eca3-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="3eca3-105">Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3eca3-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="3eca3-106">Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="3eca3-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="3eca3-107">Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="3eca3-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="3eca3-108">De manière continue, vous devez surveiller le processeur et la mémoire utilisée par le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifiée.</span><span class="sxs-lookup"><span data-stu-id="3eca3-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="3eca3-109">Pour cela, vous pouvez utiliser l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3eca3-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="3eca3-110">**Pour l’API web de communications unifiées (UCWA) :**</span><span class="sxs-lookup"><span data-stu-id="3eca3-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="3eca3-111">Le processus de travail **LyncUcwa** dans le Gestionnaire des Services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="3eca3-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="3eca3-112">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="3eca3-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="3eca3-113">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="3eca3-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="3eca3-114">Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="3eca3-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="3eca3-115">Utilisation de la mémoire doit être dans les limites décrites dans [surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="3eca3-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="3eca3-116">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="3eca3-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="3eca3-117">**LS:WEB - limitation et Authentication\WEB - nombre Total de demandes de traitement en**, qui indique le nombre de demandes web sur le serveur en attente.</span><span class="sxs-lookup"><span data-stu-id="3eca3-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="3eca3-118">Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="3eca3-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="3eca3-119">**ASP.NET\Requests Queued** (doit toujours être égal à zéro).</span><span class="sxs-lookup"><span data-stu-id="3eca3-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="3eca3-120">Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.</span><span class="sxs-lookup"><span data-stu-id="3eca3-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="3eca3-121">**Pour le service de mobilité (Mcx) :**</span><span class="sxs-lookup"><span data-stu-id="3eca3-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="3eca3-122">Processus de travail **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le Gestionnaire des Services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="3eca3-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="3eca3-123">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="3eca3-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="3eca3-124">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="3eca3-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="3eca3-125">Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="3eca3-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="3eca3-126">Utilisation de la mémoire doit être dans les limites décrites dans [surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="3eca3-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="3eca3-127">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="3eca3-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="3eca3-128">**ASP.NET v2.0.50727\Requests Current**, qui indique le nombre de demandes web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="3eca3-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="3eca3-129">Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="3eca3-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="3eca3-130">**ASP.NET\Requests Queued** (doit toujours être égal à zéro).</span><span class="sxs-lookup"><span data-stu-id="3eca3-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="3eca3-131">Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.</span><span class="sxs-lookup"><span data-stu-id="3eca3-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="3eca3-132">Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3eca3-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="3eca3-133">Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="3eca3-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="3eca3-134">Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="3eca3-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3eca3-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3eca3-135">See also</span></span>

[<span data-ttu-id="3eca3-136">Surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="3eca3-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)