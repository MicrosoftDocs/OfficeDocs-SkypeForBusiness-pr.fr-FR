---
title: Surveiller l’utilisation du service de mobilité et de UCWA dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé: gestion du service de mobilité (MCX) et de l’API Web de communications unifiées (UCWA) dans Skype entreprise Server.'
ms.openlocfilehash: 5447eb0ac8ffe468fd52c7011824cc1f2f2f7b55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279794"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="86321-103">Surveiller l’utilisation du service de mobilité et de UCWA dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="86321-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="86321-104">**Résumé:** Gestion du service de mobilité (MCX) et de l’API Web de communications unifiées (UCWA) dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="86321-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="86321-105">La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="86321-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="86321-106">Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts.</span><span class="sxs-lookup"><span data-stu-id="86321-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="86321-107">Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="86321-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="86321-108">D’un point de vue continu, vous devez surveiller l’unité centrale et la mémoire utilisée par le service de mobilité Skype entreprise Server (MCX) et l’API Web de communications unifiées (UCWA).</span><span class="sxs-lookup"><span data-stu-id="86321-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="86321-109">Pour cela, vous pouvez utiliser l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="86321-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="86321-110">**Pour l’API web de communications unifiées (UCWA) :**</span><span class="sxs-lookup"><span data-stu-id="86321-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="86321-111">Processus de travail **LyncUcwa** dans le gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="86321-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="86321-112">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="86321-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="86321-113">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="86321-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="86321-114">Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="86321-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="86321-115">L’utilisation de la mémoire doit être comprise dans les limites décrites dans [surveiller les limites de capacité de mémoire du serveur dans Skype entreprise Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="86321-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="86321-116">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="86321-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="86321-117">**Ls: limitations sur le Web et Authentication\WEB: total des demandes de traitement**, qui indique le nombre de demandes Web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="86321-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="86321-118">Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="86321-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="86321-119">**ASP.NET\Requests Queued** (doit toujours être égal à zéro).</span><span class="sxs-lookup"><span data-stu-id="86321-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="86321-120">Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.</span><span class="sxs-lookup"><span data-stu-id="86321-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="86321-121">**Pour le service de mobilité (Mcx) :**</span><span class="sxs-lookup"><span data-stu-id="86321-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="86321-122">Processus du travailleur **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="86321-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="86321-123">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="86321-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="86321-124">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="86321-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="86321-125">Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="86321-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="86321-126">L’utilisation de la mémoire doit être comprise dans les limites décrites dans [surveiller les limites de capacité de mémoire du serveur dans Skype entreprise Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="86321-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="86321-127">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="86321-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="86321-128">**ASP.NET v2.0.50727\Requests Current**, qui indique le nombre de demandes web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="86321-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="86321-129">Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="86321-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="86321-130">**ASP.NET\Requests Queued** (doit toujours être égal à zéro).</span><span class="sxs-lookup"><span data-stu-id="86321-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="86321-131">Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.</span><span class="sxs-lookup"><span data-stu-id="86321-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="86321-132">La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="86321-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="86321-133">Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts.</span><span class="sxs-lookup"><span data-stu-id="86321-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="86321-134">Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="86321-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86321-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86321-135">See also</span></span>

[<span data-ttu-id="86321-136">Surveiller les limites de capacité de mémoire serveur dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="86321-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
